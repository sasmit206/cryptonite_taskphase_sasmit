# code

```bash
hacker@paths~position-yet-elsewhere:~$ cd/
ssh-entrypoint: cd/: No such file or directory
hacker@paths~position-yet-elsewhere:~$ cd/
ssh-entrypoint: cd/: No such file or directory
hacker@paths~position-yet-elsewhere:~$ cd /
hacker@paths~position-yet-elsewhere:/$ ls
bin   challenge  etc   home  lib32  libx32  mnt  opt   root  sbin  sys  usr
boot  dev        flag  lib   lib64  media   nix  proc  run   srv   tmp  var
hacker@paths~position-yet-elsewhere:/$ /challenge/run
Incorrect...
You are not currently in the /usr/share/build-essential directory.
Please use the `cd` utility to change directory appropriately.
hacker@paths~position-yet-elsewhere:/$ cd /usr/share/build-essential
hacker@paths~position-yet-elsewhere:/usr/share/build-essential$ /challenge/run
Correct!!!
/challenge/run is an absolute path, invoked from the right directory!
Here is your flag:
pwn.college{8OJ96yFJPL7Gu6o7kqAPiyKJ6LO.dhDN1QDL0kzN0czW}
hacker@paths~position-yet-elsewhere:/usr/share/build-essential$
```

# learnings

- learnt to execute files from the correct directory
- to access the correct name of directory
