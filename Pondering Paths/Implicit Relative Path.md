# code:
```bash
Connected!                                                                        
hacker@paths~implicit-relative-path:~$ cd /challenge
hacker@paths~implicit-relative-path:/challenge$ run
ssh-entrypoint: run: command not found
hacker@paths~implicit-relative-path:/challenge$ .run
ssh-entrypoint: .run: command not found
hacker@paths~implicit-relative-path:/challenge$ ./run
Correct!!!
./run is a relative path, invoked from the right directory!
Here is your flag:
pwn.college{gOIa7fdOYsh8S7S-zcKgaMg-3d6.dFTN1QDL0kzN0czW}
hacker@paths~implicit-relative-path:/challenge$ 
```
# learnings
- how to execute a program within a given directory
- use '.' to specify that we have to execute it in the directory in which we are present.
