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


# 
Correct! You have redirected the PWN file into my standard input, and I read 
the value 'COLLEGE' out of it!
Here is your flag:
pwn.college{E3dG4GEx9yy71TljqBlPYo2xwSS.dBzN1QDL0kzN0czW}
```

# grepping stored output
## code
```bash
hacker@piping~grepping-stored-results:~$ /challenge/run > /tmp/data.txt
[INFO] WELCOME! This challenge makes the following asks of you:
[INFO] - the challenge will check that output is redirected to a specific file path : /tmp/data.txt
[INFO] - the challenge will output a reward file if all the tests pass : /challenge/.data.txt

[HYPE] ONWARDS TO GREATNESS!

[INFO] This challenge will perform a bunch of checks.
[INFO] If you pass these checks, you will receive the /challenge/.data.txt file.

[TEST] You should have redirected my stdout to a file called /tmp/data.txt. Checking...

[HINT] File descriptors are inherited from the parent, unless the FD_CLOEXEC is set by the parent on the file descriptor.
[HINT] For security reasons, some programs, such as python, do this by default in certain cases. Be careful if you are
[HINT] creating and trying to pass in FDs in python.

[PASS] The file at the other end of my stdout looks okay!
[PASS] Success! You have satisfied all execution requirements.
hacker@piping~grepping-stored-results:~$ grep "flag" /tmp/data.txt
[FLAG] Here is your flag:
flagstones
flags
flagellates
flagellated
flag's
unflagging
flagpole
camouflaging
flagstaff's
flagship
flagon
camouflaged
flagellation
flagpole's
flagons
flagellum
conflagration's
flagellum's
flagella
flagstone's
flagellate
flagship's
camouflages
flagstaffs
flag
flagrantly
camouflage
persiflage
flagellums
conflagration
flagellation's
conflagrations
flagships
flagrant
flagellating
flagstone
flagging
flagon's
persiflage's
flagpoles
camouflage's
flagged
flagstaff
hacker@piping~grepping-stored-results:~$ grep "{}" /tmp/data.txt
hacker@piping~grepping-stored-results:~$ grep "*{*}*" /tmp/data.txt
hacker@piping~grepping-stored-results:~$ grep "pwn.college" /tmp/data.txt
pwn.college{g_-YRz7iNMyaEtNLUbDMiJhmM9W.dhTM4QDL0kzN0czW}
hacker@piping~grepping-stored-results:~$
```
## learnings
a bit twisted, the art of redrecting the output was pretty trivial. The only trick was to grep using the correct manner as grepping for the work "flag" simply returned words having flag in them and not the flag itself. thus used pwn.college to locate the flag as the key is returned in the format of pwn.college{_}

# grepping live output
## code
```
hacker@piping~grepping-live-output:~$ echo /challenge/run | grep "pwn.college"
hacker@piping~grepping-live-output:~$  /challenge/run | grep "pwn.college"
[INFO] WELCOME! This challenge makes the following asks of you:
[INFO] - the challenge checks for a specific process at the other end of stdout : grep
[INFO] - the challenge will output a reward file if all the tests pass : /challenge/.data.txt

[HYPE] ONWARDS TO GREATNESS!

[INFO] This challenge will perform a bunch of checks.
[INFO] If you pass these checks, you will receive the /challenge/.data.txt file.

[TEST] You should have redirected my stdout to another process. Checking...
[TEST] Performing checks on that process!

[INFO] The process' executable is /nix/store/xpq4yhadyhazkcsggmqd7rsgvxb3kjy4-gnugrep-3.11/bin/grep.
[INFO] This might be different than expected because of symbolic links (for example, from /usr/bin/python to /usr/bin/python3 to /usr/bin/python3.8).
[INFO] To pass the checks, the executable must be grep.

[PASS] You have passed the checks on the process on the other end of my stdout!
[PASS] Success! You have satisfied all execution requirements.
pwn.college{IaXlGhNvspAOYUorTPzRi6GLxIy.dlTM4QDL0kzN0czW}
```
## learning
learnt usage of pipe operator. the statements in the left are executed and fed as inputs to the statements in the right side of | operator


# grepping errors
## code 
```bash
hacker@piping~grepping-errors:~$ /challenge/run 2>& 1 txt
[INFO] WELCOME! This challenge makes the following asks of you:
[INFO] - the challenge checks for a specific process at the other end of stderr : grep
[INFO] - the challenge will output a reward file if all the tests pass : /challenge/.data.txt

[HYPE] ONWARDS TO GREATNESS!

[INFO] This challenge will perform a bunch of checks.
[INFO] If you pass these checks, you will receive the /challenge/.data.txt file.

[TEST] You should have redirected my stderr to another process. Checking...

[FAIL] You did not satisfy all the execution requirements.
[FAIL] Specifically, you must fix the following issue:
[FAIL]   stderr of this process does not appear to be a pipe!
hacker@piping~grepping-errors:~$ /challenge/run 2>& 1 | grep "pwn.college"
[INFO] WELCOME! This challenge makes the following asks of you:
[INFO] - the challenge checks for a specific process at the other end of stderr : grep
[INFO] - the challenge will output a reward file if all the tests pass : /challenge/.data.txt

[HYPE] ONWARDS TO GREATNESS!

[INFO] This challenge will perform a bunch of checks.
[INFO] If you pass these checks, you will receive the /challenge/.data.txt file.

[TEST] You should have redirected my stderr to another process. Checking...
[TEST] Performing checks on that process!

[INFO] The process' executable is /nix/store/xpq4yhadyhazkcsggmqd7rsgvxb3kjy4-gnugrep-3.11/bin/grep.
[INFO] This might be different than expected because of symbolic links (for example, from /usr/bin/python to /usr/bin/python3 to /usr/bin/python3.8).
[INFO] To pass the checks, the executable must be grep.

[PASS] You have passed the checks on the process on the other end of my stderr!
[PASS] Success! You have satisfied all execution requirements.
pwn.college{0jo5XAP4Ae1cCgIfFVvDTsPZvdX.dVDM5QDL0kzN0czW}
```
## learning
learnt how to combine the stderr file as well before using the '|' operator. used 2>&1 to combine botht the standard output and error file and grepped thorugh it by finally passing the combined file thorugh | operator as a whole

# duplicating data with tee
## code
```bash
hacker@piping~duplicating-piped-data-with-tee:~$ /challenge/pwn | tee cm1_o | /challenge/college
Processing...
The input to 'college' does not contain the correct secret code! This code 
should be provided by the 'pwn' command. HINT: use 'tee' to intercept the 
output of 'pwn' and figure out what the code needs to be.
hacker@piping~duplicating-piped-data-with-tee:~$ cat cm1_o
Usage: /challenge/pwn --secret [SECRET_ARG]

SECRET_ARG should be "4tmPW-Ef"
hacker@piping~duplicating-piped-data-with-tee:~$ /challenge/pwn --4tmPW-Ef | /challenge/college
Processing...
The input to 'college' does not contain the correct secret code! This code 
should be provided by the 'pwn' command. HINT: use 'tee' to intercept the 
output of 'pwn' and figure out what the code needs to be.
hacker@piping~duplicating-piped-data-with-tee:~$ /challenge/pwn --4tmPW-Ef
Processing...
You must pipe the output of /challenge/pwn into /challenge/college (or 'tee' 
for debugging).
hacker@piping~duplicating-piped-data-with-tee:~$ /challenge/pwn --secret [4tmPW-Ef] | /challenge/college
Processing...
The input to 'college' does not contain the correct secret code! This code 
should be provided by the 'pwn' command. HINT: use 'tee' to intercept the 
output of 'pwn' and figure out what the code needs to be.
hacker@piping~duplicating-piped-data-with-tee:~$ /challenge/pwn --secret 4tmPW-Ef | /challenge/college
Processing...
Correct! Passing secret value to /challenge/college...
Great job! Here is your flag:
pwn.college{4tmPW-Ef6r1LcGX3FjfQX3RGo9k.dFjM5QDL0kzN0czW}
hacker@piping~duplicating-piped-data-with-tee:~$ 
```
## learning
learnt how to debug the console using tee operator. its essentialfunction is to list the reason as to why the piping of first command into the second one is non executable and stroing it in cm1_o. listed contents of cm1_o to find the secret argument to be passed

# writing to multiple programs
## code
```bash
hacker@piping~writing-to-multiple-programs:~$ /challenge/hack | tee (/challenge/th)e |  /challenge/planet
ssh-entrypoint: syntax error near unexpected token `/challenge/th'
hacker@piping~writing-to-multiple-programs:~$ /challenge/hack | tee (/challenge/the) |  /challenge/planet
ssh-entrypoint: syntax error near unexpected token `/challenge/the'
hacker@piping~writing-to-multiple-programs:~$ /challenge/hack | tee >(/challenge/the) |  /challenge/planet
Congratulations, you have duplicated data into the input of two programs! Here 
is your flag:
pwn.college{ETlLBfh1tuOXvXxUHzGbj10WGib.dBDO0UDL0kzN0czW}
hacker@piping~writing-to-multiple-programs:~$
```
## learning
how to pass output of a file as an input to another file using >() 

# split piping stderr and stdout
## code
```bash
hacker@piping~split-piping-stderr-and-stdout:~$ /challenge/hack > >(/challenge/planet) 2> >(/challenge/the)
Congratulations, you have learned a redirection technique that even experts 
struggle with! Here is your flag:
pwn.college{A16ghxbL5DyNEwTYCZdMoaZlygU.dFDNwYDL0kzN0czW}
hacker@piping~split-piping-stderr-and-stdout:~$ 
```
## learning
passed the output of /challenge/hack as the input to /challlenge/planet. Further, passed the stderr (ie errors) of /challenge/hack into the /challenge/the file.

