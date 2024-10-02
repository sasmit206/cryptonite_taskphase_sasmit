# learning from documentation 
## code 
```bash
hacker@man~learning-from-documentation:~$ cat not-the-flag
cat: not-the-flag: Permission denied
hacker@man~learning-from-documentation:~$ /challenge/challenge --giveflag
Correct argument! Here is your flag:
pwn.college{4oerEKcmhJla1oT8-fgceBmq7kz.dRjM5QDL0kzN0czW}
hacker@man~learning-from-documentation:~$ 
```
## learnings
learnt to pass arguments 

# learning complex usage
## code
```bash
hacker@man~learning-complex-usage:/$ /challenge/challenge --printfile /not-the-flag
Correct argument! Here is the /not-the-flag file:
cat: /not-the-flag: No such file or directory
hacker@man~learning-complex-usage:/$ /challenge/challenge --printfile /flag
Correct argument! Here is the /flag file:
pwn.college{cnXTNkGik3NxEKPVOEsfaPaLcUK.dVjM5QDL0kzN0czW}
hacker@man~learning-complex-usage:/$ 
```
## learning
lernt to access the flag after passing an argyment to an argument of a command

# reading manuals
## code
```bash
hacker@man~reading-manuals:~$ man challenge

CHALLENGE(1)                                                                 Challenge Commands                                                                CHALLENGE(1)

NAME
       /challenge/challenge - print the flag!

SYNOPSIS
       challenge OPTION

DESCRIPTION
       Output the flag when called with the right arguments.

       --fortune
              read a fortune

       --version
              output version information and exit

       --tkvuld NUM
              print the flag if NUM is 624

AUTHOR
       Written by Zardus.
hacker@man~reading-manuals:~$ /challenge/challenge --fortune
A scientific truth does not triumph by convincing its opponents and
making them see the light, but rather because its opponents eventually
die and a new generation grows up that is familiar with it.
		-- Max Planck
hacker@man~reading-manuals:~$ /challenge/challenge --tkvuld
Incorrect usage! Please read the challenge man page!
hacker@man~reading-manuals:~$ /challenge/challenge --version
I'm exactly the version I need to be!
hacker@man~reading-manuals:~$ /challenge/challenge --tkvuld 624
Correct usage! Your flag: pwn.college{E_I6_t_24k0vX5uQYU02N9X1lRR.dRTM4QDL0kzN0czW}
hacker@man~reading-manuals:~$
```
## learnings
learnt how to read manuals

# searching manuals
## code
```bash
hacker@man~searching-manuals:~$ man command
No manual entry for command
hacker@man~searching-manuals:~$ man challenge
hacker@man~searching-manuals:~$ /challenge/ -m
ssh-entrypoint: /challenge/: Is a directory
hacker@man~searching-manuals:~$ man challenge
hacker@man~searching-manuals:~$ /challenge/-m
ssh-entrypoint: /challenge/-m: No such file or directory
hacker@man~searching-manuals:~$ /challlenge/challenge -m
ssh-entrypoint: /challlenge/challenge: No such file or directory
hacker@man~searching-manuals:~$ man command
No manual entry for command
hacker@man~searching-manuals:~$ man challenge
hacker@man~searching-manuals:~$ /challenge/challenge -m
Initializing...
Correct usage! Your flag: pwn.college{MXMORlEZDseeh2N0hKhB_WS3k0C.dVTM4QDL0kzN0czW}
hacker@man~searching-manuals:~$
```
## learnings
learnt how to search within the manual of a command using '/' and locating its positions with 'n'

#
## code
```bash
man hacker@man~searching-for-manuals:~$ man man
MAN(1)                                                                       Manual pager utils                                                                      MAN(1)

NAME
       man - an interface to the system reference manuals

SYNOPSIS
       man [man options] [[section] page ...] ...
       man -k [apropos options] regexp ...
       man -K [man options] [section] term ...
       man -f [whatis options] page ...
       man -l [man options] file ...
       man -w|-W [man options] page ...

DESCRIPTION
       man  is the system's manual pager.  Each page argument given to man is normally the name of a program, utility or function.  The manual page associated with each of
       these arguments is then found and displayed.  A section, if provided, will direct man to look only in that section of the manual.  The default action is  to  search
       in all of the available sections following a pre-defined order (see DEFAULTS), and to show only the first page found, even if page exists in several sections.

       The table below shows the section numbers of the manual followed by the types of pages they contain.

       1   Executable programs or shell commands
       2   System calls (functions provided by the kernel)
       3   Library calls (functions within program libraries)
hacker@man~searching-for-manuals:~$ man -k challenge
gztqyudymp (1)       - print the flag!
hacker@man~searching-for-manuals:~$ /challenge/challenge --gztqyudymp
Incorrect usage! Please read the challenge man page!
hacker@man~searching-for-manuals:~$ man gztqyudymp

CHALLENGE(1)                                                                 Challenge Commands                                                                CHALLENGE(1)

NAME
       /challenge/challenge - print the flag!

SYNOPSIS
       challenge OPTION

DESCRIPTION
       Output the flag when called with the right arguments.

       --fortune
              read a fortune

       --version
              output version information and exit

       --gztqyu NUM
              print the flag if NUM is 640

AUTHOR
       Written by Zardus.
hacker@man~searching-for-manuals:~$ /challenge/challenge --gztqyu 640
Correct usage! Your flag: pwn.college{g6zNtqEyHTWudMymZNpdGgdWDNa.dZTM4QDL0kzN0czW}
```
## learnings
to access the manual of man and then further pass an argument so as to read the hidden manual and then access it using man function

# helpful programs
## code
```bash
hacker@man~helpful-programs:~$ /challenge/challenge --help
usage: a challenge to make you ask for help [-h] [--fortune] [-v] [-g GIVE_THE_FLAG] [-p]

optional arguments:
  -h, --help            show this help message and exit
  --fortune             read your fortune
  -v, --version         get the version number
  -g GIVE_THE_FLAG, --give-the-flag GIVE_THE_FLAG
                        get the flag, if given the correct value
  -p, --print-value     print the value that will cause the -g option to give you the flag
hacker@man~helpful-programs:~$ /challenge/challenge -p
The secret value is: 944
hacker@man~helpful-programs:~$ /challenge/challenge --give-the-flag 944
Correct usage! Your flag: pwn.college{QQg_E9JCIm_w4nZaoXykbrhQFnf.ddjM4QDL0kzN0czW}
hacker@man~helpful-programs:~$ /challenge/challenge  -g 944
Correct usage! Your flag: pwn.college{QQg_E9JCIm_w4nZaoXykbrhQFnf.ddjM4QDL0kzN0czW}
```
## learnings
learnt how to use --help in order to understand the functioning of a program if manual page is not available upon using man function

# help for bulletins
## code
```bash
hacker@man~help-for-builtins:~$ help challenge
challenge: challenge [--fortune] [--version] [--secret SECRET]
    This builtin command will read you the flag, given the right arguments!
    
    Options:
      --fortune		display a fortune
      --version		display the version
      --secret VALUE	prints the flag, if VALUE is correct

    You must be sure to provide the right value to --secret. That value
    is "4IYFsZ-k".
hacker@man~help-for-builtins:~$ challenge --secret VALUE
ERROR: incorrect argument to --secret. Read the help!
hacker@man~help-for-builtins:~$ challenge --secret 4IYFsZ-k
Correct! Here is your flag!
pwn.college{4IYFsZ-ktOAOSh9dp239DXofeIp.dRTM5QDL0kzN0czW}
```
## learnings
learnt the functioning of built-in functions. And how to use help in order to understand the working of built in functions

