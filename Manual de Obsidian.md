si al final de un párrafo pone comillas y pegado ``al elemento abajo los `elementos` 
`tienden` a ~formar~  ``pegado`` del párrafo. los
las anidación de títulos o temas que se puedan abrir o colapsar en obsidian obedecen a la alineación de la tabulación por niveles, en el caso de listas numeración o puntos son en paralelos y basado en tabulación de espacios esto es en el modo para escribir en el modo solo para ver no sucede igual en listas. y en niveles de títulos de letras grandes tiene 6 niveles.
		hola este es un texto ejemplo de anidación en párrafo solo por tabulación y solo funciona en el modo para escribir y no en el modo solo para ver. para poder ver los caracteres especiales que hacen algún efecto especial en obsidian se usa esto \\ como el siguiente ejemplo del \<br> que es para el salto de linea para todo no solo párrafos en obsidian, esto se parece como en el \<br> de html .  pero obsidian solo reconoce un salto de solo para linea en salto de linea natural solo dentro de los párrafos del cual si  quieres hacer mas saltos de lineas tiene que usar con el \<br> varias veces.
		
   
   
   ojo si puede haber mas salto de lineas entre elementos que no sean párrafos.
   ademas dar espacio entre la ultima frase de párrafos arriba y elementos abajo puede hacer que la tabulación tome control sobre de la comillas u otras cosas    
		~ejemplo~
		
		`de`<br>``saltar``
		
		
		~~este~~<br><br>`párrafo`
---
+ ***Un ejemplo sobre de las listas***
	-  se puede hacer #listas con los símbolos + o -  pero con espacio obligado justo a lado des pues de esos 2 símbolos
	- el patrón se repite a los del anterior de la lista con solo aplastar el botón Enter para baja a la siguiente linea. 
		1. también existen #listas/numéricas numéricas  y de tareas y las listas se pueden combinar pero combinar sintaxis para expresar lo mismo en las listas puede dar errores por ejemplo listas de numeración pueden ser escritas 1. o 1)
			1. este es un ejemplo de otra forma de 
		2.  las listas numeradas y sub numerada en la siguiente linea se ordenan en números consecutivos automáticamente pones ademas pubes este símbolo para listas de tarea  [ ]
			1. [ ]  ejemplo de lista de tareas
			2. [ ] los corchetes deben de tener espacio en el medio antes y al inicio y finalization de los 2 corchetes
			-  [ ] si pones - o + como punto y luego los corchetes del check de lista de tareas sale de esa manera no se ve el punto.
				+ [ ] sin embargo es posible hacer sub nivel que se puede colapsar las listas sin problemas.  `ademas ni las listas ni los cuadrado del check de listas de tarea acceptan negritas ni italisca etc.`
		       3. links a  [[#^15d583|lista de imágenes]]
	- >ademas se pueden colapsar las listas que tienen sub-niveles por tabulación de espacios y que también estén en listados en puntos
		+ ``puede haber listas de sub-listas de cualquier sub-nivel  que pueden colapsarse``
		

  
---
- ***hay 3 formas de hacer linea de separación ejemplo:*** *** o --- o ___
	- ***
	---

>  las citas pueden estar pegado a hacia arriba a las listas
>  adema si activas un plugin en los plugins principales sobre las lineas de separation cada entre lineas que no estén en sub listas pueden actuar como un separador de presentaciones por secciones.
___
###### como hacer textos negritas o cursiva
seleccionar el ejemplos de como se hacen las letras negritas,
cursivas o ambas seleccionar el texto de ejemplo saldrán los comandos
ocultos que lo transforman.
ejem:
*Texto en cursiva*	// atajo de teclado es control + i
**Texto en Negrita**   // atajo de teclado es control + b
***Texto en cursiva y negrita***  // aplica ***ambos*** ctr + b + i
___hay otra forma de hacer negrita y cursiva___
~~Texto tachado~~  // atajo de teclado? no hay pero hay otra forma para
==texto resaltado==	//  -  las de mas formas doble click para seleccionar palabra y luego pones los símbolos especiales aparecerán de relleno por ambos lados incluye los casos de arriba separados por los \<br>
(subrayado por abajo o arriba todavía no se no la encuentro o no hay )
> Texto en cita coge todo lo de abajo dentro de un nivel de anidación  puedes combinar los tipos de textos:  ==**ejemplo**==   ~~___~~  ***`ghaa`***
---

###### sistema de títulos con letras grande a chiquito de 6 niveles
obsidian tiene un sistema markdown que se había creado para dar alternativa a html en lo siguiente veras que existen 6 niveles de títulos donde el nivel del titulo mas grande es 1 y el mas bajo 6 cuando dice niveles se refiere a que títulos mas chicos pueden estar dentro de tirulos mas grandes y no al revés o mejor dicho están anidados de nivel superior 1 hasta el 6 uno dentro del otro, en cuando si hay 2 títulos del mismo nivel obsidian lo considera como paralelo. solo anida de arriba para abajo el titulo nivel 1 de abajo no anida lo de arriba. la anidación da una animación que se puede colapsar la información de adentro. 
la sintaxis de invocación de un hashtag(#) y luego va espacio vació y el nombre del títulos o subtitulo que quieras. si no pones espacio y escribes por ejem. #listas  , esto va sucede similar a twitter que puede presionarlo y comenzara a busca sobre del nombre en el buscador ademas también los tag pueden tener sub categorías #listas/numéricas .
ver en los siguientes ejemplos:

# Ejemplo del nivel 1
		vea que se puede anidar y collapsar los titulos. intenta jugar con los otros
		titulos de ejemplos de niveles y ver como funciona el patron de colapso anidado
## Ejemplo del nivel 2
		se puede escribir informacion dentro de cada titulo del propio
		nivel de titulo sin que el nivel 3 lo tape.
### Ejemplo del nivel 3
		ya  que tiene una logica de niveles de contenido perteneciente
		de cada nivel en informacion del nivel mas genera 
		hacia los mas paricular 
--- las 3 lineas de separación para las presentaciones no funcionan en todo tipo de sub anidados		
#### Ejemplo del nivel 4
		cuando usas las flechas direcionales especialmente al bajar de nivel
		rapidamente puede bajar hasta el nivel siguiente sin aplastar con el
		mouse de desscolapsar
##### Ejemplo del nivel 5
		cuando colapsas un nivel superior se cierran todos los niveles
		anteriores, y al abrirlos queda como lo habias dejado antes sin
		tener que des collapsar lo todo.
###### Ejemplo del nivel 6
		y si antes no lo habias des colapsado pues es nivel no se ve ameno
		que lo habras, sucede igual si lo colapsas o cierras de nuevo este 
		patron de comportamiento se repite en todos los subniveles.
	###### Es para ver si los títulos le afectan los sub niveles
	- vease que dentro del subnivel en tabulacion de un titulo no funciona ni lista ni mismo titulo.


#   
---
##### truco de las anidaciónes fantasma y teoría que muchos otros no explican
con 3 guiones(---) espacio abajo pegado del de # nivel 1 hace que no se superponga con el titulo | si lo quitas se supe pondrá. y también sin tabulación el texto sale así.
> por alguna razón no se puede salir de la anidación del nivel 6 lo que se puede hacer  es crear un #  de nivel 6 y espacio fantasma saltar a la siguiente linea esto permite de alguna forma rara salir se de la anidación como mismo nivel paralelo pero permite colapsarse como fantasma en el sentido de que parece y desaparece y no se puede ver una ves colapsado fácilmente ademas de que si  en un reglón linea mas abajo pones otro hashtag titulo se superpondrá el botón del colapso en el modo solo vista y aveces se podrá colapsar el titulo y a veces ni siquiera el titulo y no se apunta bien el signo.
##
	 > aqui hay un ejemplo de anidación fantams consecutiva cuando pone tabulacion y luego el signo del texto en cita la anidación lo anula salvo que la segunda linea no sigas la tabulacion. 	 
>un ejemplo de no seguir la tabulación
###
```
 con comilla triple superior sale en el tema tokio nigth como si se usara anidación
 ademas al parecer cuendo estan en este modo el plugin de ortografia no funciona
```
####
> 			al tabular dentro de un texto con cita  sale ambos corrido 
> 			al aplastar ente y saltar la linea a uno de abajo obsidian automáticamente 
> 			copia el patrón de escritura de antes o la continua. ademas si el salto de 
> 			tabulación esta dentro de un texto de cita allí parece haber una excepción 
> 			y el corrector ortográfico si funciona
	>  y en la segunda linea pegado  al texto de arriba si tabulo y luego pongo  > la anidación no elimina el texto con cita gana

---
# links y imágenes en obsidian

^15d583

- **estos 2 casos son imágenes dentro del alcance de la bóveda local**

	- el signo ! hace que se puedas ver en imagen del link interno o externo
	   este caso no guarda proporción
	![[img_fv/ed-and_rocket.png|200x180]]
	
	- cuando no se especifica el alto se guarda la proporción original
	![[bb_hm.png|350]]

- **estos 2  son imágenes link conectado al internet fuera de lo local **

	- primero va el signo de exclamación si se quire ver una imagen luego un solo corchete abrir y cerra adentro y a lado y después del nombre y antes de cerrar corchete del nombre del imagen de el signo | donde a lado puede poner las dimensiones de la imagen similar al caso de arriba luego entre paracentesis u pegado va el link del imagen o web. 
	
	- pondré 2 ejemplos
		1.  si no escribo en listas algo arriba del link el numero aparece abajo como si cogiera el elemento.  ![YouTube para aprender obsidian](https://www.youtube.com/watch?v=9pHzd3VetY8&list=PL5d9BRTY5SwWvme_YX68vjqav9y99mZ_U&index=8)
		2. me he dado cuenta que solo coge imágenes y video pagina webs de varios elemento que no sean videos no ![miku_sexy|300](https://cdn.donmai.us/original/50/38/50382cb482ec71eb614bbaf9843e3ba2.png)
		      

- **ejemplo de como hacer un recuadro donde usualmente se usa para poner un bloque de código**
	- esto se hace poniendo los 3 comillas superiores aparecen otras 3 separado y  aparece un recuadro del recuadro va ha estar al nivel del tabulación que se encuentra y para que el código este dentro del recuadro tiene que esta en una tabulación hijo o dentro de lo 3 comillas que aparece después de escribir los 3 primeros ```
		```.js 
	 	
	 	main() {
		 	function fancyAlert() {
			 	if(args) {
				 	$.ghaa({div:#foo})
			 	}
		 	}
	 	}  

  > para que en el modo escritura se termine un recuadro de donde val el código necesita esas  trees rallas así sea separación ojo que en modo vista aparece fuera del recuadro del código pero no en modo escritura el color en los código el video dice que vienes de un plugin descargado y ademas esta escritura no debe de respetar la tabulación de lo contrario entra dentro del recuadro incluso en el modo vista.


- para escribir  un comentario y que obsidian y no lo capture en modo lectura se pone  al inicio \%%  y al final\%%  y no considera lo de al medio de lo contrario te invalida todo lo de abajo este caso en concreto lo he escrito con este character que permite mostrar a los caracteres especiales \\
	-  este seria un ejemplo: %% hole este es un comentario meta dato%% 

- ejemplo de enlace directo  la web
	- https:\//overthewire.org/wargames/bandit/bandit18.html https://overthewire.org/wargames/bandit/bandit18.html
	- \[Enlace a >>  **over the wire**]\(https:\//overthewire.org/wargames/bandit/bandit18.html) 
	    [Enlace a >> **over the wire**](https://overthewire.org/wargames/bandit/bandit18.html)
	- crear un enlace interno a otra nota si no existe la crea de la siguiente forma: 
		- \[[el enlace]] : [[el enlace]] 
		- también puede cambiar de nombre y referirte a lo mismo ejem. \[[el enlace|ghaa]], [[el enlace|ghaa]]
		- *también se puede hacer similar a imagines pero como archivo empotrado* \![[el enlace]] -> 
			+ cuando no son empotrados y enlace directo ala imagen no se puede controlar los pixels que se muestran ![[el enlace]]
			+ [[Alan walker - Best Song Of All Time.mp4]]
			+ ![[LGR Cheat Sheet.pdf]]
			+ cuando es texto puede seleccionar solo un sección para empotrar lo ![[resolviendo overdewire y aprendiendo bash#^6cd805]]
-  ***por si acaso :***
	-  las imágenes se pueden simplemente arrastrar a obsidian y se creara un carpeta automáticamente para todas las imagen arrastradas sea por local o web también video por local. y video de web solo serian links creo . 
	- este es un ejemplo de enlace a ![[manual de canvas.canvas|manual de canvas]] 










