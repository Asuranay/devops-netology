1. git show aefea </br>
Update CHANGELOG.md</br>
aefead2207ef7e2aa5dc81a34aedf0cad4c32545
2. tag: v0.12.23
3. $ git log b8d720 --pretty=format:"%p"</br>
56cd7859e0 9ea88f22fc</br>
56cd7859e0</br>
58dcac4b79 ffbcf55817</br>
58dcac4b79</br>
472d958b10</br>
58ef73814e</br>
b6a041af2b dae1efe62a</br>
4e5a18c621</br>
8b0888798f</br>
c5300dc46d 6bad4e3dc0</br>
e184b9edb9 9e5fca67e8</br>
8ea60ea651</br>
7471779fca</br>
d72a192078</br>
82678ed156</br>
4d8fde3d6f</br>
5d3ca8aaf1</br>
4045a6e5d0</br>
2a95d98383</br>
2b2ac1f6de</br>
948d4d0ecf</br>
ae407060f0 62aae82913</br>
413e423bba</br>
4977120764 98c02ac114</br>
dc178789b2 e4c4c8cab5</br>
dc178789b2</br>
7f8e087ce3</br>
413e423bba</br>
413e423bba</br>
c0176aeab3</br>
c0176aeab3</br>
aa8a0f063c
4. $ git log v0.12.23..v0.12.24 --oneline</br>
33ff1c03bb (tag: v0.12.24) v0.12.24</br>
b14b74c493 [Website] vmc provider links</br>
3f235065b9 Update CHANGELOG.md</br>
6ae64e247b registry: Fix panic when server is unreachable</br>
5c619ca1ba website: Remove links to the getting started guide's old location</br>
06275647e2 Update CHANGELOG.md</br>
d5f9411f51 command: Fix bug when using terraform login on Windows</br>
4b6d06cc5d Update CHANGELOG.md</br>
dd01a35078 Update CHANGELOG.md</br>
225466bc3e Cleanup after v0.12.23 release
5. $ git log -S 'func providerSource' --pretty=format:'%h - %cd'</br>
5af1e6234a - Tue Apr 21 16:28:59 2020 -0700</br>
8c928e8358 - Mon Apr 6 09:24:23 2020 -0700</br>
func providerSource(services)
6. $ git log -S 'synchronizedWriters' --pretty=format:'%h - %cd \--/ %an -%ae'</br>
5ac311e2a9 - Thu May 4 15:36:51 2017 -0700 \--/ Martin Atkins -mart@degeneration.co.uk


