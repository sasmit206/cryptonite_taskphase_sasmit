# The Root
## code
```bash
Connected!
hacker@paths~the-root:~$ /pwn
BOOM!!!
Here is your flag:
pwn.college{4n2KC6qarpIG88AMpLxFk8s-KRr.dhzN5QDL0kzN0czW}
hacker@paths~the-root:~$ 
```

## learnings
- to be familiar with the mapping of absolute path to directories
- file system starts with /

# Position Thy Self
## code
```bash
Connected!
hacker@paths~position-thy-self:~$ cd /
hacker@paths~position-thy-self:/$ ls
bin   challenge  etc   home  lib32  libx32  mnt  opt   root  sbin  sys  usr
boot  dev        flag  lib   lib64  media   nix  proc  run   srv   tmp  var
hacker@paths~position-thy-self:/$ /challenge/run
Correct!!!
/challenge/run is an absolute path, invoked from the right directory!
Here is your flag:
pwn.college{4GvmlXI-HCaAr0pxtKGczsrnNxg.dZDN1QDL0kzN0czW}
hacker@paths~position-thy-self:/$ 


```

## learnings
got familiar with listing directories and execution of programs in a specific directory.
also got familiar with the cd & ls command

# Position Elsewhere
## code
``` bash
acker@paths~position-elsewhere:~$ cd /
hacker@paths~position-elsewhere:/$ ls
bin   challenge  etc   home  lib32  libx32  mnt  opt   root  sbin  sys  usr
boot  dev        flag  lib   lib64  media   nix  proc  run   srv   tmp  var
hacker@paths~position-elsewhere:/$ cd tmp
hacker@paths~position-elsewhere:/tmp$ /challenge/run
Incorrect...
You are not currently in the /usr/share/doc directory.
Please use the `cd` utility to change directory appropriately.
hacker@paths~position-elsewhere:/tmp$ cd /usr/share/doc
hacker@paths~position-elsewhere:/usr/share/doc$ /challenge/run
Correct!!!
/challenge/run is an absolute path, invoked from the right directory!
Here is your flag:
pwn.college{os35J5iSCxxZ-lQo4qvoT1LLn7x.ddDN1QDL0kzN0czW}
```

## learnings
to explore directories in the system
to execute the given program from a specified directory
learnt how to see the path from which the program was supposed to be executed,by the line "you are..."
# Position Yet Elsewhere
## code

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

## learnings

- learnt to execute files from the correct directory
- to access the correct name of directory

# Implicit Relative Path, from /
## code
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

## learnings:
- learnt how to access relative paths.
- learnt that relative paths dont start with '/'

# Explicit Relative Path, from /

## code
```bash
                                                        Connected!
hacker@paths~explicit-relative-paths-from-:~$ cd /
hacker@paths~explicit-relative-paths-from-:/$ ls
bin   challenge  etc   home  lib32  libx32  mnt  opt   root  sbin  sys  usr
boot  dev        flag  lib   lib64  media   nix  proc  run   srv   tmp  var
hacker@paths~explicit-relative-paths-from-:/$ /challenge/run
Incorrect...
You invoked this challenge with an absolute path. This challenge needs a relative path!
hacker@paths~explicit-relative-paths-from-:/$ challenge/run
Incorrect...
This challenge must be called with a relative path that explicitly starts with a `.`!
hacker@paths~explicit-relative-paths-from-:/$ .challenge/run
ssh-entrypoint: .challenge/run: No such file or directory
hacker@paths~explicit-relative-paths-from-:/$ ./challenge/run
Correct!!!
./challenge/run is a relative path, invoked from the right directory!
Here is your flag:
pwn.college{sgZb1F4_rbG23E9mMtM_TNrnvsk.dBTN1QDL0kzN0czW}
hacker@paths~explicit-relative-paths-from-:/$ 
```
## learnings
- the '.' refers to the same directory and is used to access the current directory where we are present.

# Implicit Relative Path
## code:
```bash
Connected!                                                                        
hacker@paths~implicit-relative-path:~$ cd /challenge
hacker@paths~implicit-relative-path:/challenge$ run
ssh-entrypoint: run: command not found
hacker@paths~implicit-relative-path:/challenge$ .run
ssh-entrypoint: .run: command not found
hacker@paths~implicit-relative-path:/challenge$ ./run
Correct!!!
./run is a relative path, invoked from the right directory!
Here is your flag:
pwn.college{gOIa7fdOYsh8S7S-zcKgaMg-3d6.dFTN1QDL0kzN0czW}
hacker@paths~implicit-relative-path:/challenge$ 
```
## learnings
- how to execute a program within a given directory
- use '.' to specify that we have to execute it in the directory in which we are present.
