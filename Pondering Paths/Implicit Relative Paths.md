```bash
bin  boot  challenge  dev  etc  flag  home  lib  lib32  lib64  libx32  media  mnt  nix  opt  proc  root  run  sbin  srv  sys  tmp  usr  var
hacker@paths~implicit-relative-paths-from-:/$ cd challenge
hacker@paths~implicit-relative-paths-from-:/challenge$ run
ssh-entrypoint: run: command not found
hacker@paths~implicit-relative-paths-from-:/challenge$ /run
ssh-entrypoint: /run: Is a directory
hacker@paths~implicit-relative-paths-from-:/challenge$ challlenge/run
ssh-entrypoint: challlenge/run: No such file or directory
hacker@paths~implicit-relative-paths-from-:/challenge$ challenge/run
ssh-entrypoint: challenge/run: No such file or directory
hacker@paths~implicit-relative-paths-from-:/challenge$ exit
exit

Connected!                                                                        
hacker@paths~implicit-relative-paths-from-:~$ ls
Desktop
hacker@paths~implicit-relative-paths-from-:~$ cd /
hacker@paths~implicit-relative-paths-from-:/$ ls
bin  boot  challenge  dev  etc  flag  home  lib  lib32  lib64  libx32  media  mnt  nix  opt  proc  root  run  sbin  srv  sys  tmp  usr  var
hacker@paths~implicit-relative-paths-from-:/$ challenge/run
Correct!!!
challenge/run is a relative path, invoked from the right directory!
Here is your flag:
pwn.college{UJbs4O8m8Gk-uFiKEC-vO5wJAdV.dlDN1QDL0kzN0czW}
hacker@paths~implicit-relative-paths-from-:/$ 
```

# learnings:
- learnt how to access relative paths.
- learnt that relative paths dont start with '/'
