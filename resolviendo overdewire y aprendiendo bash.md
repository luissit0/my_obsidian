resolviendo overdewire y aprendiendo bash


bandit0 

para conectarte a un servidor usuario remoto

ssh <<nombre del usuario>>@[direacion web o ip] -p 2220
ssh bandit0@bandit.labs.overthewire.org -p 2220

de halli te pedira la contrasenya es: bandit0

hay una contrasenya dentro poner: 
cat [el fichero] // para ver la consetrasenya adentro

para ver que version de linux estas:
lsb_release -a
   o
cat /etc/*-release
  o   
uname -a

sudo apt install screenfetch
screenfetch

sudo apt install neofetch
neofetch


felicidades!! la contrasenya para el siguiente nivel1 es:
NH2SXQwcBdpmTEzi3bvBHMM9H66vVXjL

----------------------------------
bandit nivel 1
la contrasenya actual es: 
NH2SXQwcBdpmTEzi3bvBHMM9H66vVXjL


dentro de bandit0 habra un achivo del cual usas el comando cat
para ver adentro y alli hay un contrasenya
usala para entrar al siguiente nivel a bandit1


felicidades..!! el contrasenya descubierta para pasar de nvile es:
rRGizSaX8Mk1RTb1CNQoXTcYZWU6lgzi 
------------------------------------------
bandit nivel 2
contrasenya actual es:
rRGizSaX8Mk1RTb1CNQoXTcYZWU6lgzi

leccion:

el comando: cat es para ver que hay dentro de un archivo

cat [directorios]

hay signos que bash lo interpreta como simbolo especiales que llaman a comoando cuando ponen esto simbolos especiales como nobre de archivo o direactorio no los puede abrir y para abria o ver lo de andentro hay un truco: por ejemplos si el direactorio se llama - no funcion cd - porque
- es un activador de opciones en bash.
hay un truco con cat :
si pones cat ./-
   o
cat < -
   o
cat /home/bandit1/-
cat /home/bandit1/* //criterio ver todo lo de adentro
  // es quivalente pwd es print word direatory donde esta el direatorio
  actual y el $() en bash es una variable temporal no asignada
cat $(pwd)/-
cat $(pwd)/* 

pasword !! felicitaciones..!! del siguiente nivel 3
aBZ0W5EmUfAf7kHTQeOwd8bauFJ2lAiG
---------------------------------------------------
bandit nivel3
contrasenya del nivel: aBZ0W5EmUfAf7kHTQeOwd8bauFJ2lAiG

el archivo tiene espacios y no se puede entrar con un simple cd
porque bash lo reconoce como si fueran vario argumentos

para resolver el problema puede comentarlo o poner scape inverso
al final de cada palabra

cat space\ in\ this\ filename
  o
cat "space in the filename"
  o 
cat 'space in the filename'    

otro truco no preciso dependiendo de como esta ese directorio

cat sp* // ver todo lo que comiensa con sp
cat *ame  // ver todo lo que termina en ame
cat  *this* // ver todo lo que esta en el medio que contenga "this"
cat * //si es el unico fichero que hay

tambien funciona con el truco anterior de ruta absoluta
cat /home/bandit2/*
cat $(pwd)/*

contrasenya descubierta para pasar al siguiente nivel es:
2EW7BBsr6aMMoJ2HjW067dm8EgX26xNe 
"felicidades!!"

--------------------------------------------------
bandit nivel4 
contrasenya del nivel actual: 2EW7BBsr6aMMoJ2HjW067dm8EgX26xNe 

la contrasenya se encuentra en un directorio con un archivo oculto 
que no se puede ver con simple: ls sino con: ls -a

los archivos oculto comiensancon un puneto ejemplo .hidden

cat .hidden

tambien puede usar el comando find y un inicial
find .
find .* //buscar de todo desde un nivel atras del directorio
find . -type f // fuscat solo tipo ficheros

leccion adicional comandos:
para que salga de forma formateada personalisada el find

find . -type f -printf "%f\t%p\t%u\t%g\t%m\n" |column -t
                       %f archivos
                       t%p mostrar los archivo desde su ruta absoluta en forma tabulada
                       t%u en forma tabulada el usuraio propietario
                       t%g en forma tabulada el grupo que pertenece
                       t%m en forma tabulada el modo o permiso de forma de uso de chmod a nuvel numerico 777 etc
el | column -t
 hace que se muestre todo ordenado en columna parejas si no sale todo feo.

find . -name .hidden                        

el comando | que le llaman pipe es para ejecutar en "paralelo o simulacion" otro comando dentro de la misma linea
find . -name .hidden | cat /home/bandit3/inhere/.hidden

pero para referenciar el nuevo comando al argumento anterior se pone xargs para no escribir  mucho en caso de un direatorio muy largo boiler plate.
find . -name .hidden | xargs cat


find . -type f | xargs cat

como leer el ls -la
el usuario propietario siempre esta en la primera columna

				     usuario root, gruop, others
						       u     g     o
[-(archivo) o d(directorio)] [rwx] [rwx] [rwx]
maxima combinacion en bnar :  111   111   111 (maximo valor en binario) 
							  421   421   421 (se suma el valor de posicional del binario)
 en hexadecimal         chmod  7     7     7  (activar todos los permisos con numeros)

propietario o grupo u otros  rwx r(read) w(write) x(executable)
rw_           r--      r-- 

para cambia los permisos
chmod o+rwx [el fichero]  // el + es para dar permiso y el - quitar permiso
      o+ es otros
      u+ es de usuario actual
      g+ es del grupo actual
     [nombre de ususario]+ el usuario especifico
chmod  u+rwx,g+rwx,o-xw [el fichero]  

para cambiar grupos es:
chgr [nombre del grupo] [el fichero]      

hay privilegios especiales avanzados: 
chattr(change attributes) y lsattr(list attributes)

permiten asignar flags o banderas a fichero especiales 
que nisiquiera root lo pueda eliminar

lsattr [directorio o fichero]
para ver cuales son sus atributo especiales.

chattr +i -v file.txt

en: man chattr puedes ver todo los atrobutos
por ejemplo el i es para que no sea modificable 
y etc

como adivinaras + es para dar y - para quitar el atributo
este es el patron de uso:
chattr [-RVf] [-+=aAcCdDeijPsStTuFx] [-p project] [-v version] files.

usar el comando: file
para ver que tipo de acrhivo es.
// file no sebasa en la extencion .txt u otros sino se basa por sus primeros
digitos exadecimales y hay numero magicos en el inicio de un texto que pueden
hacer cambiar el tipo de archivo. ejmeplo en un txt la primera fila poner GIF8*;
y saldra que es un gif y no un txt

comando para editar hexadecimal:
hexeditor
// lo que lista con que tipo de archivos se esta trantando son los primero bites protocolos de identificacion de programas por disenyo de convencion. los primeros 4de 2 digitos headecimales al parecer era.

find . -name -file* | xargs file

si agregas time al inicio // puede ver el tiempo de demora de computo del algoritmo.
time find . -name -file* | xargs file
// comparar cual scripting es mas rapido o optimisado
time file inhere/*

luego para ver
time cat inhere/-file07
time find . -name  -file07 | xargs cat
time cat $(find . -name -file07)

contrasenya descubierta para pasar al siguiente nivel es:
lrIWWI6bB37kxfiCQZqUdOIYfr6eEeqR
"felicidades!!"

------------------------------------------------------
 bandit nivel 5
 contrasenya actual del nivel es:
 lrIWWI6bB37kxfiCQZqUdOIYfr6eEeqR

The password for the next level is stored in a file somewhere under the inhere directory and has all of the following properties:

    human-readable
    1033 bytes in size
    not executable
//un truquito
con control r //sale con autorelleno de comando anteriores para ver

solucionar con el comando find y sub opciones o metodos internos o asociados:

time find . -type f -readable ! -exceutable -size 1033c | xargs cat
time cat $(find . -type f -readable ! -executable - size 1033c) // esta salio mas rapido

-type f significa que es del tipo fichero
la c del 1033c significa que el numero es en bites si no lo toma de otra cosa no se.
 
si agregas un | xargs //te ayuda a formatear lo que sale sin saltos de linea
time find . -type f -readable ! -executable -size 1033c | xargs cat | xargs
time cat $(find . -type f -readable ! -executable - size 1033c) | xarg

para ver la lineas iniciales es con head las finales con tail
ejemplo:
cat [direactorios o ficheros] | tail -n 2 //mostrar las 2 ultimas lineas
                                head -n 2 //mostrar la x ultimas lineas
                                awk 'NR=2' //mostrar de la linea exactas
                                awk '/palabra/' //muestra la linea con la palabra 

awk puede funcionar de otra forma syntactica como:
awk '/palabra/' data.txt


cat [direactorios o ficheros] | tail -n 2 | sed 's/root/noroot/' //remplasar
	                                            's/root/noroot/g'
	                                            //con el g remplasa todos.

	                                            el primero se remplasa por el segundo
	                                            's/root//g' //quita el root

siquieres buscar estrictamente como inicia la palabra en grep ejemplo:
cat /etc/ghaa | grep "^root" //va con el sobrerito ala do inicial	

y para finalisar con la letra espesifica es on $ ejemplo:
cat /etc/ghaa | grep "^root$" -n 
// el -n me dice que que lina se encuentra lo que se a
elegido o filtrado. el -n luego sirve para el awk.                                           


"felicidades..!!" contrasenya descubierta para el siguiente nivel 6:
P4L4vucdmLnm8I7Vl7jG1ApGSfjYKqJU

-----------------------------------------------------------
bandit6
contrasenya del nivel6:
P4L4vucdmLnm8I7Vl7jG1ApGSfjYKqJU

The password for the next level is stored somewhere on the server and has all of the following properties:

    owned by user bandit7
    owned by group bandit6
    33 bytes in size

find / -user bandit7 -group bandit6 -size 33c 2>/dev/null | xargs cat

el /dev/null es una sona de linux que cambia lo valorea a la referencia de nulo. el 2> es un comando de unix que manda los errores que sale al null

para ver lo que se ha tirado al /dev/null ejm:
cat /etc/passwd 2>/dev/null //para errores lo errores se sirigen alli
cat /etc/passwrd 2>&1 //estos no son errores

firefox > /dev/null 2>&1 // abrir sin que salga informacion en la terminal
firefox > /dev/null 2>&1 & //permite anyadir acciones en el segundo plano si es solo se abrira con segundo plano 
// al abrise al segundo plano puedo anyadir el comando: disown

felicitacione..!! pasastes el nivel 6 a 7!!
contrasenya para pasar al nivel 7:
z7WtoNQU2XfjmMtWA8u5rN4vzqu4v99S

--------------------------------------------------------------------
bandit7 
contrasenya del nivel7 es:
z7WtoNQU2XfjmMtWA8u5rN4vzqu4v99S

Level Goal

The password for the next level is stored in the file data.txt next to the word millionth
Commands you may need to solve this level

man, grep, sort, uniq, strings, base64, tr, tar, gzip, bzip2, xxd

cat data.txt | grep "^millionth"

time grep '/millionh/' data.txt -n 
el -n es para ver en que numero de linea se situa la palabra.
awk 'NR==37262' data.txt

time awk '/palabra/' data.txt | awk '{print $1}'
time awk '/millionth/' data.txt | awk 'NF{print $NF}'

time awk '/millionth/' data.txt | rev //revierte la cadena
time awk '/millionth/' data.txt | rev | awk '{print $1}' | rev

echo "hola   que tal" | cut -d ' ' -f 1


felicitacione..!! pasastes el nivel 7 a 8!!
contrasenya para pasar al nivel 8:
TESKZC0XvTetK0S9xNwm25STk5iWrBvPexit

-------------------------------------------------------------
bandit8
contrasenya del nivel7 es:
TESKZC0XvTetK0S9xNwm25STk5iWrBvPexit

//para ver cuantas lineas hay en el txt
cat data.txt | wc -l 
wc significa word count y -l contar por linea de fila enteras.

The password for the next level is stored in the file data.txt and is the only line of text that occurs only once
Commands you may need to solve this level

cat data.txt | sort //el sort hace un ordenamiento alfabetico ACII 
por defecto

cat data.txt | sort | uniq -u //no va sola porque demoraria demaciado o operaria mal va con el sort.
sort data.txt | uniq -u //funciona mejor en teoria mas rapido.



felicitaciones..!! pasastes el nivel 8 a 9!!
contrasenya para pasar al nivel 8:
EN632PlfYiZbn3PhVK3XOGSlNInNE00t

------------------------------------------------------------
bandit9
contrasenya del nivel9 es:
EN632PlfYiZbn3PhVK3XOGSlNInNE00t

Level Goal

The password for the next level is stored in the file data.txt in one of the few human-readable strings, preceded by several ‘=’ characters.
Commands you may need to solve this level

grep, sort, uniq, strings, base64, tr, tar, gzip, bzip2, xxd

strings data.txt | grep "^===" | tail -n 3

count=1; strings data.txt | grep "===" | while read line; do echo "Line $count $line"; let count+=1;  done | awk 'NR==4'


touch bucle.sh
chmod u+x !$  // el signo este hace que ponga el ultimo argumento anterior
para la nueva funcion.
chmod u+x bucle.sh
nano !$


felicitaciones..!! pasastes el nivel 9 a 10!!
contrasenya para pasar al nivel 10:
G7w8LIi6J3kTb8A7j9LgrywtEUlyyp6s

-------------------------------------------------------------
bandit10
contrasenya del nivel10:
G7w8LIi6J3kTb8A7j9LgrywtEUlyyp6s

Level Goal

The password for the next level is stored in the file data.txt, which contains base64 encoded data

// para codificar un texto a base 64
echo "tranformalo a base 64" | base64 | base64 -d

solucion:
cat data.txt | base64 -d

ejercicios aparte:
cat data.txt | base64 -d | tr ' ' '\n'
// esto hara que cada palabra salga en una linea completa
cat data.txt | base64 -d | tr 'gha' 'daa'
// esto remplaza letra por letra no la palabra como conjunto por lo tanto bucara esos letra 1 o varios y los cambiaran 1 por 1. (parece un encriptor o remplasador con patron)


cat data.txt | base64 -d | sed 's/ /\n/g'
// el comando sed hace simillar solo que nececita /g
para que se aplique para todos (parece mas un selentor con regex)

felicitaciones..!! pasastes el nivel 10 a 11!!
contrasenya para pasar al nivel 11:
6zPeziLdR2RKNdNYFNb6nVCKzphlXHBM

---------------------------------------------------------
bandit11
contrasenya del nivel11:
6zPeziLdR2RKNdNYFNb6nVCKzphlXHBM

Level Goal

The password for the next level is stored in the file data.txt, where all lowercase (a-z) and uppercase (A-Z) letters have been rotated by 13 positions

solucion:
primero poner:
cat data.txt //sale
Gur cnffjbeq vf WIAOOSFzMjXXBC0KoSKBbJ8puQm5lIEi
//comparar con las
27 letras del abcdario: abcdefghijkmnliopqrstuvwxyz
// la primera letra del encriptado es G asi del G a la Z

cat data.txt | tr '[G-ZA-Fg-za-f]' '[T-ZA-St-za-s]'
youtube(https://www.youtube.com/watch?v=RUorAzaDftg&list=PL55pR12vPhpbsZZprEYnEU_2FZhriYbxB&index=2)
Scripting en Bash para principiantes #1 s4vitar
explicacion en el tiempo 1:18:32 
//el comando tr '[A-Zaz]' '[]' permite rotacion 
//el primer argumento va el desde la letra inicial del encriptado la G a la Z, luego el restante A hasta la F. primero en mayusculas y luego en minusculas.oxea remplaza los ecnriptados [rotados] al [segundo argumento que es] el conteo del abcdario rotado desde la g sin contar la g misma 13 letras el 13avo letra es S pero no es inclusivo asi que se pone la siguiente letra la T. entonces pone desde la t hasta la z y luego desde la a hasta la s que es el abcedario rotado y NO EL ENCRIPTADO YA ROTADO.


//la letra inicial es donde se inicia a contar desde el abcedario
por que puede iniciar la rotacion desde cualkier parte del abcdario
asi que desde la G(del encriptado) se cuenta y se salta 13 posiciones del abcdario no incluye g mueves 13 posiciones llega hasta la s va depues de la s la t

cat data.txt | tr '[G-ZA-Fg-za-f]' '[T-ZA-St-za-s]' | awk 'NF{print $NF}'
// resumen
1:19:07 para ser sincero me está poco tranca de entender eso para aclarar lo el primer argumento del tr es el encriptado rotado desde el g y el segundo argumento es el abecedario post rotado desde la g sin contar la g hasta el 13 que sale letra s, pero no cuenta el mismo 13, sino el siguiente que, es el t son límites externos exclusivos no inclusivos. Para los que tienen dudas yo tuve que pausar lo y tratar de hacer. Una explicación por escrito, leer lo si tiene sentido y retroceder, escuchar de nuevo, frase por frase, pensar, unir cuál es el sentido general de todo. Contar y contar el abecedario, etc.


felicitaciones..!! pasastes el nivel 11 a 12!!
contrasenya para pasar al nivel 12:
JVNBBFSmZwKKOP0XbFXOoW8chDz5yVRv

-----------------------------------------------------------
bandit12@@bandit.labs.overthewire.org -p 2220
contrasenya del nivel 12 es:
JVNBBFSmZwKKOP0XbFXOoW8chDz5yVRv


echo "Hola que tal" | xxd
//esto tranforma el texto en hexadecimal

echo "Hola que tal" | xxd | xxd -r
// lo revierte

// otra forma de hacer lo mentiendo y usando variable.
gha=$(echo "Hola que tal" | xxd) | echo $gha
echo $gha | xxd -r

echo "Hola que tal" | xxd -ps
//la opcion -ps del comando xxd

solucion
xxd -r comprimido_hex.txt > data
file data
mv data data.gzip
7z l data.gzip // 7z es universal en ves de recordar gunzip tar -xf etc.
// el l es para ver lo que hay adentro a descomprimir no lo extrae
lo ver en un listado como en el juego dice que esta comprimido muchas veces
hay que ver si hay mas para descomprimir
7z x data.gzip
// la opcion x si es parar extraer el descomprimido

//recuerda que grep busca la palabra name desde esa linea comienza a buscar.
7z l data.gzip | grep "Name" -A 2 // la opcion -A lista a n lineas abajo
                             -B 2 // 2lineas para arriba
                             -C 2 // hace ambas A y C

7z data.gzip | grep "Name" -A 2 | tail -n 1 | awk 'NF{print $NF}'

//ejecutar el script que esta por:
/home/system_os/Documentos/practicas_programacion/bash_pratices/over_the_wire

en el la shell:
./decompresor.sh 

felicitaciones..!! pasastes el nivel 12 a 13!!
contrasenya para pasar al nivel 13:
wbWdlBxEir4CaE8LaPhauuOo6pwRmrDw

----------------------------------------------------------------
ssh bandit13@bandit.labs.overthewire.org -p 2220
contrasenya del nivel 13 es:
wbWdlBxEir4CaE8LaPhauuOo6pwRmrDw

Level Goal

The password for the next level is stored in /etc/bandit_pass/bandit14 and can only be read by user bandit14. For this level, you don’t get the next password, but you get a private SSH key that can be used to log into the next level. Note: localhost is a hostname that refers to the machine you are working on

algoritmos de la solucion:

bandit13@bandit:~$ ls -a
.  ..  .bash_logout  .bashrc  .profile  sshkey.private
bandit13@bandit:~$ cat sshkey.private 
-----BEGIN RSA PRIVATE KEY-----
MIIEpAIBAAKCAQEAxkkOE83W2cOT7IWhFc9aPaaQmQDdgzuXCv+ppZHa++buSkN+
gg0tcr7Fw8NLGa5+Uzec2rEg0WmeevB13AIoYp0MZyETq46t+jk9puNwZwIt9XgB
ZufGtZEwWbFWw/vVLNwOXBe4UWStGRWzgPpEeSv5Tb1VjLZIBdGphTIK22Amz6Zb
ThMsiMnyJafEwJ/T8PQO3myS91vUHEuoOMAzoUID4kN0MEZ3+XahyK0HJVq68KsV
ObefXG1vvA3GAJ29kxJaqvRfgYnqZryWN7w3CHjNU4c/2Jkp+n8L0SnxaNA+WYA7
jiPyTF0is8uzMlYQ4l1Lzh/8/MpvhCQF8r22dwIDAQABAoIBAQC6dWBjhyEOzjeA
J3j/RWmap9M5zfJ/wb2bfidNpwbB8rsJ4sZIDZQ7XuIh4LfygoAQSS+bBw3RXvzE
pvJt3SmU8hIDuLsCjL1VnBY5pY7Bju8g8aR/3FyjyNAqx/TLfzlLYfOu7i9Jet67
xAh0tONG/u8FB5I3LAI2Vp6OviwvdWeC4nOxCthldpuPKNLA8rmMMVRTKQ+7T2VS
nXmwYckKUcUgzoVSpiNZaS0zUDypdpy2+tRH3MQa5kqN1YKjvF8RC47woOYCktsD
o3FFpGNFec9Taa3Msy+DfQQhHKZFKIL3bJDONtmrVvtYK40/yeU4aZ/HA2DQzwhe
ol1AfiEhAoGBAOnVjosBkm7sblK+n4IEwPxs8sOmhPnTDUy5WGrpSCrXOmsVIBUf
laL3ZGLx3xCIwtCnEucB9DvN2HZkupc/h6hTKUYLqXuyLD8njTrbRhLgbC9QrKrS
M1F2fSTxVqPtZDlDMwjNR04xHA/fKh8bXXyTMqOHNJTHHNhbh3McdURjAoGBANkU
1hqfnw7+aXncJ9bjysr1ZWbqOE5Nd8AFgfwaKuGTTVX2NsUQnCMWdOp+wFak40JH
PKWkJNdBG+ex0H9JNQsTK3X5PBMAS8AfX0GrKeuwKWA6erytVTqjOfLYcdp5+z9s
8DtVCxDuVsM+i4X8UqIGOlvGbtKEVokHPFXP1q/dAoGAcHg5YX7WEehCgCYTzpO+
xysX8ScM2qS6xuZ3MqUWAxUWkh7NGZvhe0sGy9iOdANzwKw7mUUFViaCMR/t54W1
GC83sOs3D7n5Mj8x3NdO8xFit7dT9a245TvaoYQ7KgmqpSg/ScKCw4c3eiLava+J
3btnJeSIU+8ZXq9XjPRpKwUCgYA7z6LiOQKxNeXH3qHXcnHok855maUj5fJNpPbY
iDkyZ8ySF8GlcFsky8Yw6fWCqfG3zDrohJ5l9JmEsBh7SadkwsZhvecQcS9t4vby
9/8X4jS0P8ibfcKS4nBP+dT81kkkg5Z5MohXBORA7VWx+ACohcDEkprsQ+w32xeD
qT1EvQKBgQDKm8ws2ByvSUVs9GjTilCajFqLJ0eVYzRPaY6f++Gv/UVfAPV4c+S0
kAWpXbv5tbkkzbS0eaLPTKgLzavXtQoTtKwrjpolHKIHUz6Wu+n4abfAIRFubOdN
/+aLoRQ0yBDRbdXMsZN/jvY44eM+xRLdRVyMmdPtP8belRi2E2aEzA==
-----END RSA PRIVATE KEY-----
bandit13@bandit:~$ file sshkey.private 
sshkey.private: PEM RSA private key

ssh -i sshkey.private bandit14@localhost -p2220

whoami

cat /etc/bandit_pass/bandit14


felicitaciones..!! pasastes el nivel 13 a 14!!
contrasenya para pasar al nivel 14:
fGrHPx402xGC7U7rXKDaxiWFTOiF0ENq

-----------------------------------------------------------------------
ssh bandit14@bandit.labs.overthewire.org -p 2220
contrasenya del nivel 14 es:
fGrHPx402xGC7U7rXKDaxiWFTOiF0ENq

Level Goal

The password for the next level can be retrieved by submitting the password of the current level to port 30000 on localhost.
Commands you may need to solve this level


solucion:

//formas para ver si el puerto esta abierto o cerrado
echo '' > /dev/tcp/127.0.0.1/30000
echo $?  // 0 de respuesta saldra
//saldra 0 si esta abierto y 1 si esta serrado
echo '' > /dev/tcp/127.0.0.1/30099
echo $?  // 1 de respuesta saldra el systema tambien avisa por default aveces.

-bash: connect: Connection refused
-bash: /dev/tcp/127.0.0.1/30099: Connection refused

//otra forma seria
echo '' > /dev/tcp/127.0.0.1/30000 && echo "[*] Puerto abierto" || echo "[*] Puerto cerrado"

//para eliminar otra informacion saliente y controlar que informacion sale
timeout 1 bash -c "echo '' > /dev/tcp/127.0.0.1/30008 2>/dev/null" 2>/dev/null && echo "[*] Puerto abierto" || echo "[*] Puerto cerrado"
[*] Puerto cerrado
           -o-
bash -c "echo '' > /dev/tcp/127.0.0.1/30001" 2>/dev/null && echo "[*] Puerto abierto" || echo "[*] Puerto cerrado"

// no se sabe porque no funciona el simple sterr le agrego un time out que no comprendo bien del todo.


its a problem with th paquet sender i will buy again. th product already gone back to china i tryed to stop then not posible. they had ignore me.

el paquete no llego a mi casa, y salio en mail americas que no hubo éxito en la entrega y que se esta regresando ha china intente por todo los medios de contactarme a que intente llamar me pero nada el paquete día siguiente sale que se regreso a china =(..!!. todo lo que tengo es que perdí una llamada solo una ves que no se, si es de mail América. fechas de entrega no coincide de ali expreses y mail América 13 - 14.

cat /etc/bandit_pass/bandit14
fGrHPx402xGC7U7rXKDaxiWFTOiF0ENq

echo "fGrHPx402xGC7U7rXKDaxiWFTOiF0ENq" | nc localhost 30000

jN2kgmIXJ6fShzhT2avhotn4Zcka6tnt

//otro forma de hacer lo mismo es por telnet
telnet localhost 30000
//luego saldramensajes y espacio vacion para que ingreses la contra senya
fGrHPx402xGC7U7rXKDaxiWFTOiF0ENq
// al ingrsar la contrasenya saldra la contrasenya que se busca como exito
jN2kgmIXJ6fShzhT2avhotn4Zcka6tnt

felicitaciones..!! pasastes el nivel 14 a 15!!
contrasenya para pasar al nivel 15:
jN2kgmIXJ6fShzhT2avhotn4Zcka6tnt

-----------------------------------------------------------------
ssh bandit15@bandit.labs.overthewire.org -p 2220
contrasenya del nivel 15 es:
jN2kgmIXJ6fShzhT2avhotn4Zcka6tnt

Level Goal

The password for the next level can be retrieved by submitting the password of the current level to port 30001 on localhost using SSL encryption.

Helpful note: Getting “HEARTBEATING” and “Read R BLOCK”? Use -ign_eof and read the “CONNECTED COMMANDS” section in the manpage. Next to ‘R’ and ‘Q’, the ‘B’ command also works in this version of that command…

solucion:

openssl s_client -connect 127.0.0.1:30001
// luego sucedera un three way hand shake al nivel de aplicacion que es un protocolo de coneccion con encriptacion
// de hally el ejercicio me pone poner la clave del bandit15 actual dentro del aplicacion del protocolo se enviara esa clave simetrica a traves al parecer de un clave asimentrica por solo 1 ves y luego probar ida y vuelta sucendciendo 3 veces por eso le llama three way hand shake




felicitaciones..!! pasastes el nivel 15 a 16!!
contrasenya para pasar al nivel 16:
JQttfApK4SeyHwDlI9SXGR50qclOAil1

--------------------------------------------------------------
ssh bandit16@bandit.labs.overthewire.org -p 2220
contrasenya del nivel 16 es:
JQttfApK4SeyHwDlI9SXGR50qclOAil1

Level Goal

The credentials for the next level can be retrieved by submitting the password of the current level to a port on localhost in the range 31000 to 32000. First find out which of these ports have a server listening on them. Then find out which of those speak SSL and which don’t. There is only 1 server that will give the next credentials, the others will simply send back to you whatever you send to it.

solucion:
// usando nmap va filtrar lo mas posible los puertos
nmap --open -T5 -v -n -p31000-32000 127.0.0.1
//esto te va ha escanear o filtrarpuerto puertos y te va salir lo siguiente que tienen que probar los puertos

Starting Nmap 7.80 ( https://nmap.org ) at 2023-06-18 07:58 UTC
Initiating Ping Scan at 07:58
Scanning 127.0.0.1 [2 ports]
Completed Ping Scan at 07:58, 0.00s elapsed (1 total hosts)
Initiating Connect Scan at 07:58
Scanning 127.0.0.1 [1001 ports]
Discovered open port 31960/tcp on 127.0.0.1
Discovered open port 31518/tcp on 127.0.0.1
Discovered open port 31790/tcp on 127.0.0.1
Discovered open port 31691/tcp on 127.0.0.1
Discovered open port 31046/tcp on 127.0.0.1
Completed Connect Scan at 07:58, 0.02s elapsed (1001 total ports)
Nmap scan report for 127.0.0.1
Host is up (0.00013s latency).
Not shown: 996 closed ports
PORT      STATE SERVICE
31046/tcp open  unknown
31518/tcp open  unknown
31691/tcp open  unknown
31790/tcp open  unknown
31960/tcp open  unknown


//luego connectar probando la filtrado donde tiene que poner la contrasenya actual me aparece en este puerto un llave asimetrica la llave privada.
openssl s_client -connect 127.0.0.1:31790
// proporcionar la contrasenya actual me va a pedir luego me sale la llave privada del bandit16
JQttfApK4SeyHwDlI9SXGR50qclOAil1

-----BEGIN RSA PRIVATE KEY-----
MIIEogIBAAKCAQEAvmOkuifmMg6HL2YPIOjon6iWfbp7c3jx34YkYWqUH57SUdyJ
imZzeyGC0gtZPGujUSxiJSWI/oTqexh+cAMTSMlOJf7+BrJObArnxd9Y7YT2bRPQ
Ja6Lzb558YW3FZl87ORiO+rW4LCDCNd2lUvLE/GL2GWyuKN0K5iCd5TbtJzEkQTu
DSt2mcNn4rhAL+JFr56o4T6z8WWAW18BR6yGrMq7Q/kALHYW3OekePQAzL0VUYbW
JGTi65CxbCnzc/w4+mqQyvmzpWtMAzJTzAzQxNbkR2MBGySxDLrjg0LWN6sK7wNX
x0YVztz/zbIkPjfkU1jHS+9EbVNj+D1XFOJuaQIDAQABAoIBABagpxpM1aoLWfvD
KHcj10nqcoBc4oE11aFYQwik7xfW+24pRNuDE6SFthOar69jp5RlLwD1NhPx3iBl
J9nOM8OJ0VToum43UOS8YxF8WwhXriYGnc1sskbwpXOUDc9uX4+UESzH22P29ovd
d8WErY0gPxun8pbJLmxkAtWNhpMvfe0050vk9TL5wqbu9AlbssgTcCXkMQnPw9nC
YNN6DDP2lbcBrvgT9YCNL6C+ZKufD52yOQ9qOkwFTEQpjtF4uNtJom+asvlpmS8A
vLY9r60wYSvmZhNqBUrj7lyCtXMIu1kkd4w7F77k+DjHoAXyxcUp1DGL51sOmama
+TOWWgECgYEA8JtPxP0GRJ+IQkX262jM3dEIkza8ky5moIwUqYdsx0NxHgRRhORT
8c8hAuRBb2G82so8vUHk/fur85OEfc9TncnCY2crpoqsghifKLxrLgtT+qDpfZnx
SatLdt8GfQ85yA7hnWWJ2MxF3NaeSDm75Lsm+tBbAiyc9P2jGRNtMSkCgYEAypHd
HCctNi/FwjulhttFx/rHYKhLidZDFYeiE/v45bN4yFm8x7R/b0iE7KaszX+Exdvt
SghaTdcG0Knyw1bpJVyusavPzpaJMjdJ6tcFhVAbAjm7enCIvGCSx+X3l5SiWg0A
R57hJglezIiVjv3aGwHwvlZvtszK6zV6oXFAu0ECgYAbjo46T4hyP5tJi93V5HDi
Ttiek7xRVxUl+iU7rWkGAXFpMLFteQEsRr7PJ/lemmEY5eTDAFMLy9FL2m9oQWCg
R8VdwSk8r9FGLS+9aKcV5PI/WEKlwgXinB3OhYimtiG2Cg5JCqIZFHxD6MjEGOiu
L8ktHMPvodBwNsSBULpG0QKBgBAplTfC1HOnWiMGOU3KPwYWt0O6CdTkmJOmL8Ni
blh9elyZ9FsGxsgtRBXRsqXuz7wtsQAgLHxbdLq/ZJQ7YfzOKU4ZxEnabvXnvWkU
YOdjHdSOoKvDQNWu6ucyLRAWFuISeXw9a/9p7ftpxm0TSgyvmfLF2MIAEwyzRqaM
77pBAoGAMmjmIJdjp+Ez8duyn3ieo36yrttF5NSsJLAbxFpdlc1gvtGCWW+9Cq0b
dxviW8+TFVEBl1O4f7HVm6EpTscdDxU+bCXWkfjuRb7Dy9GOtt9JPsX8MBTakzh3
vBgsyi/sN3RqRBcGU40fOoZyfAMT8s1m/uYv52O6IgeuZ/ujbjY=
-----END RSA PRIVATE KEY-----

//crear un direactorio temporal
mktemp -d
//se te crea esto que sale en tu terminal del cual tiene que entrar: /tmp/tmp.mxZdjQMG44
cd /tmp/tmp.mxZdjQMG44
// y dentro creas file donde ira tu private key copias pegas
nano id_rsa
// depues de compiar pegar debes de activar los permisos chmod pero con permiso solo de usurioa roor codigo en numero 600
chmod 600 id_rsa
// luego usas ssh para conectar al bandit17
ssh -i id_rsa bandit17@localhost -p2220
// luego que te halla conectado como bandit 17 buscas su contrasenya con el siguiente comando
cat /etc/bandit_pass/bandit17


felicitaciones..!! pasastes el nivel 16 a 17!!
contrasenya para pasar al nivel 17:
VwOSWtCA7lRKkTfbr2IDh6awj9RNZM5e

--------------------------------------------------------------
ssh bandit17@bandit.labs.overthewire.org -p 2220
contrasenya del nivel 1 es:
VwOSWtCA7lRKkTfbr2IDh6awj9RNZM5e ^6cd805


continuara__!! acuerdate de leer mas sobre opn ssl y netcat
1:55:04