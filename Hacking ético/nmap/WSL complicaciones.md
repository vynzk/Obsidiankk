[[Nmap]]
Lo que pasa es que WSL tiene su propia red privada, por lo que hay que usar la ip de tu OS anfitrión para escanear, pero ese sería el único problema. 
``` bash
ipconfig
```
en la shell de windows daria la red local que tienes que usar ;)