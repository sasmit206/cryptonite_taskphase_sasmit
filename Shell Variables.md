# printing varibales
## code
```bash
hacker@variables~printing-variables:~$ echo $FLAG
pwn.college{gTMTDtQI66HZLzDu5OV4R_nHThq.ddTN1QDL0kzN0czW}
hacker@variables~printing-variables:~$ 
```
## learnings
learnt how to access the value present inside a variable
  
# setting varibales
## code
```bash
hacker@variables~setting-variables:~$ PWN=COLLEGE
You've set the PWN variable properly! As promised, here is the flag:
pwn.college{kx3GDStLZNb5XmLMyrKWZ_IoV00.dlTN1QDL0kzN0czW}
hacker@variables~setting-variables:~$ 
```
## learnings
learnt how to assign values to varibale, also being careful of not using spaces
  
# multi word varibales
## code
```bash
hacker@variables~multi-word-variables:~$ PWN="COLLEGE YEAH"
You've set the PWN variable properly! As promised, here is the flag:
pwn.college{4bNwIGaglemY6Y29ikHxJ46cqvp.dBjN1QDL0kzN0czW}
hacker@variables~multi-word-variables:~$ 

```
## learnings
learnt how to assign multiple words to a given variable. Also understood that a the words following a space-' ' is interpreted by the shell to be a command
  
# exporting varibales
## code
```bash
hacker@variables~exporting-variables:~$ export PWN=COLLEGE
You've set the PWN variable to the proper value!
hacker@variables~exporting-variables:~$ COLLEGE=PWN
You've set the PWN variable to the proper value!
You've set the COLLEGE variable to the proper value!
hacker@variables~exporting-variables:~$ /challenge/run
CORRECT!
You have exported PWN=COLLEGE and set, but not exported, COLLEGE=PWN. Great 
job! Here is your flag:
pwn.college{A0zCiNpihqcA4mQTFwVj8BxStSK.dJjN1QDL0kzN0czW}
You've set the PWN variable to the proper value!
You've set the COLLEGE variable to the proper value!
hacker@variables~exporting-variables:~$ 
```
## learnings
very simple. had to expost the PWN varibale with th egiven value and asssign the COLLEGE varibale with a value without exporting it. Fianlly executed /challenge/run
  
# printing exposrted varibales
## code
```bash
hacker@variables~printing-exported-variables:~$ env
SHELL=/run/dojo/bin/bash
HOSTNAME=variables~printing-exported-variables
PWD=/home/hacker
DOJO_AUTH_TOKEN=1810d825655213b181bb5cbb7c0f6132305e45ea468565b268e78211f7e0884f
HOME=/home/hacker
LANG=C.UTF-8
LS_COLORS=rs=0:di=01;34:ln=01;36:mh=00:pi=40;33:so=01;35:do=01;35:bd=40;33;01:cd=40;33;01:or=40;31;01:mi=00:su=37;41:sg=30;43:ca=00:tw=30;42:ow=34;42:st=37;44:ex=01;32:*.7z=01;31:*.ace=01;31:*.alz=01;31:*.apk=01;31:*.arc=01;31:*.arj=01;31:*.bz=01;31:*.bz2=01;31:*.cab=01;31:*.cpio=01;31:*.crate=01;31:*.deb=01;31:*.drpm=01;31:*.dwm=01;31:*.dz=01;31:*.ear=01;31:*.egg=01;31:*.esd=01;31:*.gz=01;31:*.jar=01;31:*.lha=01;31:*.lrz=01;31:*.lz=01;31:*.lz4=01;31:*.lzh=01;31:*.lzma=01;31:*.lzo=01;31:*.pyz=01;31:*.rar=01;31:*.rpm=01;31:*.rz=01;31:*.sar=01;31:*.swm=01;31:*.t7z=01;31:*.tar=01;31:*.taz=01;31:*.tbz=01;31:*.tbz2=01;31:*.tgz=01;31:*.tlz=01;31:*.txz=01;31:*.tz=01;31:*.tzo=01;31:*.tzst=01;31:*.udeb=01;31:*.war=01;31:*.whl=01;31:*.wim=01;31:*.xz=01;31:*.z=01;31:*.zip=01;31:*.zoo=01;31:*.zst=01;31:*.avif=01;35:*.jpg=01;35:*.jpeg=01;35:*.mjpg=01;35:*.mjpeg=01;35:*.gif=01;35:*.bmp=01;35:*.pbm=01;35:*.pgm=01;35:*.ppm=01;35:*.tga=01;35:*.xbm=01;35:*.xpm=01;35:*.tif=01;35:*.tiff=01;35:*.png=01;35:*.svg=01;35:*.svgz=01;35:*.mng=01;35:*.pcx=01;35:*.mov=01;35:*.mpg=01;35:*.mpeg=01;35:*.m2v=01;35:*.mkv=01;35:*.webm=01;35:*.webp=01;35:*.ogm=01;35:*.mp4=01;35:*.m4v=01;35:*.mp4v=01;35:*.vob=01;35:*.qt=01;35:*.nuv=01;35:*.wmv=01;35:*.asf=01;35:*.rm=01;35:*.rmvb=01;35:*.flc=01;35:*.avi=01;35:*.fli=01;35:*.flv=01;35:*.gl=01;35:*.dl=01;35:*.xcf=01;35:*.xwd=01;35:*.yuv=01;35:*.cgm=01;35:*.emf=01;35:*.ogv=01;35:*.ogx=01;35:*.aac=00;36:*.au=00;36:*.flac=00;36:*.m4a=00;36:*.mid=00;36:*.midi=00;36:*.mka=00;36:*.mp3=00;36:*.mpc=00;36:*.ogg=00;36:*.ra=00;36:*.wav=00;36:*.oga=00;36:*.opus=00;36:*.spx=00;36:*.xspf=00;36:*~=00;90:*#=00;90:*.bak=00;90:*.crdownload=00;90:*.dpkg-dist=00;90:*.dpkg-new=00;90:*.dpkg-old=00;90:*.dpkg-tmp=00;90:*.old=00;90:*.orig=00;90:*.part=00;90:*.rej=00;90:*.rpmnew=00;90:*.rpmorig=00;90:*.rpmsave=00;90:*.swp=00;90:*.tmp=00;90:*.ucf-dist=00;90:*.ucf-new=00;90:*.ucf-old=00;90:
FLAG=pwn.college{MQwIDsyEsE6ConhsS_5rfO6a1X6.dhTN1QDL0kzN0czW}
LESSCLOSE=/usr/bin/lesspipe %s %s
TERM=xterm
LESSOPEN=| /usr/bin/lesspipe %s
SHLVL=1
LC_CTYPE=C.UTF-8
PATH=/run/challenge/bin:/run/workspace/bin:/usr/local/sbin:/usr/local/bin:/usr/sbin:/usr/bin:/sbin:/bin
_=/run/workspace/bin/env
```
## learnings
accessing and printing exported variable using 'env'
  
# storing cmd output
## code
```bash
hacker@variables~storing-command-output:~$ PWN=$(/challenge/run)
Congratulations! You have read the flag into the PWN variable. Now print it out 
and submit it!
hacker@variables~storing-command-output:~$ echo PWN
PWN
hacker@variables~storing-command-output:~$ echo $PWN
pwn.college{A5qBoLlsyWGY2Z9SyQPXSCH9OXe.dVzN0UDL0kzN0czW}
hacker@variables~storing-command-output:~$ 
```
## learnings
reading output of a command into a variable
  
# reading input 
## code
```bash
hacker@variables~reading-input:~$ read PWN

hacker@variables~reading-input:~$ PWN=COLLEGE
You've set the PWN variable properly! As promised, here is the flag:
pwn.college{EBUVyRVtyXY9mt0IEO5L_a9fVL9.dhzN1QDL0kzN0czW}
```
## learnings
learnt reading inputs entered into  a varibale
  
# reading files
## code
```bash
hacker@variables~reading-files:~$ read PWN</challenge/read_me
You've set the PWN variable properly! As promised, here is the flag:
pwn.college{4lCY8p8n416xoszaH6pv4BTgunL.dBjM4QDL0kzN0czW}
```
## learnings
learnt how to read other files to a given variable
