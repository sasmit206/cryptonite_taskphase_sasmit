# Redirecting Output
## code
```bash
hacker@piping~redirecting-output:~$ echo PWN > COLLEGE
Correct! You successfully redirected 'PWN' to the file 'COLLEGE'! Here is your 
flag:
pwn.college{ML5gLpfMmFLHjXQ5K6NlbJgp65s.dRjN1QDL0kzN0czW}
hacker@piping~redirecting-output:~$ 
```
## learnings
learnt to redirect outputs to a file

# Redirecting More Outputs
## code
```bash
hacker@piping~redirecting-more-output:~$ /challenge/run > myflag
[INFO] WELCOME! This challenge makes the following asks of you:
[INFO] - the challenge will check that output is redirected to a specific file path : myflag
[INFO] - the challenge will output a reward file if all the tests pass : /flag

[HYPE] ONWARDS TO GREATNESS!

[INFO] This challenge will perform a bunch of checks.
[INFO] If you pass these checks, you will receive the /flag file.

[TEST] You should have redirected my stdout to a file called myflag. Checking...

[PASS] The file at the other end of my stdout looks okay!
[PASS] Success! You have satisfied all execution requirements.
hacker@piping~redirecting-more-output:~$ cat myflag

[FLAG] Here is your flag:
[FLAG] pwn.college{0ZJvyR91g6O6y80BarmuS1r5B2I.dVjN1QDL0kzN0czW}

hacker@piping~redirecting-more-output:~$ 
```
## learning
learnt how to redirect output of /challenge/run to myflag.
then viewed contents of myflag using 'cat' command

# 
## code
```bash
hacker@piping~appending-output:~$ /challenge/run >> /home/hacker/the-flag
[INFO] WELCOME! This challenge makes the following asks of you:
[INFO] - the challenge will check that output is redirected to a specific file path : /home/hacker/the-flag

[HYPE] ONWARDS TO GREATNESS!

[INFO] This challenge will perform a bunch of checks.
[INFO] Good luck!

[TEST] You should have redirected my stdout to a file called /home/hacker/the-flag. Checking...

[HINT] File descriptors are inherited from the parent, unless the FD_CLOEXEC is set by the parent on the file descriptor.
[HINT] For security reasons, some programs, such as python, do this by default in certain cases. Be careful if you are
[HINT] creating and trying to pass in FDs in python.

[PASS] The file at the other end of my stdout looks okay!
[PASS] Success! You have satisfied all execution requirements.
I will write the flag in two parts to the file /home/hacker/the-flag! I'll do 
the first write directly to the file, and the second write, I'll do to stdout 
(if it's pointing at the file). If you redirect the output in append mode, the 
second write will append to (rather than overwrite) the first write, and you'll 
get the whole flag!
hacker@piping~appending-output:~$ cat myflag

[FLAG] Here is your flag:
[FLAG] pwn.college{0ZJvyR91g6O6y80BarmuS1r5B2I.dVjN1QDL0kzN0czW}

hacker@piping~appending-output:~$ cat the-flag
 | 
\|/ This is the first half:
 v 
pwn.college{M_BuyHgBD_1y1eFuvpmy7Pjo7Ti.ddDM5QDL0kzN0czW}
                              ^
     that is the second half /|\
                              |

If you only see the second half above, you redirected in *truncate* mode (>) 
rather than *append* mode (>>), and so the write of the second half to stdout 
overwrote the initial write of the first half directly to the file. Try append 
mode!
```
## learnings
learnt how to use '>>' append argument. 
was also tricked once by having displayed 'my-flag' instead of 'the-flag'

# redirecting errors
## code
```bash
hacker@piping~redirecting-errors:~$ /challenge/run >myflag 2>instructions
hacker@piping~redirecting-errors:~$ cat myflag

[FLAG] Here is your flag:
[FLAG] pwn.college{EmEDYvjHAsrgKiAmtIOoj3mZkSu.ddjN1QDL0kzN0czW}
```
## learnings
learnt how to redirect errors present in a given file 'instructions' and the flag in 'myflag'.
used 2> to redirect errors
and > to redirect output

# redirecting inputs
## code
```bash
Connected!                                                                        
hacker@piping~redirecting-input:~$ echo COLLEGE > PWN
hacker@piping~redirecting-input:~$ cat PWN
COLLEGE
hacker@piping~redirecting-input:~$ /challenge/run < PWN
Reading from standard input...
Correct! You have redirected the PWN file into my standard input, and I read 
the value 'COLLEGE' out of it!
Here is your flag:
pwn.college{E3dG4GEx9yy71TljqBlPYo2xwSS.dBzN1QDL0kzN0czW}
```
