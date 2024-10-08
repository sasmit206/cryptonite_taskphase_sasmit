# listing processes
## code
```bash
hacker@processes~listing-processes:~$ ps aux
USER         PID %CPU %MEM    VSZ   RSS TTY      STAT START   TIME COMMAND
root           1  0.7  0.0   1056   640 ?        Ss   19:08   0:00 /sbin/docker-init -- /nix/var/nix/profiles/default/bin/dojo-init /run/dojo/bin/sleep 6h
root           7  0.0  0.0   5052  2240 ?        S    19:08   0:00 /run/dojo/bin/sleep 6h
root          68  0.0  0.0   4132  2560 ?        S    19:08   0:00 /challenge/3018-run-14541
root          72  0.0  0.0   2744  1600 ?        S    19:08   0:00 sleep 6h
hacker        73  0.6  0.0   5360  3840 pts/0    Ss   19:08   0:00 /run/dojo/bin/ssh-entrypoint
hacker        90  0.0  0.0   7868  3520 pts/0    R+   19:08   0:00 ps aux
hacker@processes~listing-processes:~$ /challenge/3018-run-14541
Yahaha, you found me! Here is your flag:
pwn.college{451CQpB5yvAW6vIlpNMbrNhQ4ji.dhzM4QDL0kzN0czW}
Now I will sleep for a while (so that you could find me with 'ps').
^[[200~/challenge/3018-run-14541^[[201~
```
## learnings
learnt how to use ps aux command and list running processes

# killing processes
## code
```bash
hacker@processes~killing-processes:~$ ps -e | grep sleep
     74 ?        00:00:00 sleep
hacker@processes~killing-processes:~$ kill 74
hacker@processes~killing-processes:~$ /challenge/run
Great job! Here is your payment:
pwn.college{oM-2r4IhkUQLNJ2x_lFNRS_VuVh.dJDN4QDL0kzN0czW}
hacker@processes~killing-processes:~$ 
```
## learnings
combined pre-known knowledge of pipe operator to find out of ps -e and passed it as input in order to grep for 'sleep'. Thus killed the process by identifying by its PID, Finally executed /challenge/run

# interuppting processes
## code
```bash
hacker@processes~interrupting-processes:~$ /challenge/run
I could give you the flag... but I won't, until this process exits. Remember, 
you can force me to exit with Ctrl-C. Try it now!
^C
Good job! You have used Ctrl-C to interrupt this process! Here is your flag:
pwn.college{Ua10ElWASxSFfCgjt3oKa4ATeb2.dNDN4QDL0kzN0czW}
```
## learnings
learnt how to interrupt a command

# suspending processes
## code
```bash
hacker@processes~suspending-processes:~$ /challenge/run
I'll only give you the flag if there's already another copy of me running in 
this terminal... Let's check!

UID          PID    PPID  C STIME TTY          TIME CMD
root          82      65  0 19:16 pts/0    00:00:00 bash /challenge/run
root          84      82  0 19:16 pts/0    00:00:00 ps -f

I don't see a second me!

To pass this level, you need to suspend me and launch me again! You can 
background me with Ctrl-Z or, if you're not ready to do that for whatever 
reason, just hit Enter and I'll exit!
^Z
[1]+  Stopped                 /challenge/run
hacker@processes~suspending-processes:~$ /challenge/run
I'll only give you the flag if there's already another copy of me running in 
this terminal... Let's check!

UID          PID    PPID  C STIME TTY          TIME CMD
root          82      65  0 19:16 pts/0    00:00:00 bash /challenge/run
root          89      65  0 19:16 pts/0    00:00:00 bash /challenge/run
root          91      89  0 19:16 pts/0    00:00:00 ps -f

Yay, I found another version of me! Here is the flag:
pwn.college{g25Wcxu1t59qnadjsJOC5Y0e4yM.dVDN4QDL0kzN0czW}
```
## learnings
leanrnt how to suspend a command; execute it's copy while the first one is suspended in the background

# resuming processes
## code
```bash
hacker@processes~resuming-processes:~$ /challenge/run
Let's practice resuming processes! Suspend me with Ctrl-Z, then resume me with 
the 'fg' command! Or just press Enter to quit me!
^Z
[1]+  Stopped                 /challenge/run
hacker@processes~resuming-processes:~$ fg
/challenge/run
I'm back! Here's your flag:
pwn.college{QbKxA1RfTnzgtit8pDbcxC2GWYh.dZDN4QDL0kzN0czW}
```
## learnings
learnt how to resume a command after having paused it with ctrl+z

# backgrounding processes
## code
```bash
hacker@processes~backgrounding-processes:~$ /challenge/run
I'll only give you the flag if there's already another copy of me running *and 
not suspended* in this terminal... Let's check!

UID          PID STAT CMD
root          82 S+   bash /challenge/run
root          84 R+   ps -o user=UID,pid,stat,cmd

I don't see a second me!

To pass this level, you need to suspend me, resume the suspended process in the 
background, and then launch a new version of me! You can background me with 
Ctrl-Z (and resume me in the background with 'bg') or, if you're not ready to 
do that for whatever reason, just hit Enter and I'll exit!
^Z
[1]+  Stopped                 /challenge/run
hacker@processes~backgrounding-processes:~$ bg
[1]+ /challenge/run &



hacker@processes~backgrounding-processes:~$ Yay, I'm now running the background! Because of that, this text will probably 
overlap weirdly with the shell prompt. Don't panic; just hit Enter a few times 
to scroll this text out.
/challenge/run
I'll only give you the flag if there's already another copy of me running *and 
not suspended* in this terminal... Let's check!

UID          PID STAT CMD
root          82 S    bash /challenge/run
root          92 S    sleep 6h
root          93 S+   bash /challenge/run
root          95 R+   ps -o user=UID,pid,stat,cmd

Yay, I found another version of me running in the background! Here is the flag:
pwn.college{wRIb-pwvD5X11VcyjaT-dQ6w8UN.ddDN4QDL0kzN0czW}
```
## learnings
learnt how to carry out execution of command in background while it's copy will also be executed

# foregrounding processes
## code
```bash
hacker@processes~foregrounding-processes:~$ /challenge/run
To pass this level, you need to suspend me, resume the suspended process in the 
background, and *then* foreground it without re-suspending it! You can 
background me with Ctrl-Z (and resume me in the background with 'bg') or, if 
you're not ready to do that for whatever reason, just hit Enter and I'll exit!
^Z
[1]+  Stopped                 /challenge/run
hacker@processes~foregrounding-processes:~$ bg
[1]+ /challenge/run &
hacker@processes~foregrounding-processes:~$ 


Yay, I'm now running the background! Because of that, this text will probably 
overlap weirdly with the shell prompt. Don't panic; just hit Enter a few times 
to scroll this text out. After that, resume me into the foreground with 'fg'; 
I'll wait.

hacker@processes~foregrounding-processes:~$ fg
/challenge/run
YES! Great job! I'm now running in the foreground. Hit Enter for your flag!

pwn.college{cHk37DYcrlW2lxVG7QIG-dK3k_q.dhDN4QDL0kzN0czW}
```
## learnings
learnt how to foreground a task after having once put it in the background

# starting backgrounded processes
## code
```bash
hacker@processes~starting-backgrounded-processes:~$ /challenge/run &
[1] 82



Yay, you started me in the background! Because of that, this text will probably 
overlap weirdly with the shell prompt, but you're used to that by now...

Anyways! Here is your flag!
pwn.college{A2w_Mrid5bz0DinJMEUkqzYQVW3.dlDN4QDL0kzN0czW}
[1]+  Done                    /challenge/run
```
## learnings
learnt how tostart of a process in background without having to pause it using ctrl+z

# process exit codes
## code
hacker@processes~process-exit-codes:~$ /challenge/get-code
Exiting with an error code!
hacker@processes~process-exit-codes:~$ echo $?
138
hacker@processes~process-exit-codes:~$ /challenge/submit-code 138
CORRECT! Here is your flag:
pwn.college{IEjmL6kh3ddKbx1uHazrLN_2TdI.dljN4UDL0kzN0czW}
## learnings
learnt how to fetch exit code after execution of a command in order to check it's functionality.
