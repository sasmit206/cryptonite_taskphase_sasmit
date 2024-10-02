# cat not the pet , command!
## code
```bash
hacker@commands~cat-not-the-pet-but-the-command:~$ cat flag
pwn.college{A4gumuSbeUW2nEzIGUDbf-lhNta.dFzN1QDL0kzN0czW}
hacker@commands~cat-not-the-pet-but-the-command:~$ 
## learnings
to view the contents of a file 'flag' present within home directory
```
# catting absolute paths 
## code
```bash
hacker@commands~catting-absolute-paths:~$ cat /flag
pwn.college{0HbCB46ac7lW8b6qRn06NYyfjLT.dlTM5QDL0kzN0czW}
hacker@commands~catting-absolute-paths:~$
```
## learnings
to list the contents a given file using cat command and its absoulte path

# more catting practice
## code
```bash
hacker@commands~more-catting-practice:~$ cat flag
cat: flag: No such file or directory
hacker@commands~more-catting-practice:~$ cat /lib/x86_64-linux-gnu/singular/flag
pwn.college{QiMPxcW_CGT7m3WRnyX1Gd088qR.dBjM5QDL0kzN0czW}
```
## learnings
to access the contents of a file using absolute paths in a different directory

# grepping for a needle in a haystack
## code
```bash
hacker@commands~grepping-for-a-needle-in-a-haystack:~$ grep pwn.college /challenge/data.txt
pwn.college{go5u2tMnq7Tdhi1xSNlPPZcN9F4.ddTM4QDL0kzN0czW}
## learnings
to search for a specified text in a given file using 'grep command
```
#listing files
## code
```bash
hacker@commands~listing-files:~$ ls /challenge
2275-renamed-run-4128  DESCRIPTION.md
hacker@commands~listing-files:~$ cat /challenge/2275-renamed-run-4128
#!/opt/pwn.college/bash

echo "Yahaha, you found me! Here is your flag:"
cat /flag
hacker@commands~listing-files:~$ cat /flag
cat: /flag: Permission denied
hacker@commands~listing-files:~$ ./cat /flag
ssh-entrypoint: ./cat: No such file or directory
hacker@commands~listing-files:~$ /challenge/2275-renamed-run-4128
Yahaha, you found me! Here is your flag:
pwn.college{MLe0fY7e0XuWouF2Qq5Q9CHNHTQ.dhjM4QDL0kzN0czW}
hacker@commands~listing-files:~$ 
```
## learnings
understood working of ls command

# touching files
## code
```bash
Connected!
hacker@commands~touching-files:~$ cd /tmp
hacker@commands~touching-files:/tmp$ ls
bin  hsperfdata_root  tmp.MiOQGWw5Zc
hacker@commands~touching-files:/tmp$ touch ./pwn
hacker@commands~touching-files:/tmp$ ls
bin  hsperfdata_root  pwn  tmp.MiOQGWw5Zc
hacker@commands~touching-files:/tmp$ touch ./college
hacker@commands~touching-files:/tmp$ ls
bin  college  hsperfdata_root  pwn  tmp.MiOQGWw5Zc
hacker@commands~touching-files:/tmp$ /challenge/run
Success! Here is your flag:
pwn.college{ciGEIkIJHtHv_9jApjQ5wwESCEQ.dBzM4QDL0kzN0czW}
hacker@commands~touching-files:/tmp$ 
```
## learnings
learnt how to create new files and view them in current directory

# removing files
## code 
```bash
Connected!
hacker@commands~removing-files:~$ ls
Desktop  delete_me  h
hacker@commands~removing-files:~$ rm delete_rm
rm: cannot remove 'delete_rm': No such file or directory
hacker@commands~removing-files:~$ rm delete_me
hacker@commands~removing-files:~$ ls
Desktop  h
hacker@commands~removing-files:~$ /challenge/check
Excellent removal. Here is your reward:
pwn.college{kHrIYzrssMfyq0ETP3RENjNjp2s.dZTOwUDL0kzN0czW}
hacker@commands~removing-files:~$
```
## learnings
learnt how to use rm command

# hidden files
## code
```bash
hacker@commands~hidden-files:~$ cd /
hacker@commands~hidden-files:/$ ls -a
.           .flag-2488128038067  challenge  home   lib64   mnt  proc  sbin  tmp
..          bin                  dev        lib    libx32  nix  root  srv   usr
.dockerenv  boot                 etc        lib32  media   opt  run   sys   var
hacker@commands~hidden-files:/$ cat .flag-2488128038067
pwn.college{Q9gaDLMiMkS5Z-fzDs4xSOW8ms0.dBTN4QDL0kzN0czW}
hacker@commands~hidden-files:/$ 
```
## learnings
learnt how to access hidden files. had made the mistake of not having speciefied directory before using ls-a command, but worked fine after using cd / command

# An Epic Filesystem Quest
## code
```bash
hacker@commands~an-epic-filesystem-quest:/opt/angr-management/_internal/jedi/third_party/django-stubs/django-stubs/contrib/auth$ exit
exit
Connection to dojo.pwn.college closed.
sasmit@Sasmits-MacBook-Air ~ % 
ssh -i ./key hacker@dojo.pwn.college
Connected!                                                                        
hacker@commands~an-epic-filesystem-quest:~$ cd /
hacker@commands~an-epic-filesystem-quest:/$ ls
TRACE  bin  boot  challenge  dev  etc  flag  home  lib  lib32  lib64  libx32  media  mnt  nix  opt  proc  root  run  sbin  srv  sys  tmp  usr  var
hacker@commands~an-epic-filesystem-quest:/$ cat TRACE
Tubular find!
The next clue is in: /opt/angr-management/_internal/jedi/third_party/django-stubs/django-stubs/contrib/auth/management
hacker@commands~an-epic-filesystem-quest:/$ /opt/angr-management/_internal/jedi/third_party/django-stubs/django-stubs/contrib/auth/management
ssh-entrypoint: /opt/angr-management/_internal/jedi/third_party/django-stubs/django-stubs/contrib/auth/management: Is a directory
hacker@commands~an-epic-filesystem-quest:/$ cd /opt/angr-management/_internal/jedi/third_party/django-stubs/django-stubs/contrib/auth/management
hacker@commands~an-epic-filesystem-quest:/opt/angr-management/_internal/jedi/third_party/django-stubs/django-stubs/contrib/auth/management$ ls
TIP  __init__.pyi  commands
hacker@commands~an-epic-filesystem-quest:/opt/angr-management/_internal/jedi/third_party/django-stubs/django-stubs/contrib/auth/management$ cat TIP
Great sleuthing!
The next clue is in: /usr/share/vim/vim81/pack/dist/opt

The next clue is **delayed** --- it will not become readable until you enter the directory with 'cd'.
hacker@commands~an-epic-filesystem-quest:/opt/angr-management/_internal/jedi/third_party/django-stubs/django-stubs/contrib/auth/management$ cd /usr/share/vim/vim81/pack/dist/opt
hacker@commands~an-epic-filesystem-quest:/usr/share/vim/vim81/pack/dist/opt$ ls
MEMO  cfilter  dvorak  editexisting  justify  matchit  shellmenu  swapmouse  termdebug
hacker@commands~an-epic-filesystem-quest:/usr/share/vim/vim81/pack/dist/opt$ cat MEMO
Lucky listing!
The next clue is in: /usr/local/lib/python3.8/dist-packages/pip/_vendor/pyproject_hooks/__pycache__

The next clue is **hidden** --- its filename starts with a '.' character. You'll need to look for it using special options to 'ls'.
hacker@commands~an-epic-filesystem-quest:/usr/share/vim/vim81/pack/dist/opt$ cd /usr/local/lib/python3.8/dist-packages/pip/_vendor/pyproject_hooks/__pycache__
hacker@commands~an-epic-filesystem-quest:/usr/local/lib/python3.8/dist-packages/pip/_vendor/pyproject_hooks/__pycache__$ ls
__init__.cpython-38.pyc  _compat.cpython-38.pyc  _impl.cpython-38.pyc
hacker@commands~an-epic-filesystem-quest:/usr/local/lib/python3.8/dist-packages/pip/_vendor/pyproject_hooks/__pycache__$ cd /usr/local/lib/python3.8/dist-packages/pip/_vendor/pyproject_hooks/__pycache__
hacker@commands~an-epic-filesystem-quest:/usr/local/lib/python3.8/dist-packages/pip/_vendor/pyproject_hooks/__pycache__$ ls
__init__.cpython-38.pyc  _compat.cpython-38.pyc  _impl.cpython-38.pyc
hacker@commands~an-epic-filesystem-quest:/usr/local/lib/python3.8/dist-packages/pip/_vendor/pyproject_hooks/__pycache__$ ls -a
.  ..  .DISPATCH  __init__.cpython-38.pyc  _compat.cpython-38.pyc  _impl.cpython-38.pyc
hacker@commands~an-epic-filesystem-quest:/usr/local/lib/python3.8/dist-packages/pip/_vendor/pyproject_hooks/__pycache__$ cat .DISPATCH
Yahaha, you found me!
The next clue is in: /opt/linux/linux-5.4/arch/mips/loongson64/common/cs5536

Watch out! The next clue is **trapped**. You'll need to read it out without 'cd'ing into the directory; otherwise, the clue will self destruct!
hacker@commands~an-epic-filesystem-quest:/usr/local/lib/python3.8/dist-packages/pip/_vendor/pyproject_hooks/__pycache__$ /opt/linux/linux-5.4/arch/mips/loongson64/common/cs5536/ls
ssh-entrypoint: /opt/linux/linux-5.4/arch/mips/loongson64/common/cs5536/ls: No such file or directory
hacker@commands~an-epic-filesystem-quest:/usr/local/lib/python3.8/dist-packages/pip/_vendor/pyproject_hooks/__pycache__$ /opt/linux/linux-5.4/arch/mips/loongson64/common/cs5536
ssh-entrypoint: /opt/linux/linux-5.4/arch/mips/loongson64/common/cs5536: Is a directory
hacker@commands~an-epic-filesystem-quest:/usr/local/lib/python3.8/dist-packages/pip/_vendor/pyproject_hooks/__pycache__$ cat /opt/linux/linux-5.4/arch/mips/loongson64/common/cs5536
cat: /opt/linux/linux-5.4/arch/mips/loongson64/common/cs5536: Is a directory
hacker@commands~an-epic-filesystem-quest:/usr/local/lib/python3.8/dist-packages/pip/_vendor/pyproject_hooks/__pycache__$ ls /opt/linux/linux-5.4/arch/mips/loongson64/common/cs5536
Makefile  POINTER-TRAPPED  cs5536_acc.c  cs5536_ehci.c  cs5536_ide.c  cs5536_isa.c  cs5536_mfgpt.c  cs5536_ohci.c  cs5536_pci.c
hacker@commands~an-epic-filesystem-quest:/usr/local/lib/python3.8/dist-packages/pip/_vendor/pyproject_hooks/__pycache__$ ls POINTER-TRAPPED
ls: cannot access 'POINTER-TRAPPED': No such file or directory
hacker@commands~an-epic-filesystem-quest:/usr/local/lib/python3.8/dist-packages/pip/_vendor/pyproject_hooks/__pycache__$ cat POINTER-TRAPPED
cat: POINTER-TRAPPED: No such file or directory
hacker@commands~an-epic-filesystem-quest:/usr/local/lib/python3.8/dist-packages/pip/_vendor/pyproject_hooks/__pycache__$ ls /opt/linux/linux-5.4/arch/mips/loongson64/common/cs5536/POINTER-TRAPPED
/opt/linux/linux-5.4/arch/mips/loongson64/common/cs5536/POINTER-TRAPPED
hacker@commands~an-epic-filesystem-quest:/usr/local/lib/python3.8/dist-packages/pip/_vendor/pyproject_hooks/__pycache__$ cat /opt/linux/linux-5.4/arch/mips/loongson64/common/cs5536/POINTER-TRAPPED
Tubular find!
The next clue is in: /usr/share/javascript/mathjax/jax/output/HTML-CSS/fonts/Neo-Euler/Size5/Regular

The next clue is **hidden** --- its filename starts with a '.' character. You'll need to look for it using special options to 'ls'.
hacker@commands~an-epic-filesystem-quest:/usr/local/lib/python3.8/dist-packages/pip/_vendor/pyproject_hooks/__pycache__$ ls /usr/share/javascript/mathjax/jax/output/HTML-CSS/fonts/Neo-Euler/Size5/Regular
Main.js
hacker@commands~an-epic-filesystem-quest:/usr/local/lib/python3.8/dist-packages/pip/_vendor/pyproject_hooks/__pycache__$ ls -a /usr/share/javascript/mathjax/jax/output/HTML-CSS/fonts/Neo-Euler/Size5/Regular
.  ..  .BLUEPRINT  Main.js
hacker@commands~an-epic-filesystem-quest:/usr/local/lib/python3.8/dist-packages/pip/_vendor/pyproject_hooks/__pycache__$ ls -a /usr/share/javascript/mathjax/jax/output/HTML-CSS/fonts/Neo-Euler/Size5/Regular/.BLUEPRINT
/usr/share/javascript/mathjax/jax/output/HTML-CSS/fonts/Neo-Euler/Size5/Regular/.BLUEPRINT
hacker@commands~an-epic-filesystem-quest:/usr/local/lib/python3.8/dist-packages/pip/_vendor/pyproject_hooks/__pycache__$ cd /usr/share/javascript/mathjax/jax/output/HTML-CSS/fonts/Neo-Euler/Size5/Regular
hacker@commands~an-epic-filesystem-quest:/usr/share/javascript/mathjax/jax/output/HTML-CSS/fonts/Neo-Euler/Size5/Regular$ ls -a
.  ..  .BLUEPRINT  Main.js
hacker@commands~an-epic-filesystem-quest:/usr/share/javascript/mathjax/jax/output/HTML-CSS/fonts/Neo-Euler/Size5/Regular$ cat .BLUEPRINT
Lucky listing!
The next clue is in: /opt/linux/linux-5.4/drivers/gpu/drm/radeon/reg_srcs

Watch out! The next clue is **trapped**. You'll need to read it out without 'cd'ing into the directory; otherwise, the clue will self destruct!
hacker@commands~an-epic-filesystem-quest:/usr/share/javascript/mathjax/jax/output/HTML-CSS/fonts/Neo-Euler/Size5/Regular$ ls /opt/linux/linux-5.4/drivers/gpu/drm/radeon/reg_srcs
SECRET-TRAPPED  cayman  evergreen  r100  r200  r300  r420  r600  rn50  rs600  rv515
hacker@commands~an-epic-filesystem-quest:/usr/share/javascript/mathjax/jax/output/HTML-CSS/fonts/Neo-Euler/Size5/Regular$ ls /opt/linux/linux-5.4/drivers/gpu/drm/radeon/reg_srcs/SELECT-TRAPPED
ls: cannot access '/opt/linux/linux-5.4/drivers/gpu/drm/radeon/reg_srcs/SELECT-TRAPPED': No such file or directory
hacker@commands~an-epic-filesystem-quest:/usr/share/javascript/mathjax/jax/output/HTML-CSS/fonts/Neo-Euler/Size5/Regular$ cat /opt/linux/linux-5.4/drivers/gpu/drm/radeon/reg_srcs/SECRET TRAPPED
cat: /opt/linux/linux-5.4/drivers/gpu/drm/radeon/reg_srcs/SECRET: No such file or directory
cat: TRAPPED: No such file or directory
hacker@commands~an-epic-filesystem-quest:/usr/share/javascript/mathjax/jax/output/HTML-CSS/fonts/Neo-Euler/Size5/Regular$ /opt/linux/linux-5.4/drivers/gpu/drm/radeon/reg_srcs/SECRET-TRAPPED
ssh-entrypoint: /opt/linux/linux-5.4/drivers/gpu/drm/radeon/reg_srcs/SECRET-TRAPPED: Permission denied
hacker@commands~an-epic-filesystem-quest:/usr/share/javascript/mathjax/jax/output/HTML-CSS/fonts/Neo-Euler/Size5/Regular$ cat /opt/linux/linux-5.4/drivers/gpu/drm/radeon/reg_srcs/SECRET-TRAPPED
Yahaha, you found me!
The next clue is in: /opt/angr-management/_internal/jedi/third_party/django-stubs/django-stubs/contrib/contenttypes

Watch out! The next clue is **trapped**. You'll need to read it out without 'cd'ing into the directory; otherwise, the clue will self destruct!
hacker@commands~an-epic-filesystem-quest:/usr/share/javascript/mathjax/jax/output/HTML-CSS/fonts/Neo-Euler/Size5/Regular$ ls /opt/angr-management/_internal/jedi/third_party/django-stubs/django-stubs/contrib/contenttypes
NOTE-TRAPPED  __init__.pyi  admin.pyi  apps.pyi  checks.pyi  fields.pyi  forms.pyi  management  models.pyi  views.pyi
hacker@commands~an-epic-filesystem-quest:/usr/share/javascript/mathjax/jax/output/HTML-CSS/fonts/Neo-Euler/Size5/Regular$ cat /opt/angr-management/_internal/jedi/third_party/django-stubs/django-stubs/contrib/contenttypes/NOTE-TRAPPED
Congratulations, you found the clue!
The next clue is in: /usr/share/perl/5.30.0/unicore/lib/CWKCF

The next clue is **hidden** --- its filename starts with a '.' character. You'll need to look for it using special options to 'ls'.
hacker@commands~an-epic-filesystem-quest:/usr/share/javascript/mathjax/jax/output/HTML-CSS/fonts/Neo-Euler/Size5/Regular$ ls /usr/share/perl/5.30.0/unicore/lib/CWKCF
Y.pl
hacker@commands~an-epic-filesystem-quest:/usr/share/javascript/mathjax/jax/output/HTML-CSS/fonts/Neo-Euler/Size5/Regular$ ls -a /usr/share/perl/5.30.0/unicore/lib/CWKCF
.  ..  .SNIPPET  Y.pl
hacker@commands~an-epic-filesystem-quest:/usr/share/javascript/mathjax/jax/output/HTML-CSS/fonts/Neo-Euler/Size5/Regular$ cat /usr/share/perl/5.30.0/unicore/lib/CWKCF/.SNIPPET
CONGRATULATIONS! Your perserverence has paid off, and you have found the flag!
It is: pwn.college{Y7sGllUT6pu8UYb3w-Vetzn0blY.dljM4QDL0kzN0czW}
hacker@commands~an-epic-filesystem-quest:/usr/share/javascript/mathjax/jax/output/HTML-CSS/fonts/Neo-Euler/Size5/Regular$ 
```

## learnings:
a bit tricky, but I learnt how to access files using their absoulte paths without using cd command.
Learnt proper application of ls -a command

# making directories
## code
``` bash
Connected!                                                                        
hacker@commands~making-directories:~$ cd /
hacker@commands~making-directories:/$ ls
bin  boot  challenge  dev  etc  flag  home  lib  lib32  lib64  libx32  media  mnt  nix  opt  proc  root  run  sbin  srv  sys  tmp  usr  var
hacker@commands~making-directories:/$ cd /tmp
hacker@commands~making-directories:/tmp$ ls
bin  hsperfdata_root  tmp.MiOQGWw5Zc
hacker@commands~making-directories:/tmp$ mkdir pwn
hacker@commands~making-directories:/tmp$ ls
bin  hsperfdata_root  pwn  tmp.MiOQGWw5Zc
hacker@commands~making-directories:/tmp$ cd /tmp/pwn
hacker@commands~making-directories:/tmp/pwn$ touch college
hacker@commands~making-directories:/tmp/pwn$ /challenge/run
Success! Here is your flag:
pwn.college{Ypwhf3ezngZqSt0fmuu_hH1CEvo.dFzM4QDL0kzN0czW}
hacker@commands~making-directories:/tmp/pwn$ 
```
## learnings
learnt to use mkdir command

# finding files
## code
```bash
Connected!                                                                        
hacker@commands~finding-files:~$ ls
Desktop  h
hacker@commands~finding-files:~$ ls -a
.  ..  .ICEauthority  .bash_history  .bash_logout  .bashrc  .cache  .config  .dbus  .local  .profile  Desktop  h
hacker@commands~finding-files:~$ find / -flag
find: unknown predicate `-flag'
hacker@commands~finding-files:~$ find / -name flag
find: ‘/tmp/tmp.MiOQGWw5Zc’: Permission denied
find: ‘/etc/ssl/private’: Permission denied
/usr/lib/python3/dist-packages/sage/libs/coxeter3/flag
/usr/local/lib/python3.8/dist-packages/pwnlib/flag
/usr/local/share/radare2/5.9.5/flag
find: ‘/var/cache/apt/archives/partial’: Permission denied
find: ‘/var/cache/ldconfig’: Permission denied
find: ‘/var/cache/private’: Permission denied
find: ‘/var/lib/apt/lists/partial’: Permission denied
find: ‘/var/lib/mysql-files’: Permission denied
find: ‘/var/lib/private’: Permission denied
find: ‘/var/lib/mysql’: Permission denied
find: ‘/var/lib/mysql-keyring’: Permission denied
find: ‘/var/lib/php/sessions’: Permission denied
find: ‘/var/log/private’: Permission denied
find: ‘/var/log/apache2’: Permission denied
find: ‘/var/log/mysql’: Permission denied
find: ‘/run/mysqld’: Permission denied
find: ‘/run/sudo’: Permission denied
find: ‘/root’: Permission denied
/opt/pwndbg/.venv/lib/python3.8/site-packages/pwnlib/flag
/opt/radare2/libr/flag
find: ‘/proc/tty/driver’: Permission denied
find: ‘/proc/1/task/1/fd’: Permission denied
find: ‘/proc/1/task/1/fdinfo’: Permission denied
find: ‘/proc/1/task/1/ns’: Permission denied
find: ‘/proc/1/fd’: Permission denied
find: ‘/proc/1/map_files’: Permission denied
find: ‘/proc/1/fdinfo’: Permission denied
find: ‘/proc/1/ns’: Permission denied
find: ‘/proc/7/task/7/fd’: Permission denied
find: ‘/proc/7/task/7/fdinfo’: Permission denied
find: ‘/proc/7/task/7/ns’: Permission denied
find: ‘/proc/7/fd’: Permission denied
find: ‘/proc/7/map_files’: Permission denied
find: ‘/proc/7/fdinfo’: Permission denied
find: ‘/proc/7/ns’: Permission denied
/nix/store/1yagn5s8sf7kcs2hkccgf8d0wxlrv5sz-radare2-5.9.0/share/radare2/5.9.0/flag
/nix/store/pmvk2bk4p550w182rjfm529kfqddnvh3-python3.11-pwntools-4.12.0/lib/python3.11/site-packages/pwnlib/flag
hacker@commands~finding-files:~$ cat /nix/store/pmvk2bk4p550w182rjfm529kfqddnvh3-python3.11-pwntools-4.12.0/lib/python3.11/site-packages/pwnlib/flag
cat: /nix/store/pmvk2bk4p550w182rjfm529kfqddnvh3-python3.11-pwntools-4.12.0/lib/python3.11/site-packages/pwnlib/flag: Is a directory
hacker@commands~finding-files:~$ ls /usr/lib/python3/dist-packages/sage/libs/coxeter3/flag
/usr/lib/python3/dist-packages/sage/libs/coxeter3/flag
hacker@commands~finding-files:~$ cat /usr/lib/python3/dist-packages/sage/libs/coxeter3/flag
pwn.college{cfOR_K_ONk8Tc5T7ltYtqgz2Y7C.dJzM4QDL0kzN0czW}hacker@commands~finding-files:~$ 
```
## learnings
first, used find command to search for files with the name 'flag' in the enitre direcotry
then, used cat to check the contents of directories to which permission was allowed and thus got the key

# linking files
## code
```bash
hacker@commands~linking-files:/$ cd / 
hacker@commands~linking-files:/$ find -name flag
find: ‘./tmp/tmp.MiOQGWw5Zc’: Permission denied
find: ‘./etc/ssl/private’: Permission denied
./usr/local/lib/python3.8/dist-packages/pwnlib/flag
./usr/local/share/radare2/5.9.5/flag
find: ‘./var/cache/apt/archives/partial’: Permission denied
find: ‘./var/cache/ldconfig’: Permission denied
find: ‘./var/cache/private’: Permission denied
find: ‘./var/lib/apt/lists/partial’: Permission denied
find: ‘./var/lib/mysql-files’: Permission denied
find: ‘./var/lib/private’: Permission denied
find: ‘./var/lib/mysql’: Permission denied
find: ‘./var/lib/mysql-keyring’: Permission denied
find: ‘./var/lib/php/sessions’: Permission denied
find: ‘./var/log/private’: Permission denied
find: ‘./var/log/apache2’: Permission denied
find: ‘./var/log/mysql’: Permission denied
find: ‘./run/mysqld’: Permission denied
find: ‘./run/sudo’: Permission denied
find: ‘./root’: Permission denied
./opt/pwndbg/.venv/lib/python3.8/site-packages/pwnlib/flag
./opt/radare2/libr/flag
find: ‘./proc/tty/driver’: Permission denied
find: ‘./proc/1/task/1/fd’: Permission denied
find: ‘./proc/1/task/1/fdinfo’: Permission denied
find: ‘./proc/1/task/1/ns’: Permission denied
find: ‘./proc/1/fd’: Permission denied
find: ‘./proc/1/map_files’: Permission denied
find: ‘./proc/1/fdinfo’: Permission denied
find: ‘./proc/1/ns’: Permission denied
find: ‘./proc/7/task/7/fd’: Permission denied
find: ‘./proc/7/task/7/fdinfo’: Permission denied
find: ‘./proc/7/task/7/ns’: Permission denied
find: ‘./proc/7/fd’: Permission denied
find: ‘./proc/7/map_files’: Permission denied
find: ‘./proc/7/fdinfo’: Permission denied
find: ‘./proc/7/ns’: Permission denied
./flag
./nix/store/1yagn5s8sf7kcs2hkccgf8d0wxlrv5sz-radare2-5.9.0/share/radare2/5.9.0/flag
./nix/store/pmvk2bk4p550w182rjfm529kfqddnvh3-python3.11-pwntools-4.12.0/lib/python3.11/site-packages/pwnlib/flag
hacker@commands~linking-files:/$ file ./usr/local/lib/python3.8/dist-packages/pwnlib/flag
./usr/local/lib/python3.8/dist-packages/pwnlib/flag: setgid, directory
hacker@commands~linking-files:/$ file ./usr/local/share/radare2/5.9.5/flag
./usr/local/share/radare2/5.9.5/flag: directory
hacker@commands~linking-files:/$ ln -s /flag /home/hacker/not-the-flag
hacker@commands~linking-files:/$ /challenge/catflag
About to read out the /home/hacker/not-the-flag file!
pwn.college{wwvsTroinvLWZ9r08a6rNLtpTWv.dlTM1UDL0kzN0czW}
hacker@commands~linking-files:/$ 
```
## learnings
this one was pretty intresting. i first thought of a way to maybe locate the places where /flag was present by using find function .
However, I later realised that ln -s could be simply used to establish a symbolic link of /home/hacker/not-the-flag to /flag. this was done as upon entering /challenge/catflag, /home/hacker/not-the-flag was being read out.




