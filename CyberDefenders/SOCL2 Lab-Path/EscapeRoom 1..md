- --
- Tags: #wireshark #cyberdefenders #escaperoom_lab #zui #brim #networkminer #upx
- --
¿Qué servicio utilizó el atacante para acceder al sistema?

![](../../Fotos/Pasted%20image%2020260710121934.png)

![](../../Fotos/Pasted%20image%2020260710121938.png)

**Respuesta:** SSH

¿Qué tipo de ataque se utilizó para acceder al sistema? (una palabra)

![](../../Fotos/Pasted%20image%2020260710121952.png)

**Respuesta:** BruteForce

¿Qué herramienta pudo usar el atacante para realizar este ataque?

**Respuesta** Hydra

¿Cuántos intentos fallidos hubo?

![](../../Fotos/Pasted%20image%2020260710121655.png)

**Respuesta:** 52

¿Qué credenciales (usuario:contraseña) se usaron para acceder a ella? Consulta shadow.log y sudoers.log.

`C:\Users\defen\Desktop\john\john-1.9.0-jumbo-1-win64\run\john.exe --wordlist=C:\Users\defen\Desktop\rockyou\rockyou.txt C:\Users\defen\Desktop\temp_extract_dir\EscapeRoom\shadow.log`

![](../../Fotos/Pasted%20image%2020260710131320.png)

**Respuesta:** forgot:manager

¿Qué otras credenciales (usuario:contraseña) podrían haberse utilizado para acceder también tienen privilegios SUDO? Consulta shadow.log y sudoers.log.

![](../../Fotos/Pasted%20image%2020260710132023.png)

**Respuesta:** sean:spectre

¿Cuál es la herramienta que se utiliza para descargar archivos maliciosos en el sistema?

![](../../Fotos/Pasted%20image%2020260710134006.png)

**Respuesta:** Wget

¿Cuántos archivos descarga el atacante para instalar malware?

![](../../Fotos/Pasted%20image%2020260710135145.png)

![](../../Fotos/Pasted%20image%2020260710135229.png)

![](../../Fotos/Pasted%20image%2020260710140115.png)

**Respuesta:** 3

¿Cuál es el principal malware en el hash MD5?

![](../../Fotos/Pasted%20image%2020260710141254.png)

![](../../Fotos/Pasted%20image%2020260710141045.png)

![](../../Fotos/Pasted%20image%2020260710141053.png)

![](../../Fotos/Pasted%20image%2020260710141108.png)

**Respuesta:** 772b620736b760c1d736b1e6ba2f885b

¿Qué archivo ha modificado el script para que el malware se inicie al reiniciarse?


![](../../Fotos/Pasted%20image%2020260710141602.png)

**Respuesta:** /etc/rc.local

¿Dónde guardaba el malware los archivos locales?

![](../../Fotos/Pasted%20image%2020260710142735.png)

**Respuesta:** /var/mail/

¿Qué falta en ps.log?

![](../../Fotos/Pasted%20image%2020260710143039.png)

**Respuesta:** /var/mail/mail

¿Cuál es el archivo principal que solía eliminar esta información de ps.log?

![](../../Fotos/Pasted%20image%2020260710143753.png)

**Respuesta:** sysmod.ko

Dentro de la función principal, ¿cuál es la función que causa las peticiones a esos servidores?

![](../../Fotos/Pasted%20image%2020260710150453.png)

![](../../Fotos/Pasted%20image%2020260710160550.png)

![](../../Fotos/Pasted%20image%2020260710211413.png)

Siguiendo el call llamado **requestFile** ..

![](../../Fotos/Pasted%20image%2020260710211513.png)

**Respuesta:** requestFile

Una de las IPs con las que el malware contactó empieza con 17. Proporciona la IP completa.

![](../../Fotos/Pasted%20image%2020260710211817.png)

![](../../Fotos/Pasted%20image%2020260710212038.png)

**Respuesta:** 174.129.57.253

¿Cuántos archivos ha solicitado el malware a servidores externos?

![](../../Fotos/Pasted%20image%2020260710212339.png)

**Respuesta:** 9

¿Cuáles son los comandos que el malware recibía de los servidores atacantes? Formato: separados por comas en orden alfabético

![](../../Fotos/Pasted%20image%2020260710215638.png)

![](../../Fotos/Pasted%20image%2020260710215618.png)

**Respuesta:** NOP,RUN