# Matching with *
## code
```bash
Connected!                                                                        
This challenge resets your working directory to /home/hacker unless you change 
directory properly...
hacker@globbing~matching-with-:~$ cd /challenge
You specified the path to 'cd' to in more than 4 characters. Disallowed!
This challenge resets your working directory to /home/hacker unless you change 
directory properly...
hacker@globbing~matching-with-:~$ cd /c*
hacker@globbing~matching-with-:/challenge$ /challenge/run
You ran me with the working directory of /challenge! Here is your flag:
pwn.college{c-9CFtgT6xypncoS1NezudAAtdu.dFjM4QDL0kzN0czW}
hacker@globbing~matching-with-:/challenge$
```
## learnings
learnt to use * glob


# Matching with ?
## code
```bash
Connected!
This challenge resets your working directory to /home/hacker unless you change 
directory properly...
hacker@globbing~matching-with-:~$ cd /?ha??enge
hacker@globbing~matching-with-:/challenge$ /challenge/run
You ran me with the working directory of /challenge! Here is your flag:
pwn.college{AtL3E6j4YpLITOOUkOBCwmwvltN.dJjM4QDL0kzN0czW}
```
## learnings
learnt to use ? glob and how it maps only a single character


# matching with []
## code
```bash
Connected!
hacker@globbing~matching-with-:~$ cd /challenge/files
hacker@globbing~matching-with-:/challenge/files$ /challenge/run file_[absh]
You got it! Here is your flag!
pwn.college{wr4C6P43CJdCWBVX9gDh8qmG2t2.dNjM4QDL0kzN0czW}
hacker@globbing~matching-with-:/challenge/files$ 
```
## learnings
learnt how to match multiple characters using [] brackets


# matching paths with []
## code
```bash
hacker@globbing~matching-paths-with-:/$ cd /challenge/files
hacker@globbing~matching-paths-with-:/challenge/files$ ls -a
.       file_b  file_e  file_h  file_k  file_n  file_q  file_t  file_w  file_z
..      file_c  file_f  file_i  file_l  file_o  file_r  file_u  file_x
file_a  file_d  file_g  file_j  file_m  file_p  file_s  file_v  file_y
hacker@globbing~matching-paths-with-:/challenge/files$ /challenge/run file_[bash]
Error: please run with a working directory of /home/hacker!
hacker@globbing~matching-paths-with-:/challenge/files$ /challenge/run /challenge/files/file_[bash]
Error: please run with a working directory of /home/hacker!
hacker@globbing~matching-paths-with-:/challenge/files$ cd /home/hacker
hacker@globbing~matching-paths-with-:~$ /challenge/run /challenge/files/file_[bash]
You got it! Here is your flag!
pwn.college{cpvFiCH7gM19XhEnhQZ0KRhnDGN.dRjM4QDL0kzN0czW}
hacker@globbing~matching-paths-with-:~$ 
```
## learnings
learnt how to execute a a program in a directory using the absoulte path along with usage of [] brackets.


# mixing globs
## code
```bash
Connected!                                                                        
hacker@globbing~mixing-globs:~$ cd /challenge/files
hacker@globbing~mixing-globs:/challenge/files$ /challenge/run [cep]*
You got it! Here is your flag!
pwn.college{ot-s3j42YjrxCGWMXTxiRp7K9qh.dVjM4QDL0kzN0czW}
hacker@globbing~mixing-globs:/challenge/files$ 
```
## learnings
this one took me the longest for some peculiar reason. although extremely trivial, it made me understand as to how only the three words were the ones starting with letters 'c' , 'e' or 'p'.


# excluding globs
## code
```bash
hacker@globbing~exclusionary-globbing:~$ cd /challenge/files
hacker@globbing~exclusionary-globbing:/challenge/files$ /challenge/run file_[!pwn]
Error: your argument is too long! It must be 8 characters or less.
hacker@globbing~exclusionary-globbing:/challenge/files$ /challenge/run [!pwn]
Your expansion did not expand to the requested files (amazing beautiful 
challenging delightful educational fantastic great happy incredible jovial kind 
laughing magical optimistic queenly radiant splendid thrilling uplifting 
victorious xenial youthful zesty).
Instead, it expanded to:
[!pwn]
hacker@globbing~exclusionary-globbing:/challenge/files$ ls -a
.        beautiful    educational  happy       kind      nice        queenly   thrilling   wonderful  zesty
..       challenging  fantastic    incredible  laughing  optimistic  radiant   uplifting   xenial
amazing  delightful   great        jovial      magical   pwning      splendid  victorious  youthful
hacker@globbing~exclusionary-globbing:/challenge/files$ echo Look: file_[!pwn]
Look: file_[!pwn]
hacker@globbing~exclusionary-globbing:/challenge/files$ /chalenge/run f*_[!pwn]
ssh-entrypoint: /chalenge/run: No such file or directory
hacker@globbing~exclusionary-globbing:/challenge/files$ /challenge/run f*_[!pwn]
Error: your argument is too long! It must be 8 characters or less.
hacker@globbing~exclusionary-globbing:/challenge/files$ /challenge/run [!pwn]*
You got it! Here is your flag!
pwn.college{MGFVlaYvC9qKVR4L6WRp0_DFM5Z.dZjM4QDL0kzN0czW}
hacker@globbing~exclusionary-globbing:/challenge/files$ 
```
## learnings
was a bit tricky, had to figure out a way to pass the argument without using 'file_'
also had to keep in mind to put * after [!pwn]. 
