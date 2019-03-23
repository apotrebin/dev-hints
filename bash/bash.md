## Info  
```
man – помощь
info – тоже помощь
uptime  - время с последнего включения
lscpu – данные процессора
whatis – показывает что делает комманда
whereis – показывает где файл
locate – показывает где файл
Ctrl+Z  - отправить процесс на background
Ctrl+C – прекратить процесс вообще
```

## Explorer
```
cd  - сменить директорию
ls – вывести содержимое директории
ls -l  - вывести содержимое директории подробно
pwd – вывести путь где мы сейчас
~    - сокращение нашей Home директории
/    - коренная директория Linux
..    - директория которая выше 
.     - директория где мы сейчас
ls –la –R  /    - показать все на компутере

touch – создать файл или обновить время
cp  - скопировать файл
mv – перенести файл или переименовать
rm – стереть файл

mkdir – создать директорию
rmdir – стереть пустую директорию
cp     - копировать директорию
mv  - переименовать или перенести директорию

ln   - создать дубликат файла 
ln –s   - создать symbolic линк на файл или директорию типа Shortcut

find  - найти файл
wc  - вывести количество строк, слов, байт
cut – вывести определенное поле из текста
sort – вывести отсортированный текст

grep  - поиск определонного слова в файле и вывод строк с этим словом

/dev/null   - устройство находящиеся в ж#$е
```

## ZIP
```
tar cf  mytar.tar  Folder1   - заархивировать Folder1
tar xf mytar.tar  - разархивировать архив
gzip     / bzip2     / xz      – скомпрессировать файл
gunzip /  bunzip2 / unxz  – раскомпресировать файл

tar cvzf myBZIP2.bz2  Folder1    – сжать Folder1
tar xvf  myBZIP2.bz2                  - распаковать архив
tar tf myBZIP2.bz2    - посмотреть что внутри архива

zip –r myZIP.zip Folder1   - Запаковать Folder1 в ZIP
unzip myZIP.zip                - Распаковать файл myZIP.zip
```

## Processes
```
top – как Task Manager в Windows
free  - показать состояние памяти в байтах
free –h  - показать состояние памяти в MB, GB
ps          -  показать мои процессы 
ps aux  - показать все процессы от всех пользователей

ps aux | grep bash  - найти все процессы bash от всех пользователей
```


## User
```
sudo  - запустить комманду используя Super User права
su   - сменить текушего пользователя

/etc/passwd    - тут хранятся все аккаунты
/etc/shadow   - тут хранятся все пароли аккаунтов
/etc/group    - тут хранятся все группы

whoami  - показать имя текущего пользователя
id   - показать к каким группам принадлежит пользователь
who – показать кто сейчас в системе
w   - показать кто сейчас в системе и что делает
last – показать последние логины
```

## Groups
```
useradd  -m vasya   - создать юзера vasya с домашней  директорией
userdel –r vasya     - стереть юзера vasya с его домашней  директорией
/etc/skel    -  это шаблон домашней директории
passwd vasya   - изменить пароль для юзера vasya

groupadd QADepartament  - создать группу QADepartament
groupdel QADepartament  - стереть группу QADepartament

usermod –aG QADepartament vasya  - добавить юзера vasya в группу QADepartament
deluser vasya QADepartament  - удалить юзера vasya  из групы QADepartament
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
chmod  741   myfile.txt  установить:   RWX   владельцу, R - -    группе,  - - X   всем остальным
r = 4
w = 2
x = 1

chmod  1777 myDir    включить StickyBit
chmod 0777 myDir    выключить StickyBit
```

## Network
```
ifconfig          - показать мой IP адресс
ip addr show  - показать мой IP адресс

route      - показать адресс раутера Gateway
ping        - протестировать коннекшен к адрессу
host       - дать IP адресс вэб сайта
dig         - дать IP адресс вэб сайта
netstat  – выдать сетевые подключения компьютера
```

## Download | Install | Remove
```
wget    - скачать файл из интернета

Ubuntu/Debian/Kali/Mint Linux:
~~~~~~~~~~~~~~~~~~~~~
apt-get install     - скачать и установить программу
apt-get remove   - удалить программу
dpkg –i                - установить программу из файла .deb
dpkg –r                - удалить программу

RedHat/CenOS Linux:
~~~~~~~~~~~~~~
yum install          - скачать и установить программу
yum remove         - удалить программу
rpm –i                  - установить программу из файла .rpm
rpm –e                 - удалить программу
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
/dev/sda    - первый SATA диск
/dev/sdb    - второй SATA диск
/dev/sdc    - третий SATA диск

fdisk –l    -  показать какие есть диски
lsblk        -  показать какие есть диски
cfdisk   /dev/sdb  - редактировать разделы sdb диска
mkfs.ntfs  –f  /dev/sdb1   - форматировать  раздел первый второго диска
/etc/fstab   - тут прописываем новые диски чтобы они присоединялись автоматически при загрузки Линукса

mount /media/hdd2   - присоединяет диск прописанный в файле fstab с именем hdd2 без перезагрузки Линукса
```

## Change IP Address
```
hostname    - вывести название компа
sudo hostname MyLinux   - переименовать в MyLinux
/etc/hostname   - тут прописано название компа
/etc/hosts          - тут прописываем новое название напротив IP адресса
ifconfig   - вывести текущий IP адресс

Временно меняем IP адресс так:
sudo  ifconfig  eth0  10.10.10.10  netmask  255.0.0.0

/etc/network/interfaces  - тут прописываем постоянный IP
sudo ifdown eth0    - отключить сетевуху eth0
sudo ifup   eth0      - включить сетевуху eth0
```

## SSH
```
service ssh status   - статус SSH сервиса
service ssh start   - запустить SSH сервис
apt-get install openssh-server   - установить SSH

ssh vasya@192.168.10.130   - подключится к компу (192.168.10.130) как пользователь (vasya)
```

## Cron
```
crontab - l    - показать расписание
crontab -e   - редактировать расписание
/etc/crontab  - файл расписания на системном уровне
```