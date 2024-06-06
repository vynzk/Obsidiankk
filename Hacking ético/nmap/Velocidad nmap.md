[[Nmap]]
Aumentar la velocidad de escaneo de Nmap puede ser esencial en ciertas situaciones donde el tiempo es un factor crítico. Sin embargo, es importante equilibrar la velocidad con la precisión y evitar generar demasiada carga en la red o ser detectado fácilmente por sistemas de detección de intrusos. Aquí hay algunos métodos para aumentar la velocidad de escaneo con Nmap:

### 1. Seleccionar el tipo de escaneo adecuado
El tipo de escaneo que elijas puede influir en la velocidad:
- **Escaneo SYN (`-sS`)**: Es más rápido y sigiloso que un escaneo completo TCP (`-sT`).
- **Escaneo UDP (`-sU`)**: Generalmente más lento y menos eficiente que el escaneo SYN, pero puedes combinarlo con SYN (`-sS -sU`) para cubrir ambos protocolos simultáneamente.

### 2. Ajustar las opciones de tiempo (`-T<0-5>`)
Nmap tiene varias configuraciones de tiempo predefinidas que controlan la velocidad de escaneo:
- **`-T0`**: Paranoico.
- **`-T1`**: Sigiloso.
- **`-T2`**: Cuidadoso.
- **`-T3`**: Normal.
- **`-T4`**: Agresivo.
- **`-T5`**: Despiadado.

Para aumentar la velocidad, puedes usar `-T4` o `-T5`, aunque esto puede aumentar la detección por sistemas de seguridad.

### 3. Ajustar el número de puertos simultáneos (`--min-parallelism` y `--max-parallelism`)
Estas opciones controlan cuántos puertos son escaneados simultáneamente.
- **`--min-parallelism <num>`**: Establece el mínimo número de puertos simultáneos.
- **`--max-parallelism <num>`**: Establece el máximo número de puertos simultáneos.

### 4. Controlar los tiempos de espera (`--min-rtt-timeout` y `--max-rtt-timeout`)
Reducir los tiempos de espera puede acelerar el escaneo, aunque puede llevar a más falsos negativos.
- **`--min-rtt-timeout <time>`**: Establece el tiempo de espera mínimo.
- **`--max-rtt-timeout <time>`**: Establece el tiempo de espera máximo.

### 5. Limitar el número de retransmisiones (`--max-retries <num>`)
Reducir el número de retransmisiones puede acelerar el escaneo, pero puede resultar en menos precisión.
- **`--max-retries <num>`**: Limita el número de retransmisiones.

### 6. Desactivar el escaneo de ping (`-Pn`)
Si estás seguro de que el host está activo, puedes desactivar el escaneo de ping para ahorrar tiempo.
- **`-Pn`**: Desactiva el escaneo de ping.

### 7. Otras optimizaciones
- **`-n`**: Desactiva la resolución de DNS para ahorrar tiempo.
- **`--host-timeout <time>`**: Establece un límite de tiempo para cada host.
- **`--scan-delay <time>` y `--max-scan-delay <time>`**: Controlan los retrasos entre envíos de paquetes.

### Ejemplo de comando optimizado
```sh
nmap -sS -T4 --min-parallelism 100 --max-parallelism 100 --min-rtt-timeout 50ms --max-rtt-timeout 200ms --max-retries 2 -Pn -n -p- <target>
```

Este comando realiza un escaneo SYN agresivo en todos los puertos de un objetivo específico, con varias opciones ajustadas para maximizar la velocidad.

Recuerda que aumentar la velocidad puede tener un impacto negativo en la precisión y aumentar la probabilidad de ser detectado. Usa estos ajustes con cuidado y considera el contexto y las políticas de tu entorno.