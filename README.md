# init

*init* - это первый DevOps проект в [школе программирования от Сбербанка](https://21-school.ru/).

Он состоит из 3х частей: 
1. Network
2. System
3. Scripts

На [wiki](../../wiki) страничке проекта вы можете найти детализированное описание с решением каждой задачи.

[`init.en.pdf`](/init.en.pdf) - само задание.

## Network:
### 1. Получите список сетевых интерфейсов машины, не отображая никаких деталей. Только список имен.
![01](https://github.com/do8rolyuboff/Init/blob/master/other/01.png)
### 2. Определите и отобразите характеристики интерфейса Ethernet:
###     (а) Определить широковещательный адрес
![02a](https://github.com/do8rolyuboff/Init/blob/master/other/02(a).png)
###     (b) Определите все IP-адреса, которые являются частью одной подсети.
![02b](https://github.com/do8rolyuboff/Init/blob/master/other/02(b).png)
### 3. Определите MAC-адрес карты Wi-Fi.
![03](https://github.com/do8rolyuboff/Init/blob/master/other/03.png)
### 4. Определите шлюз по умолчанию в таблице маршрутизации.
![04](https://github.com/do8rolyuboff/Init/blob/master/other/04.png)
### 5. Определите IP-адрес DNS, который отвечает на следующий URL: slash16.org
![05](https://github.com/do8rolyuboff/Init/blob/master/other/05.png)
### 6. Получить полный путь к файлу, который содержит IP-адрес DNS-сервера вы используете
`/etc/resolv.conf`
### 7. Запросите внешний DNS-сервер по доменному имени slash16.org (т. Е. Google. 8.8.8.8)
![07](https://github.com/do8rolyuboff/Init/blob/master/other/07.png)
### 8. Найдите поставщика slash16.org
`ost slash16.org' or 'nslookup slash16.org`
`whois 13.33.242.162' or 'https://ipinfo.io/`
### 9. Найти внешний IP 42.fr
`163.172.250.12`
`163.172.250.13`
### 10. Определите сетевые устройства между вашим компьютером и доменом slash16.org.
![10](https://github.com/do8rolyuboff/Init/blob/master/other/10.png)
### 11. Используйте вывод предыдущей команды, чтобы найти имя и IP-адрес устройство, которое устанавливает связь между вами (локальной сетью) и внешним миром
`192.168.30.1`
### 12. Найдите IP, который был назначен вам сервером DHCP
![12](https://github.com/do8rolyuboff/Init/blob/master/other/12.png)
### 13. Благодаря предыдущему вопросу и обратному DNS найдите имя вашего хоста
`host 192.168.29.78`
### 14. Какой файл содержит локальные записи DNS?
`/etc/hosts`
### 15. Переадресация адреса intra.42.fr на 46.19.122.85.
`46.19.122.85 intra.42.fr`

## System:
### 1. В каком файле вы можете найти установленную версию вашего Debian?
`/etc/debian_version`
### 2. Какую команду вы можете использовать для переименования вашей системы?
`sudo hostname "new_name"`
### 3. Какой файл нужно изменить, чтобы сделать его постоянным?
`/etc/hostname`
### 4. Какая команда показывает время с момента последней загрузки вашей системы?
`uptime`
### 5. Назовите команду, которая определяет состояние службы SSH.
`sudo service ssh status`
### 6. Назовите команду, которая перезагружает службу SSH.
`sudo service ssh restart`
### 7. Определите PID службы SSHD.
`cat /var/run/sshd.pid`
### 8. Какой файл содержит ключи RSA систем, которым разрешено подключаться через SSH?
`~/.ssh/sshkey`
### 9. Какая команда позволяет узнать, кто подключен к системе?
`who`
### 10. Назовите команду, в которой перечислены таблицы разделов дисков?
`lsblk`
### 11. Назовите команду, которая отображает доступное свободное место и используется в системе.
`df -H`
### 12. Выясните точный размер каждой папки / var в понятной для человека форме следуя по этому пути.
`sudo du -sh /var/*`
### 13. Назовите команду, которая в реальном времени находит текущие процессы.
`top`
### 14. Запустите команду «tail -f / var / log / syslog» в фоновом режиме.
`sudo tail -f /var/log/syslog &`
### 15. Найдите команду, которая убивает процесс фоновой команды.
`sudo pkill tail`
### 16. Найдите сервис, который позволяет запускать конкретные задачи после регулярного график.
`cron`
### 17. Найдите команду, которая позволяет подключаться через ssh на ВМ. (Параллельно с графическая сессия)
`ssh localhost`
### 18. Найти команду, которая убивает службу SSH
`systemctl stop ssh`
### 19. Перечислите все сервисы, которые запускаются во время загрузки, и назовите этот вид сервисов.
`/*
** systemctl list-unit-files --type=service | grep "enabled" | awk -F'.service' '{print $1}'
*/

accounts-deamon
anacron
apparmor
autovt@
avahi-deamon
bluetooth
console-setup
cron
cups-browsed
cups
dbus-fi.w1.wpa_supplicant1
dbis-org.bluez
dbis-org.freedesktop.Avahi
dbis-org.freedesktop.ModemManager1
dbis-org.freedesktop.nm-dispather
dbis-org.freedesktop.timesync1
getty@
keyboard-setup
ModemManager
network-manager
networking
NetworkManager-dispatcher
NetworkManager-wait-online
NetworkManager
pppd-dns
rsyslog
ssh
sshd
switheroo-control
syslog
systemd-fsck-root
systemd-timesyncd
udisks2
unattended-upgrades
wpa_supplicant

Type: daemon`
### 20. Перечислите всех существующих пользователей на ВМ
`cat /etc/passwd | awk -F':' '{print $1}'`
### 21. Список всех реальных пользователей на ВМ
`less /etc/passwd`
### 22. Найдите команду, которая добавляет нового локального пользователя
`sudo adduser`
### 23. Объясните, как подключить себя как нового пользователя. (С графической сессией и сессией SSH)
`Graphical : Просто сменить пользователя
SSH : ssh localhost`
### 24. Найдите команду, которая перечисляет все пакеты
`dpkg -l`
