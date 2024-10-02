# The Root
# code
```bash
Connected!
hacker@paths~the-root:~$ /pwn
BOOM!!!
Here is your flag:
pwn.college{4n2KC6qarpIG88AMpLxFk8s-KRr.dhzN5QDL0kzN0czW}
hacker@paths~the-root:~$ 
```

# learnings
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


