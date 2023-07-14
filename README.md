# Домашнее задание к занятию «Система мониторинга Zabbix. Часть 2» - `Костюк Денис`

### Задание 1
#### Требования к результату 

1. Прикрепите в файл README.md скриншот страницы шаблона с названием «Задание 1»
   ![Скрин1](https://github.com/denniskostyuk/zabbix-2/blob/main/task-1_template.png)

А также итемы для шаблона Zadanie-1:
   ![Скрин2](https://github.com/denniskostyuk/zabbix-2/blob/main/task-1_item1.png)
   ![Скрин3](https://github.com/denniskostyuk/zabbix-2/blob/main/task-1_item2.png)
   
3. Приложите в файл README.md текст использованных команд в GitHub

sudo su

apt install postgresql

apt update

apt upgrade

wget https://repo.zabbix.com/zabbix/6.0/debian/pool/main/z/zabbix-release/zabbix-release_6.0-4+debian11_all.deb

dpkg -i zabbix-release_6.0-4+debian11_all.deb

apt update

apt install zabbix-server-pgsql zabbix-frontend-php php7.4-pgsql zabbix-apache-conf zabbix-sql-scripts

systemctl status zabbix-server.service

sudo -u postgres createuser --pwprompt zabbix

sudo -u postgres createdb -O zabbix zabbix

zcat /usr/share/zabbix-sql-scripts/postgresql/server.sql.gz | sudo -u zabbix psql zabbix

nano /etc/zabbix/zabbix_server.conf

systemctl restart zabbix-server apache2

systemctl enable zabbix-server apache2

systemctl status zabbix-server.service


### Задание 2

#### Требования к результаты 
1. Приложите в файл README.md скриншот раздела Configuration > Hosts, где видно, что агенты подключены к серверу
   ![Скрин1](https://github.com/denniskostyuk/zabbix-1/blob/main/Screen-21.png)
   
2. Приложите в файл README.md скриншот лога zabbix agent, где видно, что он работает с сервером
   ![Скрин2](https://github.com/denniskostyuk/zabbix-1/blob/main/Screen-22.png)
   
3. Приложите в файл README.md скриншот раздела Monitoring > Latest data для обоих хостов, где видны поступающие от агентов данные.
   ![Скрин3](https://github.com/denniskostyuk/zabbix-1/blob/main/Screen-23.png)
   
4. Приложите в файл README.md текст использованных команд в GitHub

sudo su

wget https://repo.zabbix.com/zabbix/6.0/debian/pool/main/z/zabbix-release/zabbix-release_6.0-4+debian11_all.deb

dpkg -i zabbix-release_6.0-4+debian11_all.deb

apt update

apt install zabbix-agent

nano /etc/zabbix/zabbix_agentd.conf

systemctl restart zabbix-agent.service

systemctl status zabbix-agent.service
