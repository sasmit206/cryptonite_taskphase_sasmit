# becoming-root-with-su
## code
```bash
hacker@users~becoming-root-with-su:~$ su
Password: 
root@users~becoming-root-with-su:/home/hacker# cat /flag
pwn.college{AIj77wdrRK1AB69U7MxRrN6EAmc.dVTN0UDL0kzN0czW}
root@users~becoming-root-with-su:/home/hacker#
```
## learnings
learnt how to use su command upon inputting password

# other-users-with-su
## code
```bash
hacker@users~other-users-with-su:~$ su zardus
Password: 
zardus@users~other-users-with-su:/home/hacker$ /challenge/run
Congratulations, you have become Zardus! Here is your flag:
pwn.college{kt4n4fGWaUhc525g1x_JFoFNY1f.dZTN0UDL0kzN0czW}
```
# learnings
learnt how to use su command to change to a diffrent user 

# cracking-passwords
## code
```bash
Connected!                                                                        
hacker@users~cracking-passwords:~$ cat /challenge/shadow-leak
root:*:19873:0:99999:7:::
daemon:*:19873:0:99999:7:::
bin:*:19873:0:99999:7:::
sys:*:19873:0:99999:7:::
sync:*:19873:0:99999:7:::
games:*:19873:0:99999:7:::
man:*:19873:0:99999:7:::
lp:*:19873:0:99999:7:::
mail:*:19873:0:99999:7:::
news:*:19873:0:99999:7:::
uucp:*:19873:0:99999:7:::
proxy:*:19873:0:99999:7:::
www-data:*:19873:0:99999:7:::
backup:*:19873:0:99999:7:::
list:*:19873:0:99999:7:::
irc:*:19873:0:99999:7:::
gnats:*:19873:0:99999:7:::
nobody:*:19873:0:99999:7:::
_apt:*:19873:0:99999:7:::
hacker::20000:0:99999:7:::
zardus:$6$WwPmlbv6C02ZjAMT$OUnni/rei9P3bzUdiK/Om7QoZrVtTcXc2cWBI6MAvhAVrgI3I7xRt9SoCjKCBhDYwGw3HTbyjyw3emei9nwBr/:20004:0:99999:7:::
hacker@users~cracking-passwords:~$ john /challenge/shdow-leak
stat: /challenge/shdow-leak: No such file or directory
hacker@users~cracking-passwords:~$ john /challenge/shadow-leak
Loaded 1 password hash (crypt, generic crypt(3) [?/64])
Press 'q' or Ctrl-C to abort, almost any other key for status
0g 0:00:00:10 99% 1/3 0g/s 287.1p/s 287.1c/s 287.1C/s zardus999991915..999991900
aardvark         (zardus)
1g 0:00:00:20 100% 2/3 0.04904g/s 285.5p/s 285.5c/s 285.5C/s Johnson..buzz
Use the "--show" option to display all of the cracked passwords reliably
Session completed
hacker@users~cracking-passwords:~$ john --show /challenge/shadow-leak
hacker:NO PASSWORD:20000:0:99999:7:::
zardus:aardvark:20004:0:99999:7:::

2 password hashes cracked, 0 left
hacker@users~cracking-passwords:~$ su zardus
Password: 
zardus@users~cracking-passwords:/home/hacker$ cat flag
cat: flag: No such file or directory
zardus@users~cracking-passwords:/home/hacker$ cat /flag
cat: /flag: Permission denied
zardus@users~cracking-passwords:/home/hacker$ /challenge/run
Congratulations, you have become Zardus! Here is your flag:
pwn.college{M01KJKjDSEWy2ITeQJoHiTFX0ia.ddTN0UDL0kzN0czW}
zardus@users~cracking-passwords:/home/hacker$ 
```
## learning
learnt how to crack some passowords using john the ripper in the terminal.
first accesed the contents of the file challenge/shadow-leak. then used john cmd on it to get passoword of user zardus. finally, su'd to zardus in order to run /challenge/run

# using sudo
## code
```bash
hacker@users~using-sudo:~$ cat /flag
cat: /flag: Permission denied
hacker@users~using-sudo:~$ sudo cat /flag
pwn.college{0NHsh3Q0UT0vIhMVRInzNQdBZYW.dhTN0UDL0kzN0czW}
```
## learning
learnt about functioning of sudo

