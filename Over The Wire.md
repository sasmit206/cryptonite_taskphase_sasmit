# lv 0
```bash
sasmit@Sasmits-MacBook-Air ~ % ssh bandit0@bandit.labs.overthewire.org -p2220
The authenticity of host '[bandit.labs.overthewire.org]:2220 ([16.16.163.126]:2220)' can't be established.
ED25519 key fingerprint is SHA256:C2ihUBV7ihnV1wUXRb4RrEcLfXC5CXlhmAAM/urerLY.
This key is not known by any other names.
Are you sure you want to continue connecting (yes/no/[fingerprint])? yes
Warning: Permanently added '[bandit.labs.overthewire.org]:2220' (ED25519) to the list of known hosts.
                         _                     _ _ _   
                        | |__   __ _ _ __   __| (_) |_ 
                        | '_ \ / _` | '_ \ / _` | | __|
                        | |_) | (_| | | | | (_| | | |_ 
                        |_.__/ \__,_|_| |_|\__,_|_|\__|
                                                       

                      This is an OverTheWire game server. 
            More information on http://www.overthewire.org/wargames

bandit0@bandit.labs.overthewire.org's password: 

      ,----..            ,----,          .---.
     /   /   \         ,/   .`|         /. ./|
    /   .     :      ,`   .'  :     .--'.  ' ;
   .   /   ;.  \   ;    ;     /    /__./ \ : |
  .   ;   /  ` ; .'___,/    ,' .--'.  '   \' .
  ;   |  ; \ ; | |    :     | /___/ \ |    ' '
  |   :  | ; | ' ;    |.';  ; ;   \  \;      :
  .   |  ' ' ' : `----'  |  |  \   ;  `      |
  '   ;  \; /  |     '   :  ;   .   \    .\  ;
   \   \  ',  /      |   |  '    \   \   ' \ |
    ;   :    /       '   :  |     :   '  |--"
     \   \ .'        ;   |.'       \   \ ;
  www. `---` ver     '---' he       '---" ire.org


Welcome to OverTheWire!

If you find any problems, please report them to the #wargames channel on
discord or IRC.

--[ Playing the games ]--

  This machine might hold several wargames.
  If you are playing "somegame", then:

    * USERNAMES are somegame0, somegame1, ...
    * Most LEVELS are stored in /somegame/.
    * PASSWORDS for each level are stored in /etc/somegame_pass/.

  Write-access to homedirectories is disabled. It is advised to create a
  working directory with a hard-to-guess name in /tmp/.  You can use the
  command "mktemp -d" in order to generate a random and hard to guess
  directory in /tmp/.  Read-access to both /tmp/ is disabled and to /proc
  restricted so that users cannot snoop on eachother. Files and directories
  with easily guessable or short names will be periodically deleted! The /tmp
  directory is regularly wiped.
  Please play nice:

    * don't leave orphan processes running
    * don't leave exploit-files laying around
    * don't annoy other players
    * don't post passwords or spoilers
    * again, DONT POST SPOILERS!
      This includes writeups of your solution on your blog or website!

--[ Tips ]--

  This machine has a 64bit processor and many security-features enabled
  by default, although ASLR has been switched off.  The following
  compiler flags might be interesting:

    -m32                    compile for 32bit
    -fno-stack-protector    disable ProPolice
    -Wl,-z,norelro          disable relro

  In addition, the execstack tool can be used to flag the stack as
  executable on ELF binaries.

  Finally, network-access is limited for most levels by a local
  firewall.

--[ Tools ]--

 For your convenience we have installed a few useful tools which you can find
 in the following locations:

    * gef (https://github.com/hugsy/gef) in /opt/gef/
    * pwndbg (https://github.com/pwndbg/pwndbg) in /opt/pwndbg/
    * gdbinit (https://github.com/gdbinit/Gdbinit) in /opt/gdbinit/
    * pwntools (https://github.com/Gallopsled/pwntools)
    * radare2 (http://www.radare.org/)

--[ More information ]--

  For more information regarding individual wargames, visit
  http://www.overthewire.org/wargames/

  For support, questions or comments, contact us on discord or IRC.

  Enjoy your stay!

bandit0@bandit:~$ pwd
/home/bandit0
bandit0@bandit:~$ ls
readme
bandit0@bandit:~$ cat readme
Congratulations on your first steps into the bandit game!!
Please make sure you have read the rules at https://overthewire.org/rules/
```

# lv1 
```bash
sasmit@Sasmits-MacBook-Air ~ % ssh bandit1@bandit.labs.overthewire.org -p2220
                         _                     _ _ _   
                        | |__   __ _ _ __   __| (_) |_ 
                        | '_ \ / _` | '_ \ / _` | | __|
                        | |_) | (_| | | | | (_| | | |_ 
                        |_.__/ \__,_|_| |_|\__,_|_|\__|
                                                       

                      This is an OverTheWire game server. 
            More information on http://www.overthewire.org/wargames

bandit1@bandit.labs.overthewire.org's password: 

      ,----..            ,----,          .---.
     /   /   \         ,/   .`|         /. ./|
    /   .     :      ,`   .'  :     .--'.  ' ;
   .   /   ;.  \   ;    ;     /    /__./ \ : |
  .   ;   /  ` ; .'___,/    ,' .--'.  '   \' .
  ;   |  ; \ ; | |    :     | /___/ \ |    ' '
  |   :  | ; | ' ;    |.';  ; ;   \  \;      :
  .   |  ' ' ' : `----'  |  |  \   ;  `      |
  '   ;  \; /  |     '   :  ;   .   \    .\  ;
   \   \  ',  /      |   |  '    \   \   ' \ |
    ;   :    /       '   :  |     :   '  |--"
     \   \ .'        ;   |.'       \   \ ;
  www. `---` ver     '---' he       '---" ire.org


Welcome to OverTheWire!

If you find any problems, please report them to the #wargames channel on
discord or IRC.

--[ Playing the games ]--

  This machine might hold several wargames.
  If you are playing "somegame", then:

    * USERNAMES are somegame0, somegame1, ...
    * Most LEVELS are stored in /somegame/.
    * PASSWORDS for each level are stored in /etc/somegame_pass/.

  Write-access to homedirectories is disabled. It is advised to create a
  working directory with a hard-to-guess name in /tmp/.  You can use the
  command "mktemp -d" in order to generate a random and hard to guess
  directory in /tmp/.  Read-access to both /tmp/ is disabled and to /proc
  restricted so that users cannot snoop on eachother. Files and directories
  with easily guessable or short names will be periodically deleted! The /tmp
  directory is regularly wiped.
  Please play nice:

    * don't leave orphan processes running
    * don't leave exploit-files laying around
    * don't annoy other players
    * don't post passwords or spoilers
    * again, DONT POST SPOILERS!
      This includes writeups of your solution on your blog or website!

--[ Tips ]--

  This machine has a 64bit processor and many security-features enabled
  by default, although ASLR has been switched off.  The following
  compiler flags might be interesting:

    -m32                    compile for 32bit
    -fno-stack-protector    disable ProPolice
    -Wl,-z,norelro          disable relro

  In addition, the execstack tool can be used to flag the stack as
  executable on ELF binaries.

  Finally, network-access is limited for most levels by a local
  firewall.

--[ Tools ]--

 For your convenience we have installed a few useful tools which you can find
 in the following locations:

    * gef (https://github.com/hugsy/gef) in /opt/gef/
    * pwndbg (https://github.com/pwndbg/pwndbg) in /opt/pwndbg/
    * gdbinit (https://github.com/gdbinit/Gdbinit) in /opt/gdbinit/
    * pwntools (https://github.com/Gallopsled/pwntools)
    * radare2 (http://www.radare.org/)

--[ More information ]--

  For more information regarding individual wargames, visit
  http://www.overthewire.org/wargames/

  For support, questions or comments, contact us on discord or IRC.

  Enjoy your stay!

bandit1@bandit:~$ pwd
/home/bandit1
bandit1@bandit:~$ cat loacated
cat: loacated: No such file or directory
bandit1@bandit:~$ cat < -
263JGJPfgU6LtdEvgfWU1XP5yac29mFx
bandit1@bandit:~$ exit 
logout
Connection to bandit.labs.overthewire.org closed.
sasmit@Sasmits-MacBook-Air ~ % 
```

# lv2 
```bash
bandit2@bandit:~$ cat spaces
cat: spaces: No such file or directory
bandit2@bandit:~$ cat "spaces in this filename"
MNk8KNH3Usiio41PRUEoDFPqfxLPlSmx
bandit2@bandit:~$ exit
logout
```

# lv3
```bash
bandit3@bandit:~$ pwd
/home/bandit3
bandit3@bandit:~$ cd /inhere
-bash: cd: /inhere: No such file or directory
bandit3@bandit:~$ cd ./inhere
bandit3@bandit:~/inhere$ ls
bandit3@bandit:~/inhere$ ls -a
.  ..  ...Hiding-From-You
bandit3@bandit:~/inhere$ cat ...Hiding-From-You
2WmrDFRmJIq3IPxneAaMGhap0pFhF3NJ
```

# lv4
``` bash
bandit4@bandit:~$ ls -a
.  ..  .bash_logout  .bashrc  inhere  .profile
bandit4@bandit:~$ cat inhere
cat: inhere: Is a directory
bandit4@bandit:~$ cd inhere
bandit4@bandit:~/inhere$ ls -a
.   -file00  -file02  -file04  -file06  -file08
..  -file01  -file03  -file05  -file07  -file09
bandit4@bandit:~/inhere$ cat < -file00
?p??&?y?,?(jo?.at?:uf?^???@bandit4@bandit:~/inhere$ 
GNU bash, version 5.2.21(1)-release (x86_64-pc-linux-gnu)
bandit4@bandit:~/inhere$ find . -type f ! -executable -exec file {} + | grep 'ASCII text'
./-file07: ASCII text
bandit4@bandit:~/inhere$ cat < -file007
-bash: -file007: No such file or directory
bandit4@bandit:~/inhere$ cat < -file07
4oQYVPkxZOOEOO5pTW81FB8j8lxXGUQw
```
very tricky, extremely complex find command used in order to look thorough the files and find the one containing ASCII text ( ie human readable ).

# lv5
```bash
bandit5@bandit:~/inhere$ find . -type f -size 1033c ! -executable -exec file {} + | grep 'ASCII text'
./maybehere07/.file2: ASCII text, with very long lines (1000)
bandit5@bandit:~/inhere$ cd ./maybehere07
bandit5@bandit:~/inhere/maybehere07$ ls -a
.  ..  -file1  .file1  -file2  .file2  -file3  .file3  spaces file1  spaces file2  spaces file3
bandit5@bandit:~/inhere/maybehere07$ cat .file2
HWasnPhtq9AVKe0dmk45nxy20cvUa6EG
```

# lv6
```bash
bandit6@bandit:~$ find / -user bandit7 -group bandit6 -size 33c
find: ‘/drifter/drifter14_src/axTLS’: Permission denied
find: ‘/root’: Permission denied
find: ‘/snap’: Permission denied
find: ‘/tmp’: Permission denied
find: ‘/proc/tty/driver’: Permission denied
find: ‘/proc/384649/task/384649/fd/6’: No such file or directory
find: ‘/proc/384649/task/384649/fdinfo/6’: No such file or directory
find: ‘/proc/384649/fd/5’: No such file or directory
find: ‘/proc/384649/fdinfo/5’: No such file or directory
find: ‘/home/bandit31-git’: Permission denied
find: ‘/home/ubuntu’: Permission denied
find: ‘/home/bandit5/inhere’: Permission denied
find: ‘/home/bandit30-git’: Permission denied
find: ‘/home/drifter8/chroot’: Permission denied
find: ‘/home/drifter6/data’: Permission denied
find: ‘/home/bandit29-git’: Permission denied
find: ‘/home/bandit28-git’: Permission denied
find: ‘/home/bandit27-git’: Permission denied
find: ‘/lost+found’: Permission denied
find: ‘/etc/polkit-1/rules.d’: Permission denied
find: ‘/etc/multipath’: Permission denied
find: ‘/etc/stunnel’: Permission denied
find: ‘/etc/xinetd.d’: Permission denied
find: ‘/etc/credstore.encrypted’: Permission denied
find: ‘/etc/ssl/private’: Permission denied
find: ‘/etc/sudoers.d’: Permission denied
find: ‘/etc/credstore’: Permission denied
find: ‘/dev/shm’: Permission denied
find: ‘/dev/mqueue’: Permission denied
find: ‘/var/log/amazon’: Permission denied
find: ‘/var/log/unattended-upgrades’: Permission denied
find: ‘/var/log/chrony’: Permission denied
find: ‘/var/log/private’: Permission denied
find: ‘/var/tmp’: Permission denied
find: ‘/var/spool/cron/crontabs’: Permission denied
find: ‘/var/spool/bandit24’: Permission denied
find: ‘/var/spool/rsyslog’: Permission denied
find: ‘/var/cache/ldconfig’: Permission denied
find: ‘/var/cache/apt/archives/partial’: Permission denied
find: ‘/var/cache/pollinate’: Permission denied
find: ‘/var/cache/private’: Permission denied
find: ‘/var/cache/apparmor/2425d902.0’: Permission denied
find: ‘/var/cache/apparmor/baad73a1.0’: Permission denied
find: ‘/var/lib/polkit-1’: Permission denied
find: ‘/var/lib/amazon’: Permission denied
/var/lib/dpkg/info/bandit7.password
find: ‘/var/lib/apt/lists/partial’: Permission denied
find: ‘/var/lib/chrony’: Permission denied
find: ‘/var/lib/snapd/void’: Permission denied
find: ‘/var/lib/snapd/cookie’: Permission denied
find: ‘/var/lib/private’: Permission denied
find: ‘/var/lib/ubuntu-advantage/apt-esm/var/lib/apt/lists/partial’: Permission denied
find: ‘/var/lib/update-notifier/package-data-downloads/partial’: Permission denied
find: ‘/var/lib/udisks2’: Permission denied
find: ‘/var/crash’: Permission denied
find: ‘/boot/efi’: Permission denied
find: ‘/boot/lost+found’: Permission denied
find: ‘/sys/kernel/tracing’: Permission denied
find: ‘/sys/kernel/debug’: Permission denied
find: ‘/sys/fs/pstore’: Permission denied
find: ‘/sys/fs/bpf’: Permission denied
find: ‘/run/lock/lvm’: Permission denied
find: ‘/run/systemd/inaccessible/dir’: Permission denied
find: ‘/run/systemd/propagate/systemd-udevd.service’: Permission denied
find: ‘/run/systemd/propagate/systemd-resolved.service’: Permission denied
find: ‘/run/systemd/propagate/systemd-networkd.service’: Permission denied
find: ‘/run/systemd/propagate/irqbalance.service’: Permission denied
find: ‘/run/systemd/propagate/systemd-logind.service’: Permission denied
find: ‘/run/systemd/propagate/chrony.service’: Permission denied
find: ‘/run/systemd/propagate/polkit.service’: Permission denied
find: ‘/run/systemd/propagate/ModemManager.service’: Permission denied
find: ‘/run/systemd/propagate/fwupd.service’: Permission denied
find: ‘/run/systemd/propagate/bolt.service’: Permission denied
find: ‘/run/lvm’: Permission denied
find: ‘/run/log/journal/ec2dd69f90c4a6285216f71caca9bbca’: Permission denied
find: ‘/run/cryptsetup’: Permission denied
find: ‘/run/multipath’: Permission denied
find: ‘/run/screen/S-bandit20’: Permission denied
find: ‘/run/screen/S-bandit27’: Permission denied
find: ‘/run/screen/S-bandit28’: Permission denied
find: ‘/run/screen/S-bandit24’: Permission denied
find: ‘/run/screen/S-bandit17’: Permission denied
find: ‘/run/screen/S-bandit12’: Permission denied
find: ‘/run/screen/S-bandit29’: Permission denied
find: ‘/run/screen/S-bandit23’: Permission denied
find: ‘/run/screen/S-bandit1’: Permission denied
find: ‘/run/screen/S-bandit31’: Permission denied
find: ‘/run/screen/S-bandit21’: Permission denied
find: ‘/run/screen/S-bandit22’: Permission denied
find: ‘/run/screen/S-bandit19’: Permission denied
find: ‘/run/screen/S-bandit30’: Permission denied
find: ‘/run/screen/S-bandit33’: Permission denied
find: ‘/run/screen/S-bandit25’: Permission denied
find: ‘/run/screen/S-bandit16’: Permission denied
find: ‘/run/sudo’: Permission denied
find: ‘/run/user/11000’: Permission denied
find: ‘/run/user/11012’: Permission denied
find: ‘/run/user/11001’: Permission denied
find: ‘/run/user/11013’: Permission denied
find: ‘/run/user/11023’: Permission denied
find: ‘/run/user/11016’: Permission denied
find: ‘/run/user/11028’: Permission denied
find: ‘/run/user/11024’: Permission denied
find: ‘/run/user/11027’: Permission denied
find: ‘/run/user/11005’: Permission denied
find: ‘/run/user/11015’: Permission denied
find: ‘/run/user/11003’: Permission denied
find: ‘/run/user/11020’: Permission denied
find: ‘/run/user/11004’: Permission denied
find: ‘/run/user/11032’: Permission denied
find: ‘/run/user/11025’: Permission denied
find: ‘/run/user/11018’: Permission denied
find: ‘/run/user/11009’: Permission denied
find: ‘/run/user/11006/systemd/inaccessible/dir’: Permission denied
find: ‘/run/user/11002’: Permission denied
find: ‘/run/user/11010’: Permission denied
find: ‘/run/user/11011’: Permission denied
find: ‘/run/user/11019’: Permission denied
find: ‘/run/user/11008’: Permission denied
find: ‘/run/user/11014’: Permission denied
find: ‘/run/user/11007’: Permission denied
find: ‘/run/user/11021’: Permission denied
find: ‘/run/user/11031’: Permission denied
find: ‘/run/user/11022’: Permission denied
find: ‘/run/user/8001’: Permission denied
find: ‘/run/user/8006’: Permission denied
find: ‘/run/user/8002’: Permission denied
find: ‘/run/user/11017’: Permission denied
find: ‘/run/user/11033’: Permission denied
find: ‘/run/chrony’: Permission denied
find: ‘/run/udisks2’: Permission denied
bandit6@bandit:~$ cat /var/lib/dpkg/info/bandit7.password
morbNTDkSW6jIlUc0ymOdMaLnOlFVAaj
```

# lv7
```bash
bandit7@bandit:~$ cat data.txt | grep "millionth*"
millionth	dfwvzFQi4mU0wfNbFOe9RoWskMLg7eEc
```

# lv8
```bash
bandit8@bandit:~$ sort data.txt | uniq -u
4CKMh1JI91bUIZZPXDqGanal4xvAg0JM
```
learnt thee working of uniq command and also learnt how to display lines with frequency of only 1

# lv9
```code
bandit9@bandit:~$ cat data.txt | grep -a "=========" 
?D??]???
        ???????h#!??Q??????J??s?V?zl7????POl%Y]?H??a?^?UvTo?D?|?@T????^?N????8g??}??b?}???
Q#?g??m1x??}========== the?Ѧ+??i?d?W??^?)F1??>)٘S?K?3?PZ???t?&xs肉WB/?2??ÜB??	?Ź/?Bjɢ?????<???э?7??<??????u?/??d|
                                  ?-??????n
#??i?u=
       ???7?֣?n?)?Uջ??ش??5bBK??K???}x?>}:??4Rl_7gH??D:?27??4????C?F??y
                                                                     Q??dqhO??????6??!??&???z?B??$?l?_G??p?hqI.X???0?2????H????$?Tw??m??⧫???o3?m?t0??p??~?L?3JprD========== passwordi???	?L? ~ˏ??<@??Ȅh?$???%Q5???D??k? ?|?3
~?T???f?;?o9?s??P#t?+Pe??΢쵟
OqDf??.?8???Czmnf&v???l:??F?X????K???b?M?
                               ?C???I???Bi?>??Y?
?Еk???  $?nX??T=~?}*4?a2?????TO"'?&?J?~fDV3========== is?d?5z(??#?&s?T!1?0?&p???oq??
?n?R? ???F
          ??z?|!?(?i?f??+??A6?4?+'??F???T=??b5??A?}?
                                                    ???#?}#9???㵴??b?R?+?̊?~&??Oi?ٱ?éT:?k?????????A????U?2?Qc?ɐ?%#?g+;YA_e?kr?????X53|?f8+e
   ]󈍅(?.?ۍg?:7???n???????n?p????????? ???????CD?`v?oS?Q?-<]?`?@?#H Uum????BiA??j堵??!O?&?????D9========== FGUW5ilLVJrxX9kMYMmlN4MgbpfMiqey
```
learnt that grep -a allows to treat binary files as text

# lv 10)
```
bandit10@bandit:~$ cat data.txt
VGhlIHBhc3N3b3JkIGlzIGR0UjE3M2ZaS2IwUlJzREZTR3NnMlJXbnBOVmozcVJyCg==
bandit10@bandit:~$ base64 -d data.txt
The password is dtR173fZKb0RRsDFSGsg2RWnpNVj3qRr
```
learnt how to use base64 command

# lv11)
``` bash
bandit11@bandit:~$ tr 'A-Za-z''N-ZA-Mn-za-m' < cat data.txt
-bash: cat: No such file or directory
bandit11@bandit:~$ tr 'A-Za-z''N-ZA-Mn-za-m' < data.txt
tr: missing operand after ‘A-Za-zN-ZA-Mn-za-m’
Two strings must be given when translating.
Try 'tr --help' for more information.
bandit11@bandit:~$ tr 'A-Za-z' 'N-ZA-Mn-za-m' < data.txt
The password is 7x16WNeHIi5YkIhWsfFIqoognUTyj9Q4
```

# lv12)
