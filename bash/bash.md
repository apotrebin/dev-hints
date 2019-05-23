## Info  
```
man     – help 
info    – help too but a lil bit other :-]
uptime  - время с последнего включения
lscpu   – данные процессора
whatis  – показывает что делает комманда
whereis – показывает где файл
locate  – показывает где файл
Ctrl+Z  - отправить процесс на background
Ctrl+C  – прекратить процесс вообще
printenv - list of environment variables

```

## Explorer
```
cd     - cd
ls     – вывести содержимое директории
ls -l  - вывести содержимое директории подробно
pwd    - path to current directory
~      - /home folder
/      - root directory of Linux
..     - directory above
.      - current directory
ls –la –R  /    - show all on pc :-]

touch  – create file or update time
cp     - copy file or directory 
mv     – move or rename file or folder
rm     – remove
mkdir  – make folder 
rmdir  – remove empty folder

ln     - create duplicate of file or folder
ln –s  - create symbolic link to file or folder, as Shortcut on Windows

find   - find file 
wc     - show number of rows, words, bytes 
cut    – show current field from file
sort   – sorted output

grep   - filtering 

/dev/null   - устройство находящиеся в ж#$е

```

## ZIP
```
tar cf  mytar.tar  Folder1   - pack Folder1
tar xf mytar.tar             - unpack
gzip / bzip2 / xz            – pack  
gunzip /  bunzip2 / unxz     – unpack

tar cvzf myBZIP2.bz2  Folder2  – pack Folder2 to myBZIP2.bz2
tar xvf  myBZIP2.bz2           - unpack myBZIP2.bz2
tar tf myBZIP2.bz2             - show fiolders and files inside of myBZIP2.bz2 

zip –r myZIP.zip Folder3       - pack Folder3 in myZIP.zip
unzip myZIP.zip                - unpack file myZIP.zip
```

## Processes
```
top      – like Task Manager in Windows
free     - show RAM in bytes 
free –h  - show RAM in MB, GB
ps       - show processes
ps aux   - show processes показать все процессы от всех пользователей

ps aux | grep bash  - find all bash processes
```


## User
```
sudo  - execute command with sudo 
su    - change user

/etc/passwd   - here all users
/etc/shadow   - here all passwords for all users
/etc/group    - here all groups

whoami  - show name of curernt user
id      - show all groups for current user показать к каким группам принадлежит пользователь
who     – show who is logged on
w       - who and what doing in system now
last    – last logged in users
```

## Groups
```
useradd  -m vasya   - создать юзера vasya с домашней директорией
userdel –r vasya    - стереть юзера vasya с его домашней директорией
/etc/skel           - это шаблон домашней директории
passwd vasya        - изменить пароль для юзера vasya

groupadd QADepartament  - создать группу QADepartament
groupdel QADepartament  - стереть группу QADepartament

usermod –aG QADepartament vasya  - добавить юзера vasya в группу QADepartament
deluser vasya QADepartament      - удалить юзера vasya  из групы QADepartament
```


## Permissions
```
chown – изменить владельца файла / директории
chgrp – изменить группу файла / директории
сhmod – изменить права доступа на файл / директорию

chmod  ugo+x  myfile.txt   довавить X всем
сhmod  g-rw   myfile.txt   убрать RW у группы
chmod  o=rw   myfile.txt   установить RW всем остальным
 u = user
 g = group
 o = other
 a = ugo


chmod  777   myfile.txt   установить RWX всем
chmod  741   myfile.txt   установить:   RWX   владельцу, R - -    группе,  - - X   всем остальным
r = 4
w = 2
x = 1

chmod  1777 myDir    turn on StickyBit
chmod 0777 myDir     turn of StickyBit
```

## Network
```
ifconfig      - show IP address of mine
ip addr show  - show IP address of mine
ifconfig      - show ip addres and some other network info
route         - show address of Gateway routee
ping          - test connection
host ts.kg    - get IP address of current host
dig           - get IP address of current host
netstat       – show connections
fuser -k 3000/tcp - kill process on 3000 port

```

## Download | Install | Remove
```
wget  - download file to pwd directory 

Ubuntu/Debian/Kali/Mint Linux:
~~~~~~~~~~~~~~~~~~~~~
apt-get install  - download and install application
apt-get remove   - uninstall application
dpkg –i          - install application from .deb file
dpkg –r          - uninstall application from .deb file

RedHat/CenOS Linux:
~~~~~~~~~~~~~~
yum install      - download and install application
yum remove       - uninstall application
rpm –i           - install application from .rpm file
rpm –e           - uninstall application from .rpm file
```

## Scripts
```
./myscript.sh  Vasya  Petya  Kolya
$0 при этом равен  ./myscript.sh
$1 при этом равен Vasya
$2 при этом равен Petya
$3 при этом равен Kolya

myOS=`uname –u`   - запускает uname –u и сохраняет  результат в переменную myOS

Сохранить ввод пользователя в переменную name:
read –p “Please enter your name: “ name
```

## Mount Drives
```
/dev/sda    - first SATA device
/dev/sdb    - second SATA device
/dev/sdc    - third SATA device

fdisk -l                    - show devices with data
lsblk                       - lists information about all or the specified block devices
cfdisk /dev/sdb             - edit partitions of sdb device
mkfs.ntfs  –f  /dev/sdb1    - format first partition of  second device
/etc/fstab   - тут прописываем новые диски чтобы они присоединялись автоматически при загрузки Линукса

mount /media/hdd2   - присоединяет диск прописанный в файле fstab с именем hdd2 без перезагрузки Линукса
```

## Change IP Address
```
hostname               - show hostname  
sudo hostname MyLinux  - rename pc name to MyLinux
/etc/hostname          - file that keep hostname 
/etc/hosts             - file that maps hostnames to IP addresses

Change IP Address for some time:
sudo  ifconfig  eth0  10.10.10.10  netmask  255.0.0.0

/etc/network/interfaces  - put here you permanent IP Address
sudo ifdown eth0         - turn of network interface with name - eth0
sudo ifup   eth0         - turn on network interface with name - eth0
```

## SSH
```
apt-get install openssh-server
service ssh status
service ssh start
ssh vasya@192.168.10.130   - connect to pc (192.168.10.130) as vasya
```

## Cron
```
crontab -l  - show schedule
crontab -e   - edit schedule
/etc/crontab - main config cron file. list of crones
```