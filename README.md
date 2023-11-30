# Домашнее задание к занятию "Уязвимости и атаки на информационные системы" - `Bazylev Artem`


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


### Задание 1. 

Сетевые службы:

| PORT   | STATE | SERVICE      | VERSION                                       |
|--------|-------|--------------|-----------------------------------------------|
| 21/tcp | open  | ftp          | vsftpd 2.3.4                                  |
| 22/tcp | open  | ssh          | OpenSSH 4.7p1 Debian 8ubuntu1 (protocol 2.0)  |
| 23/tcp | open  | telnet       | Linux telnetd                                 |
| 25/tcp | open  | smtp         | Postfix smtpd                                 |
| 80/tcp | open  | http         | Apache httpd 2.2.8 ((Ubuntu) DAV/2)            |
| 111/tcp| open  | rpcbind      | 2 (RPC #100000)                               |
| 139/tcp| open  | netbios-ssn  | Samba smbd 3.X - 4.X (workgroup: WORKGROUP)   |
| 445/tcp| open  | netbios-ssn  | Samba smbd 3.X - 4.X (workgroup: WORKGROUP)   |
| 512/tcp| open  | exec         | netkit-rsh rexecd                             |
| 513/tcp| open  | login?       |                                               |
| 514/tcp| open  | tcpwrapped   |                                               |
| 1099/tcp| open | java-rmi     | GNU Classpath grmiregistry                   |
| 1524/tcp| open | bindshell    | Metasploitable root shell                    |
| 2049/tcp| open | nfs          | 2-4 (RPC #100003)                            |
| 2121/tcp| open | ftp          | ProFTPD 1.3.1                                |
| 3306/tcp| open | mysql        | MySQL 5.0.51a-3ubuntu5                       |
| 5432/tcp| open | postgresql   | PostgreSQL DB 8.3.0 - 8.3.7                  |
| 5900/tcp| open | vnc          | VNC (protocol 3.3)                           |
| 6000/tcp| open | X11          | (access denied)                               |
| 6667/tcp| open | irc          | UnrealIRCd                                   |
| 8009/tcp| open | ajp13        | Apache Jserv (Protocol v1.3)                 |
| 8180/tcp| open | http         | Apache Tomcat/Coyote JSP engine 1.1          |




Обнаруженные уязвимости:
1. Уязвимость в ProFTPD 1.3.1: [Ссылка на Exploit Database](https://www.exploit-db.com/exploits/15449)
2. Уязвимость в MySQL 5.0: [Ссылка на Exploit Database](https://www.exploit-db.com/exploits/1741)
3. Уязвимость в Apache Tomcat: [Ссылка на Exploit Database](https://www.exploit-db.com/exploits/4162)


### Задание 2.

Режимы сканирования SYN, FIN, Xmas и UDP отличаются друг от друга в том, каким образом они взаимодействуют с целевым сервером и какой сетевой трафик они генерируют.

    SYN сканирование:
        Характеристики трафика: Отправляются только пакеты SYN (открытие соединения).
        Ответ сервера: Если порт открыт, сервер отвечает пакетом SYN/ACK. Если порт закрыт, сервер отвечает пакетом RST.

    FIN сканирование:
        Характеристики трафика: Отправляется только пакет FIN (завершение соединения).
        Ответ сервера: Если порт открыт, сервер может проигнорировать пакет или ответить RST, в зависимости от реализации стека.

    Xmas сканирование:
        Характеристики трафика: Отправляются пакеты с установленными флагами FIN, PSH и URG.
        Ответ сервера: Если порт закрыт, сервер может ответить RST, или проигнорировать пакет, в зависимости от реализации стека.

    UDP сканирование:
        Характеристики трафика: Отправляются пакеты UDP.
        Ответ сервера: Если порт открыт, сервер не отвечает пакетом ICMP (протокол ошибки); если порт закрыт, сервер отправляет пакет ICMP Port Unreachable.









