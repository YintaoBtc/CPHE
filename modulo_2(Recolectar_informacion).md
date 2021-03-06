# RECOLECTAR INFORMACION

## Footprinting, information gathering, fingerprinting...

## Herramientas de uso online con material publico:
1. Whois --> en consola seria: 
    - whois dominio
    - ping dominio --> obtenemos la ip del objetivo
    - traceroute dominio --> saltos hasta la ip objetivo
2. Plugins:
    - firefox --> tools --> addons
    - wappalyzer --> indica estructura de la pagina
    - ip address and domain information --> informacion ip, whois, ...
    - Cookie Editor
        - owasp mantra:
        1. apt-get install owasp-mantra-ff
        2. owasp-mantra-ff --> vamos a la pagina abriendo el navegador
        3. abajo a la derecha sale la barra oculta pasando el raton por encima. 
        4. P --> Passive Recon
    
### Comprobando Passive Recon:
bing
ip:<IP> --> muestra todas las paginas dentro de esa misma ip

`dnsenum dominio` --> conseguimos las dns

`theharvester -d dominio -l 500 -b google` --> muestra los 500(maximo) correos de un dominio en el -b (google)

`whatweb -v dominio`  --> misma informacion que wappalyzer pero en consola

`wafw00f http://dominio` --> peticiones para que salten firewall o antivirus.

`dirb http://dominio` --> usa un diccionario por defecto para encontrar directorios 

## FOCA
https://www.elevenpaths.com/es/labstools/foca-2/index.html

Solo para Windows. 

Nuevo proyecto --> nombre y dominio

Search All

Download All

Extract metadatos 

Version online para archivos --> https://www.elevenpaths.com/labstools/metashield-analyzer-2/index.html


## Escaneo interno
Nmap --> escaneo de ips/puertos de una red 

`ip address`

`nmap -v ip/24`

`service apache2 start` --> en kali

`netstat -antp` --> comprobar que apache esta up\

Desde un navegador buscar la web de apache en 127.0.0.1. Lanzamos nmap otra vez para comprobar que encuentra el apache, puerto 80

## Anonimato

1. Tor Browser 
- cebolla options 

2. VPN
- protonvpn
- mullvad

## Nmap
`ifconfig`\
`ip address`

`nmap -v -Pn 192.168.1.0/24` --> verbose y ping. Silencioso.\
`zenmap`  --> parte grafica de nmap\
`nmap -v -sS 192.168.1.0/24` --> Silencioso\
`nmap -v -sT 192.168.1.0/24` --> Mas ruidoso con scan

`nmap -v -O 192.168.1.0/24` --> identificar sistema operativo\
`nmap -v -O -sV 192.168.1.0/24` --> versiones de los protocolos --> carga 43 scripts\
`nmap -v -A 192.168.1.0/24` --> muy ruidoso y muy completo --> carga 148 scripts\
`nmap -A -p- -v 192.168.1.123` --> escanear todos los puertos --> -p1-65535 o -p-\
`nmap -p21000 -sV 192.168.1.123` --> escanea el puerto 21000 solo\


## Enum linux
`enum4linux 192.168.1.123`


## Analisis de vulnerabilidades

1. Nikto
- Vulnerabilidades en aplicaciones o servidores web --> 80/443
- Muy ruidosa y lenta. 
- `nikto -h http://192.168.1.123:20000`

2.  Owasp ZAP
- Aplicaciones webs
- Arrancar ZAP, automated scan y añadir URL a atacar
- Esto es intrusivo, hace falta permiso. 

3. Nessus
- `apt update && apt upgrade`
- https://es-la.tenable.com/products/nessus/select-your-operating-system --> download 64 bit
- `sudo dpkg -i nessus.deb` 
- `/etc/init.d/nessusd start`
- kali:8834
- https://www.tenable.com/products/nessus/activation-code --> nessus activation code 
- update plugins 
- `update-rc.d nessusd enable` --> start when Kali Linux boots

4.  Accunetix
- De pago. 
- Para aplicaciones webs


5. Burpsuite
- Activar proxy firefox
- open menu --> preferences --> search proxy settings --> manual confi
- proxy http: 127.0.0.1    
- port: 8080

6. Joom scan
`joomscan -u <target>`

7. CMSmap
`./cmsmap.py <target> -f W -F` --> escaneo full sobre WP

8. WPscan
`wpscan --url <target.com> -e u ap`
