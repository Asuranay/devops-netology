1. git show aefea </br>
Update CHANGELOG.md</br>
aefead2207ef7e2aa5dc81a34aedf0cad4c32545
2. tag: v0.12.23
3. $ git log b8d720 --pretty=format:"%P"</br>
56cd7859e05c36c06b56d013b55a252d0bb7e158 
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


