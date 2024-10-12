# the PATH variable
## code
```bash
hacker@path~the-path-variable:~$ PATH=""
hacker@path~the-path-variable:~$ /challenge/run
Trying to remove /flag...
/challenge/run: line 4: rm: No such file or directory
The flag is still there! I might as well give it to you!
pwn.college{83HXMx_BMKoQ3P4vfi3AVzQweet.dZzNwUDL0kzN0czW}
hacker@path~the-path-variable:~$
```
# learnings
set PATH  to "" in order to avoid /challenge/run to access the rm command

#  setting PATH
## code
```bash
hacker@path~setting-path:~$ PATH="/challenge/more_commands/"
hacker@path~setting-path:~$ win
It looks like 'win' was improperly launched. Don't launch it directly; it MUST 
be launched by /challenge/run!
hacker@path~setting-path:~$ /challenge/run
Invoking 'win'....
Congratulations! You properly set the flag and 'win' has launched!
pwn.college{YXYq5mPXhSTOEBKcM07DaxndNZg.dVzNyUDL0kzN0czW}
```
## learnings
setting PATH to a particualr directory in order to run /challenge/run present inside /challenge/more_commands/

# Adding Commands
## code 
```bash
Connected!                                                                        
hacker@path~adding-commands:~$ pwd
/home/hacker
hacker@path~adding-commands:~$ nano /home/hacker/win
hacker@path~adding-commands:~$ ls-l win
ssh-entrypoint: ls-l: command not found
hacker@path~adding-commands:~$ ls -l win
-rwxr-xr-x 1 hacker hacker 17 Oct 12 04:53 win
hacker@path~adding-commands:~$ export PATH=/home/hacker:$PATH
hacker@path~adding-commands:~$ echo $PATH
/home/hacker:/run/challenge/bin:/run/workspace/bin:/usr/local/sbin:/usr/local/bin:/usr/sbin:/usr/bin:/sbin:/bin
hacker@path~adding-commands:~$ /home/hacker/win
/bin/cat: /flag: Permission denied
hacker@path~adding-commands:~$ /challenge/run
Invoking 'win'....
pwn.college{8nXAkEm2iztdq8rkpmIjIG1Gh9e.dZzNyUDL0kzN0czW}
hacker@path~adding-commands:~$ 
```
## learnings
extremely tricky.
learnt how to create my own shell, make it executable and finally invoke it. ALso learnt how to set The PATH to the address of the given directory.  


# Hijacking Commands
## code
```
hacker@path~hijacking-commands:~$ nano rm
hacker@path~hijacking-commands:~$ chmod +x rm
hacker@path~hijacking-commands:~$ export PATH=/home/hacker:$PATH
hacker@path~hijacking-commands:~$ /challenge/run
Trying to remove /flag...
Found 'rm' command at /home/hacker/rm. Executing!
rm is disabled
hacker@path~hijacking-commands:~$ ./win
/bin/cat: /flag: Permission denied
hacker@path~hijacking-commands:~$ nano rm
hacker@path~hijacking-commands:~$ /challenge/run
Trying to remove /flag...
Found 'rm' command at /home/hacker/rm. Executing!
pwn.college{8HQMeZshzCeBzsUZVAxA6oD5PYx.ddzNyUDL0kzN0czW}
rm is disabled
hacker@path~hijacking-commands:~$
```
## learnings
extremely intresting.
learnt the thought process of hijacking the rm command. Made my own command rm which overrode the default rm command as used chmod +x in order to make it executable. 
Also noticed that since win shell was not giving me the flag, instead passsed the argument of /bin/cat /flag (used absolute path of cat since PATH had to be set to a diffrent address) inside the new rm shell I had created.


