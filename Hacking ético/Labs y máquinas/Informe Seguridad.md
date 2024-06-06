
# Encontrar la máquina
requeridos
- [[Escalado de privilegios]]
- [[Cómo escanear la red privada y saber el SO]] 
``` bash
192.168.1.212
```
![[Pasted image 20240604153434.png]]

```
nmap -sSUC -p111 192.168.1.212

sudo nmap -p- -sV -O 192.168.1.212
```

![[Pasted image 20240604155815.png]]

usar dirb
https://www.youtube.com/watch?v=W3-JGk7H2Cg

exploit-CVE-2016-10033
https://github.com/opsxcq/exploit-CVE-2016-10033

"phpmailer/phpmailer": "~5.2" 5.2.16

https://www.youtube.com/watch?v=sqQ4aEvJO44 phpmailer
![[Pasted image 20240604163727.png]]
https://legalhackers.com/advisories/PHPMailer-Exploit-Remote-Code-Exec-CVE-2016-10033-Vuln.html
![[Pasted image 20240604164740.png]]

exploit! https://legalhackers.com/exploits/CVE-2016-10033/10045/10034/10074/PwnScriptum_RCE_exploit.py

![[Pasted image 20240604170005.png]]