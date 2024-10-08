# chaining-with-semicolons
## code
```bash
hacker@chaining~chaining-with-semicolons:~$ /challenge/pwn; /challenge/college
Yes! You chained /challenge/pwn and /challenge/college! Here is your flag:
pwn.college{sz53BR43U7qMuqHzH4LCVdojoP1.dVTN4QDL0kzN0czW}
```
## learning
learnt how to execute mutiple commands in a single line

# our-first-shell-script
## code
```bash
hacker@chaining~your-first-shell-script:~$ bash x.sh
Great job, you've written your first shell script! Here is the flag:
pwn.college{Ep5r-0iL0JQQjNlpOFB3dJE1hex.dFzN4QDL0kzN0czW}
hacker@chaining~your-first-shell-script:~$ 
```

# redirecting-script-output
## code
```bash
hacker@chaining~redirecting-script-output:~$ nano x.sh
hacker@chaining~redirecting-script-output:~$ bash x.sh > /challenge/solve
No shenanigans with bash options yet, please! Just run your script with 'bash 
x.sh'.
ssh-entrypoint: /challenge/solve: Permission denied
hacker@chaining~redirecting-script-output:~$ bash x.sh | /challenge/solve
Correct! Here is your flag:
pwn.college{051KKRJZ1Brkvc88LYoHgvg_h4T.dhTM5QDL0kzN0czW}
```
## learning
learnt how to use pipe operator in order to feed the output of multiple programs present in a shell to a single program using pipe operator

# executable-shell-scripts
## code
```bash
hacker@chaining~executable-shell-scripts:~$ nano x.sh
hacker@chaining~executable-shell-scripts:~$ pwd
/home/hacker
hacker@chaining~executable-shell-scripts:~$ chmod u=rwx /challenge/solve
chmod: changing permissions of '/challenge/solve': Operation not permitted
hacker@chaining~executable-shell-scripts:~$ chmod u=rwx x.sh
hacker@chaining~executable-shell-scripts:~$ /x.sh
ssh-entrypoint: /x.sh: No such file or directory
hacker@chaining~executable-shell-scripts:~$ ./x.sh
Congratulations on your shell script execution! Your flag:
pwn.college{8n_dFuYtN8rg1Yy09SHHgebMsg4.dRzNyUDL0kzN0czW}
```
## learning
learnt how to invoke a shell without having to use bash by using chmod funtion in order to make it executable in the present directory

