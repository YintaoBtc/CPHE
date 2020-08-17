# Password Cracking

# Wordlist
cewl -v www.librosbitcoin.es -w wordlibros --> hace un diccionario con palabras de la web

crunch 2 4 abcABC123! -o crunchword  --> Contraseñas de 2 a 4 o:output

# Hashcat
Lenta, multihilo, calienta mucho la grafica, hace falta grafica buena(2g o mas), interfaz grafica...

Saber que tipo de hash --> hashidentifier, https://onlinehashcrack.com/hash-identification.php

# Hydra
Modo grafico(xhydra) o modo consola. Puede lanzar pruebas contra varios objetivos

`hydra -l msfadmin -P /root/rockyou.txt ssh://192.168.1.123 -vV -t 4 -e ns`

xhydra --> interfaz grafica

# Medusa
Más lento que hydra

medusa -d --> modulos de medusa

`medusa -h 192.168.1.123 -v 10 -M ftp -u root -P rockyou.txt`

# Herramientas para Hash
1. Cain 
2. Script python
3. Tipo de hash:
    * MD2
    * MD4
    * MD5
    * SHA-1
    * SHA-2(256)
    * SHA-2(384)
    * SHA-2(512)
    * RIPÈMD-160
    * LM
    * NT
    * CISCO PIX
    * VNC Hash

# Ophcrack
Windows vista y XP

https://ophcrack.sourceforge.io/ --> tambien version live

https://ophcrack.sourceforge.io/tables.php --> importamos tablas a ophcrack

/etc/passwd --> copiamos hash

load --> new hash 

https://crackstation.net/ --> crackeo contraseñas onlinehashcrack

onlinehashcrack.com --> por 5€ servicio

# Jhon the reaper
`john --wordlist /root/rockyou.txt pass.txt`

~~~
uname -a 
id
nano /etc/passwd
nano /etc/shadow
unshadow /etc/passwd /etc/shadow > passlinux
john passlinux
~~~


# Auditoria Wifi
WAP --> Wireless Access Point --> nombre de la red SSID --> todos los dispositivos comparten SSID --> es publico

Tarjetas:
* Alfa.com.tw 
* wifisky

# Aircrack POC
`aircrack-ng` 

`ifconfig` --> wlan0 

`iwconfig` --> tarjetas en modo monitor

`airmon-ng start wlan0`

`airmon-ng check kill` --> mata todos los procesos

`airodump-ng wlan0mon` --> buscar redes inhalambricas al alcance

`aireplay-ng --deauth 50 -a <BSSID> wlan0mon` --> 50 paquetes

`iwconfig wland0mon channel numero` --> cambiar de canal

`airodump-ng -c 11 --bssid BSSID -w captura wland0mon` --> c: channel w:write caputramos handshake

`aircrack-ng -w /usr/share/wfuzz/wordlist/big.txt -b BSSID /root/captura-01.cap` --> sacar contraseña del handshake con wordlist

# Airgeddon
`./airgeddon`

Interfaz de consola con aircrack y mas.

"Practica Evil Twin +5 points"

