# Домашнее задание к занятию "`Git`" - `Петр Буланенко`


### Инструкция по выполнению домашнего задания

   1. Сделайте `fork` данного репозитория к себе в Github и переименуйте его по названию или номеру занятия, например, https://github.com/имя-вашего-репозитория/git-hw или  https://github.com/имя-вашего-репозитория/7-1-ansible-hw).
   2. Выполните клонирование данного репозитория к себе на ПК с помощью команды `git clone`.
   3. Выполните домашнее задание и заполните у себя локально этот файл README.md:
      - впишите вверху название занятия и вашу фамилию и имя
      - в каждом задании добавьте решение в требуемом виде (текст/код/скриншоты/ссылка)
      - для корректного добавления скриншотов воспользуйтесь [инструкцией "Как вставить скриншот в шаблон с решением](https://github.com/netology-code/sys-pattern-homework/blob/main/screen-instruction.md)
      - при оформлении используйте возможности языка разметки md (коротко об этом можно посмотреть в [инструкции  по MarkDown](https://github.com/netology-code/sys-pattern-homework/blob/main/md-instruction.md))
   4. После завершения работы над домашним заданием сделайте коммит (`git commit -m "comment"`) и отправьте его на Github (`git push origin`);
   5. Для проверки домашнего задания преподавателем в личном кабинете прикрепите и отправьте ссылку на решение в виде md-файла в вашем Github.
   6. Любые вопросы по выполнению заданий спрашивайте в чате учебной группы и/или в разделе “Вопросы по заданию” в личном кабинете.
   
Желаем успехов в выполнении домашнего задания!
   
### Дополнительные материалы, которые могут быть полезны для выполнения задания  

1. [Руководство по оформлению Markdown файлов](https://gist.github.com/Jekins/2bf2d0638163f1294637#Code)

     

---

Задание 1
Что нужно сделать:

Установите Zabbix Server с веб-интерфейсом.

Процесс выполнения
Выполняя ДЗ, сверяйтесь с процессом отражённым в записи лекции.
Установите PostgreSQL. Для установки достаточна та версия, что есть в системном репозитороии Debian 11.
Пользуясь конфигуратором команд с официального сайта, составьте набор команд для установки последней версии Zabbix с поддержкой PostgreSQL и Apache.
Выполните все необходимые команды для установки Zabbix Server и Zabbix Web Server.
Требования к результатам
Прикрепите в файл README.md скриншот авторизации в админке.
Приложите в файл README.md текст использованных команд в GitHub.

<img width="1495" height="868" alt="image" src="https://github.com/user-attachments/assets/5fcbe1e6-96ac-4463-b782-fec1d2f401bf" />      

  
  apt install postgres  
    4  apt install postgressql  
    5  apt install postgresql  
    
    6  wget https://repo.zabbix.com/zabbix/7.0/ubuntu/pool/main/z/zabbix-release/zabbix-release_latest_7.0+ubuntu24.04_all.deb
    7  ls
    8  dkpg -i zabbix-release_latest_7.0+ubuntu24.04_all.deb
    9  dpkg -i zabbix-release_latest_7.0+ubuntu24.04_all.deb
   10  ls -la /etc/apt/sources.list.d/  
   11  cat /etc/apt/sources.list.d/zabbix.list   
   12  apt update  
   13  apt install zabbix-server-pgsql zabbix-frontend-php php8.3-pgsql zabbix-apache-conf zabbix-sql-scripts  
   14  systemctl status zabbix-server.service   
   15  su - postgres -c 'psql' --command "CREATE USER zabbix WITH PASSWORD '\'123456789\'';"'    
   16  u -  
   17  su -  
   18  exit  
   19  su petr  
   20  su - postgres -c "psql -c \"CREATE USER zabbix WITH PASSWORD '123456789';\""  
   21  sudo -u postgres createdb -O zabbix zabbix   
   22  zcat /usr/share/zabbix-sql-scripts/postgresql/server.sql.gz | sudo -u zabbix psql zabbix   
   23  fine / -name zabbix_agentd  
   24  find / -name zabbix_agentd  
   25  sudo find / -name zabbix_agentd  
   26  cd /etc  
   27  cd /zabbix  
   28  ll  
   29  cd zabbix  
   30  ll  
   31  nano zabbix_server.conf   
   32  systamctl restart zabbix-server appache2  

  

Задание 2
Установите Zabbix Agent на два хоста.

Процесс выполнения
Выполняя ДЗ, сверяйтесь с процессом отражённым в записи лекции.
Установите Zabbix Agent на 2 вирт.машины, одной из них может быть ваш Zabbix Server.
Добавьте Zabbix Server в список разрешенных серверов ваших Zabbix Agentов.
Добавьте Zabbix Agentов в раздел Configuration > Hosts вашего Zabbix Servera.
Проверьте, что в разделе Latest Data начали появляться данные с добавленных агентов.
Требования к результатам
Приложите в файл README.md скриншот раздела Configuration > Hosts, где видно, что агенты подключены к серверу
Приложите в файл README.md скриншот лога zabbix agent, где видно, что он работает с сервером
Приложите в файл README.md скриншот раздела Monitoring > Latest data для обоих хостов, где видны поступающие от агентов данные.
Приложите в файл README.md текст использованных команд в GitHub



dpkg -i zabbix-release_latest_7.0+ubuntu24.04_all.deb  
   56  apt update   
   57  apt install zabbix-agent  
   58  systemctl status zabbix-agent.servuce  
   59  systemctl status zabbix-agent.service  
   60  find / -name zabbix_agentd.conf  
   61  nano /etc/zabbix/zabbix_agentd.conf  
   62  sytemctl restart zabbix_agent.service  
   63  systemctl restart zabbix_agent.service  
   64  systemctl restart zabbix-agent.service  
   65  systemctl status zabbix-agent.service  



     <img width="1199" height="858" alt="image" src="https://github.com/user-attachments/assets/306b3b3b-8e7b-4d26-ab3d-66770c66785f" />  
     <img width="1320" height="866" alt="image" src="https://github.com/user-attachments/assets/cd5e1c16-6402-4d05-a5b6-b91b1c16a41b" />  
     <img width="1554" height="649" alt="image" src="https://github.com/user-attachments/assets/1a26c231-4f89-4793-9583-b96276efda3e" />







```
Поле для вставки кода...
....
....
....
....
```

`При необходимости прикрепитe сюда скриншоты
![Название скриншота](ссылка на скриншот)`
