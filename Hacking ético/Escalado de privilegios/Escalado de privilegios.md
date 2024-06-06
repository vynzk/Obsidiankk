[[Hacking ético]] 
# Comandos útiles para escalado de privilegios

1. **sudo**: Verificar si el usuario actual tiene permisos para ejecutar comandos con sudo y sin necesidad de contraseña:

    ```bash
    sudo -l
    
    ```

2. **Buscar archivos SUID y SGID**: Archivos con permisos especiales pueden ser explotados para ejecutar comandos con los privilegios del propietario o del grupo. Puedes encontrar estos archivos con:

    ```bash
    find / -type f \\( -perm -4000 -o -perm -2000 \\) -exec ls -l {} \\;
    
    ```

3. **Ver procesos en ejecución**: A veces, procesos en ejecución pueden tener permisos elevados. Puedes revisar los procesos en ejecución con:
    
    ```bash
    ps aux
    
    ```

4. **Buscar archivos con permisos inseguros**: Archivos con permisos de escritura por todos los usuarios pueden ser explotados para modificar archivos críticos del sistema.

    ```bash
    find / -type f -perm -o=w
    
    ```

5. **Examinar archivos de configuración**: A menudo, los archivos de configuración pueden contener contraseñas u otras credenciales almacenadas en texto plano. Puedes examinar estos archivos con:

    ```bash
    cat /etc/passwd
    
    ```

6. **Examinar logs de sistema**: Los logs pueden contener información útil sobre el sistema y los usuarios que acceden a él. Puedes examinar los logs de autenticación con:

    ```bash
    cat /var/log/auth.log
    
    ```

7. **Uso de herramientas especializadas**: Herramientas como LinEnum o LinPeas pueden ayudar a automatizar la búsqueda de vulnerabilidades y la escalada de privilegios en sistemas Linux.
