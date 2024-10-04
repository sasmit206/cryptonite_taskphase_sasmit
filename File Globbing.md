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
this one was a bit tricky.learnt how to execute a a program in a directory using the absoulte path along with usage of [] brackets.

# mixing globs
## code
```bash

```
## learnings
