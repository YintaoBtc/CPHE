# INTRODUCCION

## Perfil Hacking Etico

1. Infraestructura y redes
2. Sistemas operativos
3. Desarrollo de Software y database(no es un requisito)

- Entusiasta(Pasion)
- Investigador
- Actualizado
- Saber Ingles
- Autonomo y trabajo en equipo
- Etica profesional


## Tipo de Analisis:

* Black Box --> El analista no tiene ningun conocimiento del objetivo
* Gray Box --> El analista conoce muy poco del objetivo
* White Box --> Ambas partes saben que test y cuando se realizaran. 


## Tipo de auditorias:

* Externa --> Se realiza desde el exterior del objetivo
* Interna --> Se realiza en casa del cliente, internamente. Se puede externa con VPN(no recomendable)
* Web --> Se realiza a una pagina web, siendo externa.
* Wifi --> Se realiza a una red wifi tanto dentro como fuera del estblecimiento del objetivo
* Aplicacion --> Se realiza sobre una aplicacion para encontrar errores o bugs
* Movil --> Se realiza sobre dispositivos moviles de una empresa



## Arquitecturas en redes

## Modelo OSI

1. Fisica -->Cables, radiofrecuencias, hubs, AP
2. Enlace de datos -->Ethernet, PPP, Frame Delay // switches, mac address
3. Red --> Direccionamiento IP, Enrutamiento // 192.168.1.195
4. Transporte --> TCP-UDP 
5. Sesion --> Establece, administra y termina sesiones entre host
6. Presentacion --> Estandariza la forma en que se representan los datos
7. Aplicacion --> aplicaciones, http, FPT, SSH, SMTP, POP3



### IP capa 3:

- Direccion ip: direcciones binarias de 32 bits son un conjunto de 4 octetos. Asi se identifica un host dentro de una red.

- Mascara de red: Que porcion de la red esta siendo utilizada para la ip y cual para el host.

- Gateway: Dispositivo de la red por donde se envian los paquetes que tienen destino la red exterior/interior


### POC Conexion
`netstat -antp // ps -A | grep sshd` --> Saber si SSH esta corriendo.

`ifconfig` --> desde kali para saber la ip

`fpt <ip kali>` --> conectar por ftp a kali


## MODO NAT Y MODO BRIDGE

1. Modo Nat:
    - 1.El router se encarga de cambiar la ip local a local externa. 
    - No es recomendable para implementar un Firewall Perimetral

2. Modo Bridge
    - Ideal para montar un firewall. 
    - Todo es administrado por el firewall antes de salir al router(ISP).
    - Añade ip del rango de red del host

## CREANDO EL LABOTORIO

Instalamos Vmware workstation Pro

Añadimos Kali Linux como una nueva maquina virtual.

Instalamos VMware Tools

Menu VM --> install wmware tools --> Extraemos la carpeta 
~~~
cd Desktop
ls
cd vmware-tools-distrib
ls
./vmware-install.pl
reboot
~~~
Hacer snapshot de Kali

