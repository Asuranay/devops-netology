### Задание 1 ###
    Файл для автозагрузки

    [Unit]
    Description=Node Exporter
    Wants=network-online.target
    After=network-online.target

    [Service]
    User=node_exporter
    Group=node_exporter
    Type=simple
    ExecStart=/opt/node_exporter-1.4.0.linux-amd64/node_exporter --web.listen-address=":9100"

    [Install]
    WantedBy=multi-user.target

    Добавление в автозагрузку
    sudo systemctl daemon-reload
    sudo systemctl enable node_exporter
    sudo systemctl restart node_exporter
    sudo systemctl status node_exporter

    Скриншот работы
![Скриншот консоли](https://github.com/Asuranay/devops-netology/blob/main/homework/node_exporter.PNG?raw=true)
### Задание 2 ###
    curl http://localhost:9100/metrics | grep node_cpu

    node_cpu_guest_seconds_total{cpu="*",mode="*"}
    node_cpu_seconds_total{cpu="*",mode="*"}

    curl http://localhost:9100/metrics | grep node_memory

    node_memory_Active_file_bytes 1.6095232e+08
    node_memory_Buffers_bytes 4.8820224e+07
    node_memory_MemAvailable_bytes 7.686639616e+09

    curl http://localhost:9100/metrics | grep node_disk

    node_disk_discard_time_seconds_total{device="dm-0"} 0
    node_disk_discard_time_seconds_total{device="sda"} 0
    node_disk_read_bytes_total{device="dm-0"} 5.31006464e+08
    node_disk_read_bytes_total{device="sda"} 5.40420096e+08

    curl http://localhost:9100/metrics | grep node_network

    node_network_info{address="00:00:00:00:00:00",broadcast="00:00:00:00:00:00",device="lo",duplex="",ifalias="",operstate="unknown"} 1
    node_network_info{address="08:00:27:a2:6b:fd",broadcast="ff:ff:ff:ff:ff:ff",device="eth0",duplex="full",ifalias="",operstate="up"} 1
    node_network_mtu_bytes{device="eth0"} 1500
    node_network_mtu_bytes{device="lo"} 65536
### Задание 3 ###
    sudo apt install -y netdata
    curl -s https://packagecloud.io/install/repositories/netdata/netdata/script.deb.sh | sudo bash
    sudo vim /etc/netdata/netdata.conf
    Добавил раздел [web] с параметром bind to = 0.0.0.0
![localhost](https://github.com/Asuranay/devops-netology/blob/main/homework/localhost.PNG?raw=true)

### Задание 4 ###
    Да понимает. Видно и настоящую машину и виртуальную

    vagrant@vagrant:~$ dmesg | grep boot
    [    0.062359] smpboot: Allowing 4 CPUs, 0 hotplug CPUs
    [    0.228942] smpboot: CPU0: AMD Ryzen 7 5700G with Radeon Graphics (family: 0x19, model: 0x50, stepping: 0x0)
    [    0.237399] smpboot: Max logical packages: 1
    [    0.237563] smpboot: Total of 4 processors activated (30342.99 BogoMIPS)
    [    0.301595] pci 0000:00:02.0: vgaarb: setting as boot VGA device

    vagrant@vagrant:~$ dmesg | grep virt
    [    0.001587] CPU MTRRs all blank - virtualized system.
    [    0.062383] Booting paravirtualized kernel on KVM
    [    0.229289] Performance Events: PMU not available due to virtualization, using software events only.
    [    2.987920] systemd[1]: Detected virtualization oracle.
### Задание 5 ###
    vagrant@vagrant:~$ sysctl fs.nr_open
    fs.nr_open = 1048576 - это лимит на количество открытых файлов
    unlimit -aH
    unlimit -aS
### Задание 6 ###
    vagrant@vagrant:~$ sudo -i
    root@vagrant:~# unshare -f --pid --mount-proc sleep 1h
    ^Z
    [1]+  Stopped                 unshare -f --pid --mount-proc sleep 1h
    root@vagrant:~# ps -a
    PID TTY          TIME CMD
    1580 pts/0    00:00:00 sudo
    1581 pts/0    00:00:00 bash
    1593 pts/0    00:00:00 unshare
    1594 pts/0    00:00:00 sleep
    1595 pts/0    00:00:00 ps
    root@vagrant:~# nsenter --target 1594 --pid --mount
    root@vagrant:/# ps -a
    PID TTY          TIME CMD
    1 pts/0    00:00:00 sleep
    2 pts/0    00:00:00 bash
    13 pts/0    00:00:00 ps
### Задание 7 ###
    fork-бомба - функция вызывающая сама себя.
    :(){ :|:& };: -- выполнил
    -bash: fork: Resource temporarily unavailable
    dmesg | grep fork
    [   33.074494] cgroup: fork rejected by pids controller in /user.slice/user-1000.slice/session-3.scope
    ulimit -u -- изменяет порог процессов




