# Домашнее задание к занятию "`Уязвимости и атаки на информационные системы`" - `Стрекозов Владимир`
### Задание 1
Скачайте и установите виртуальную машину Metasploitable: https://sourceforge.net/projects/metasploitable/.  
Это типовая ОС для экспериментов в области информационной безопасности, с которой следует начать при анализе уязвимостей.  
Просканируйте эту виртуальную машину, используя nmap.  
Попробуйте найти уязвимости, которым подвержена эта виртуальная машина.  
Сами уязвимости можно поискать на сайте https://www.exploit-db.com/.   
Для этого нужно в поиске ввести название сетевой службы, обнаруженной на атакуемой машине, и выбрать подходящие по версии уязвимости.  
Ответьте на следующие вопросы:  
Какие сетевые службы в ней разрешены?  
Список открытых сетевых портов:  
![](https://github.com/Svalker1989/Inforamtion_security/blob/main/Z1.PNG)  
Какие уязвимости были вами обнаружены? (список со ссылками: достаточно трёх уязвимостей)  
1.  Exploit for the 2.2 linux-kernel TCP/IP weakness
[1](https://www.exploit-db.com/exploits/237)  
2. Служба NFS
  [2](https://www.exploit-db.com/exploits/42305)  
4. RPCBind
   [3](https://www.exploit-db.com/exploits/41974)  
### Задание 2
Проведите сканирование Metasploitable в режимах SYN, FIN, Xmas, UDP.  
Запишите сеансы сканирования в Wireshark.    
Ответьте на следующие вопросы:  
Чем отличаются эти режимы сканирования с точки зрения сетевого трафика?  
Как отвечает сервер?  
Режим SYN - режим опроса портов по протоколу TCP, когда посылается пакет с флагом SYN на определенный порт  
Возможные ответы:  
* SYN/ACK(порт открыт)
* RST(порт закрыт)
* нет ответа (порт отфильтрован)
FIN - пакеты отправляются с флагом FIN. Такое сканирование может быть менее заметным и может помочь обойти некоторые фаерволы  
Возможные ответы:  
* No response received (even after retransmissions)	open|filtered
* TCP RST packet	closed
* ICMP unreachable error (type 3, code 1, 2, 3, 9, 10, or 13)	filtered
Xmas - пакеты отправляются с флагами FIN, PSH, and URG.  
Возможные ответы:  
* No response received (even after retransmissions)	open|filtered
* TCP RST packet	closed
* ICMP unreachable error (type 3, code 1, 2, 3, 9, 10, or 13)	filtered
UDP - сканирование портов происходит по протоколу UDP.  
Возможные ответы:  
* Any UDP response from target port -	open
* No response received (even after retransmissions) - port open|filtered
* ICMP port unreachable error (type 3, code 3) -	port closed
* Other ICMP unreachable errors (type 3, code 1, 2, 9, 10, or 13) - port	filtered

  
