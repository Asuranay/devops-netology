### Задание 1 ###
    Это внутренняя/встроенная команда оболочки, ее поведение может немного отличаться от оболочки к оболочке. Он использует переменные среды оболочки для определения необходимой информации для его выполнения.
### Задание 2 ###
    grep <search> <file_name> -c 
### Задание 3 ###
    systemd, в старых дистрибутивах может быть init
<details><summary>Дерево</summary>
    pstree -p
    systemd(1)─┬─ModemManager(811)─┬─{ModemManager}(832)
           │                   └─{ModemManager}(835)
           ├─VBoxService(927)─┬─{VBoxService}(928)
           │                  ├─{VBoxService}(929)
           │                  ├─{VBoxService}(930)
           │                  ├─{VBoxService}(931)
           │                  ├─{VBoxService}(932)
           │                  ├─{VBoxService}(933)
           │                  ├─{VBoxService}(934)
           │                  └─{VBoxService}(935)
</details>

### Задание 4 ###
    ~$ ls -l /dev/stderr>/dev/pts/2
<details><summary>Пояснение для себя</summary>
    exec < filename - ввод из файла
    > - ввод и перезапись
    >> - добавление в файл строк
    find / -name wireless 2> denied.txt > found.txt- Разброс данных по файлам.
</details>

### Задание 5 ###
    команда 2> stderr.txt 0> stdout.txt 1> stdout.txt - разбросает потоки по соответсвующим названию файлам.
### Задание 6 ###
    Думаю что все реально. 
### Задание 7 ###
    bash 5>&1 - перенаправляет /pts/5 в stdout
    echo netology > /proc/$$/fd/5 - перенаправляет и выводит netology
<details><summary>Пояснение для себя</summary>
    Нужно перенаправлять потоки на вывод. Иначе получим ошибку No such file or directory
</details>

### Задание 8 ###
    ls -l 6>&2 2>&1 1>&6 | команда
### Задание 9 ###
     cat /proc/$$/environ
<details><summary>Вывод команды выше</summary>
    SHELL=/bin/bashPWD=/home/vagrantLOGNAME=vagrantXDG_SESSION_TYPE=ttyMOTD_SHOWN=pamHOME=/home/vagrantLANG=en_US.UTF-8LS_COLORS=rs=0:di=01;34:ln=01;36:mh=00:pi=40;33:so=01;35:do=01;35:bd=40;33;01:cd=40;33;01:or=40;31;01:mi=00:su=37;41:sg=30;43:ca=30;41:tw=30;42:ow=34;42:st=37;44:ex=01;32:*.tar=01;31:*.tgz=01;31:*.arc=01;31:*.arj=01;31:*.taz=01;31:*.lha=01;31:*.lz4=01;31:*.lzh=01;31:*.lzma=01;31:*.tlz=01;31:*.txz=01;31:*.tzo=01;31:*.t7z=01;31:*.zip=01;31:*.z=01;31:*.dz=01;31:*.gz=01;31:*.lrz=01;31:*.lz=01;31:*.lzo=01;31:*.xz=01;31:*.zst=01;31:*.tzst=01;31:*.bz2=01;31:*.bz=01;31:*.tbz=01;31:*.tbz2=01;31:*.tz=01;31:*.deb=01;31:*.rpm=01;31:*.jar=01;31:*.war=01;31:*.ear=01;31:*.sar=01;31:*.rar=01;31:*.alz=01;31:*.ace=01;31:*.zoo=01;31:*.cpio=01;31:*.7z=01;31:*.rz=01;31:*.cab=01;31:*.wim=01;31:*.swm=01;31:*.dwm=01;31:*.esd=01;31:*.jpg=01;35:*.jpeg=01;35:*.mjpg=01;35:*.mjpeg=01;35:*.gif=01;35:*.bmp=01;35:*.pbm=01;35:*.pgm=01;35:*.ppm=01;35:*.tga=01;35:*.xbm=01;35:*.xpm=01;35:*.tif=01;35:*.tiff=01;35:*.png=01;35:*.svg=01;35:*.svgz=01;35:*.mng=01;35:*.pcx=01;35:*.mov=01;35:*.mpg=01;35:*.mpeg=01;35:*.m2v=01;35:*.mkv=01;35:*.webm=01;35:*.ogm=01;35:*.mp4=01;35:*.m4v=01;35:*.mp4v=01;35:*.vob=01;35:*.qt=01;35:*.nuv=01;35:*.wmv=01;35:*.asf=01;35:*.rm=01;35:*.rmvb=01;35:*.flc=01;35:*.avi=01;35:*.fli=01;35:*.flv=01;35:*.gl=01;35:*.dl=01;35:*.xcf=01;35:*.xwd=01;35:*.yuv=01;35:*.cgm=01;35:*.emf=01;35:*.ogv=01;35:*.ogx=01;35:*.aac=00;36:*.au=00;36:*.flac=00;36:*.m4a=00;36:*.mid=00;36:*.midi=00;36:*.mka=00;36:*.mp3=00;36:*.mpc=00;36:*.ogg=00;36:*.ra=00;36:*.wav=00;36:*.oga=00;36:*.opus=00;36:*.spx=00;36:*.xspf=00;36:SSH_CONNECTION=10.0.2.2 1042 10.0.2.15 22LESSCLOSE=/usr/bin/lesspipe %s %sXDG_SESSION_CLASS=userTERM=xtermLESSOPEN=| /usr/bin/lesspipe %sUSER=vagrantSHLVL=1XDG_SESSION_ID=4XDG_RUNTIME_DIR=/run/user/1000SSH_CLIENT=10.0.2.2 1042 22XDG_DATA_DIRS=/usr/local/share:/usr/share:/var/lib/snapd/desktopPATH=/usr/local/sbin:/usr/local/bin:/usr/sbin:/usr/bin:/sbin:/bin:/usr/games:/usr/local/games:/snap/binDBUS_SESSION_BUS_ADDRESS=unix:path=/run/user/1000/busSSH_TTY=/dev/pts/1_=/usr/bin/bash
</details>
    
    env / printenv - вывод аналогичен, set добавит локальные переменные
### Задание 10 ###
    /proc/<PID>/cmdline - это файл только для чтения, который содержит полную информацию о процессе из командной строки. Если процесс был заменен местами в дополнение к памяти или процесс является зомби-процессом, то этот файл не имеет содержимого. Файл заканчивается нулевым символом вместо символа новой строки.
    /proc/<PID>/exe - это символическая ссылка на фактически работающую программу.
### Задание 11 ###
    sse версии 4_2
<details><summary>Информация о процессоре</summary>
    processor       : 7
    vendor_id       : AuthenticAMD
    cpu family      : 23
    model           : 113
    model name      : AMD Ryzen 9 3900X 12-Core Processor
    stepping        : 0
    cpu MHz         : 3799.996
    cache size      : 512 KB
    physical id     : 0
    siblings        : 8
    core id         : 7
    cpu cores       : 8
    apicid          : 7
    initial apicid  : 7
    fpu             : yes
    fpu_exception   : yes
    cpuid level     : 16
    wp              : yes
    flags           : fpu vme de pse tsc msr pae mce cx8 apic sep mtrr pge mca cmov pat pse36 clflush mmx fxsr sse sse2 ht syscall nx mmxext fxsr_opt rdtscp lm constant_tsc rep_good nopl nonstop_tsc cpuid extd_apicid tsc_known_freq pni pclmulqdq ssse3 cx16 sse4_1 sse4_2 x2apic movbe popcnt aes xsave avx rdrand hypervisor lahf_lm cmp_legacy cr8_legacy abm sse4a misalignsse 3dnowprefetch ssbd vmmcall fsgsbase bmi1 avx2 bmi2 rdseed clflushopt arat
    bugs            : fxsave_leak sysret_ss_attrs null_seg spectre_v1 spectre_v2
    bogomips        : 7599.99
    TLB size        : 3072 4K pages
    clflush size    : 64
    cache_alignment : 64
    address sizes   : 48 bits physical, 48 bits virtual
    power management:
</details>

### Задание 12 ###
    По умолчанию TTY не выделяется для удаленного сеанса, исправляется добавление -t или -tt.
<details><summary>-t и -tt</summary>
    -t Переназначение псевдо-терминала. Это может быть использовано для произвольного выполнения программ базирующихся на выводе изображения на удаленной машине, что может быть очень полезно, например, при реализации возможностей меню. Несколько параметров -t заданных подряд переназначат терминал, даже если ssh не имеет локального терминала.
</details>

### Задание 13 ###
    vagrant@vagrant:~$ top
<details><summary>Вывод команлды top</summary>
    top - 02:40:13 up 0 min,  1 user,  load average: 0.12, 0.04, 0.01
    Tasks: 131 total,   1 running, 130 sleeping,   0 stopped,   0 zombie
    %Cpu(s):  0.1 us,  0.0 sy,  0.0 ni, 99.9 id,  0.0 wa,  0.0 hi,  0.0 si,  0.0 st
    MiB Mem :   7791.3 total,   7308.1 free,    147.2 used,    336.0 buff/cache
    MiB Swap:   1953.0 total,   1953.0 free,      0.0 used.   7407.4 avail Mem

        PID USER      PR  NI    VIRT    RES    SHR S  %CPU  %MEM     TIME+ COMMAND
        1 root      20   0  101872  11348   8348 S   0.0   0.1   0:00.66 systemd
        2 root      20   0       0      0      0 S   0.0   0.0   0:00.00 kthreadd
        3 root       0 -20       0      0      0 I   0.0   0.0   0:00.00 rcu_gp
        4 root       0 -20       0      0      0 I   0.0   0.0   0:00.00 rcu_par_gp
        5 root      20   0       0      0      0 I   0.0   0.0   0:00.00 kworker/0:0-events
        6 root       0 -20       0      0      0 I   0.0   0.0   0:00.00 kworker/0:0H-kblockd
        7 root      20   0       0      0      0 I   0.0   0.0   0:00.02 kworker/0:1-events
        8 root      20   0       0      0      0 I   0.0   0.0   0:00.00 kworker/u8:0-events_power+
        9 root       0 -20       0      0      0 I   0.0   0.0   0:00.00 mm_percpu_wq
        10 root      20   0       0      0      0 S   0.0   0.0   0:00.00 ksoftirqd/0
        11 root      20   0       0      0      0 I   0.0   0.0   0:00.01 rcu_sched
        12 root      rt   0       0      0      0 S   0.0   0.0   0:00.00 migration/0
        13 root     -51   0       0      0      0 S   0.0   0.0   0:00.00 idle_inject/0
        14 root      20   0       0      0      0 S   0.0   0.0   0:00.00 cpuhp/0
        15 root      20   0       0      0      0 S   0.0   0.0   0:00.00 cpuhp/1
        16 root     -51   0       0      0      0 S   0.0   0.0   0:00.00 idle_inject/1
        17 root      rt   0       0      0      0 S   0.0   0.0   0:00.20 migration/1
        18 root      20   0       0      0      0 S   0.0   0.0   0:00.01 ksoftirqd/1
        19 root      20   0       0      0      0 I   0.0   0.0   0:00.00 kworker/1:0-events
        20 root       0 -20       0      0      0 I   0.0   0.0   0:00.00 kworker/1:0H-kblockd
        21 root      20   0       0      0      0 S   0.0   0.0   0:00.00 cpuhp/2
        22 root     -51   0       0      0      0 S   0.0   0.0   0:00.00 idle_inject/2
        23 root      rt   0       0      0      0 S   0.0   0.0   0:00.20 migration/2
        24 root      20   0       0      0      0 S   0.0   0.0   0:00.01 ksoftirqd/2
        25 root      20   0       0      0      0 I   0.0   0.0   0:00.00 kworker/2:0-events
        26 root       0 -20       0      0      0 I   0.0   0.0   0:00.00 kworker/2:0H-kblockd
        27 root      20   0       0      0      0 S   0.0   0.0   0:00.00 cpuhp/3
        28 root     -51   0       0      0      0 S   0.0   0.0   0:00.00 idle_inject/3
        29 root      rt   0       0      0      0 S   0.0   0.0   0:00.20 migration/3
        30 root      20   0       0      0      0 S   0.0   0.0   0:00.01 ksoftirqd/3
        31 root      20   0       0      0      0 I   0.0   0.0   0:00.00 kworker/3:0-cgroup_destroy
        32 root       0 -20       0      0      0 I   0.0   0.0   0:00.00 kworker/3:0H-kblockd
        33 root      20   0       0      0      0 S   0.0   0.0   0:00.00 kdevtmpfs
    [1]+  Stopped                 top
</details>

    vagrant@vagrant:~$ bg
    [1]+ top &
    vagrant@vagrant:~$ job -l
    -bash: job: command not found
    [1]+  Stopped                 top
    vagrant@vagrant:~$ disown top
    -bash: warning: deleting stopped job 1 with process group 1491
    vagrant@vagrant:~$ ps -a
        PID TTY          TIME CMD
    1491 pts/0    00:00:00 top
    1493 pts/0    00:00:00 ps
    vagrant@vagrant:~$ tmux
    [exited]
    вышел CTRL+C и прописал vagrant ssh заново
    vagrant@vagrant:~$ tmux attach
    no sessions
    vagrant@vagrant:~$ ps -a
    PID TTY          TIME CMD
    1611 pts/1    00:00:00 ps

### Задание 14 ###
    tee - считывает стандартный ввод и записывает его одновременно в стандартный вывод и в один или несколько файлов.
    tee запускается из под sudo
