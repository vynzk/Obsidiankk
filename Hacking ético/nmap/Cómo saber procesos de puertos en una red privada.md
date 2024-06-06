[[Nmap]]
Para identificar qué servicios y procesos están corriendo en puertos específicos de una máquina utilizando Nmap, no puedes obtener directamente los procesos (como lo hacen comandos como `netstat` o `lsof` en sistemas locales), pero puedes usar varias opciones de Nmap para identificar qué servicios están activos en esos puertos, lo cual puede darte una buena idea de los procesos subyacentes.

A continuación te muestro cómo usar Nmap para identificar servicios:

### 1. Escaneo de Servicios con Nmap

Nmap puede realizar un escaneo de detección de servicios que intenta identificar qué servicio (y a veces qué software y versión) está corriendo en cada puerto abierto. Esto se hace usando la opción `-sV`.

```bash
sudo nmap -sV [dirección IP o rango de IPs]
```

Donde:
- `-sV`: Activa la detección de la versión del servicio.

Por ejemplo:

```bash
sudo nmap -sV 192.168.1.1
```

Este comando escaneará la máquina con dirección IP 192.168.1.1 y tratará de identificar información sobre los servicios que corren en los puertos abiertos.

### 2. Escaneo Agresivo

Para un análisis más exhaustivo, puedes combinar varias opciones:

```bash
sudo nmap -sS -sV -A -T4 [dirección IP o rango de IPs]
```

Donde:
- `-sS`: Realiza un escaneo SYN que es rápido y menos intrusivo.
- `-sV`: Detecta la versión de los servicios.
- `-A`: Activa la detección del sistema operativo, versión de servicios, script de escaneo y traceroute.
- `-T4`: Establece el nivel de temporización para un escaneo más rápido.

Por ejemplo:

```bash
sudo nmap -sS -sV -A -T4 192.168.1.1
```

### 3. Uso de Scripts NSE

Nmap también tiene una capacidad potente para utilizar scripts (NSE - Nmap Scripting Engine) que pueden ayudar a descubrir aún más detalles sobre los servicios corriendo en los puertos. Por ejemplo, puedes utilizar scripts específicos para extraer información de ciertos tipos de servicios:

```bash
sudo nmap --script=[nombre-del-script] [dirección IP o rango de IPs]
```

Por ejemplo, para ver detalles sobre un servidor HTTP, podrías usar:

```bash
sudo nmap --script=http-title 192.168.1.1
```

Este comando intentará obtener el título de cualquier página web servida por el puerto HTTP estándar de la dirección IP especificada.