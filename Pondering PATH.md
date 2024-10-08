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


