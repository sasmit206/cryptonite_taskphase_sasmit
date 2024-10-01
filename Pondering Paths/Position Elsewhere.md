# code
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

#learnings
to explore directories in the system
to execute the given program from a specified directory
learnt how to see the path from which the program was supposed to be executed,by the line "you are..."
