# SegundoParcial_SPD

![Tinkercad](Segundo_parcial/Img/portada.jpg)


## Integrante
- Diego Uthurburu


## Proyecto: MONTACARGAS.
![Tinkercad](Parcial/Img/trabajo.png)


## Descripción
Permita al usuario dar ordenes a un montacargas de subir, bajar o pausar
desde diferentes pisos y muestre el estado actual del montacargas en el display 7.


## Funciónes principales
Estas funciones se encargan de encender y apagar los leds.

 UP, DOWN, STOP, LED_RED, LED_GREEN, A, B, C, D ,E, F, G,
 son #define que utilizamos para agregar los leds y los pulsadores, asociandolo a pines de la placa arduino.

(Esta funcion se encarga de prender los Led )

~~~ C++ (lenguaje en el que esta escrito)
void encender(int led)
{
	  digitalWrite(led, HIGH);
}
~~~
(Esta funcion se encarga de apagar los Led )

~~~ C++ (lenguaje en el que esta escrito)
void apagar(int led)
{
	  digitalWrite(led, LOW);
}
~~~

  (Esta funcion se encarga de prender los led del Visualizador de 7 segmentos, mediante la configuración de sus pines. Se le pasa el estado requerido de cada pin en orden alfabetico)
~~~ C++ (lenguaje en el que esta escrito)
void encender_display(int a, int b, int c, int d, int e, int f, int g)
{
	digitalWrite(A, a);
  	digitalWrite(B, b);
  	digitalWrite(C, c);
  	digitalWrite(D, d);
  	digitalWrite(E, e);
  	digitalWrite(F, f);
  	digitalWrite(G, g);
}
~~~

 (Esta funcion muestra un número de piso en un display de 7 segmentos, recibe como parametro el numero de piso )
~~~ C++ (lenguaje en el que esta escrito)
void mostrar_piso(int piso)
{
  switch(piso)
  {
 	case 1:
    	encender_display(LOW,HIGH,HIGH,LOW,LOW,LOW,LOW);
    	break;
    case 2:
    	encender_display(HIGH,HIGH,LOW,HIGH,HIGH,LOW,HIGH);
    	break;
    case 3:
    	encender_display(HIGH,HIGH,HIGH,HIGH,LOW,LOW,HIGH);
    	break;
    case 4:
    	encender_display(LOW,HIGH,HIGH,LOW,LOW,HIGH,HIGH);
    	break;
    case 5:
    	encender_display(HIGH,LOW,HIGH,HIGH,LOW,HIGH,HIGH);
    	break;
    case 6:
    	encender_display(LOW,LOW,HIGH,HIGH,HIGH,HIGH,HIGH);
    	break;
    case 7:
    	encender_display(HIGH,HIGH,HIGH,LOW,LOW,LOW,LOW);
    	break;
    case 8:
    	encender_display(HIGH,HIGH,HIGH,HIGH,HIGH,HIGH,HIGH);
    	break;
    case 9:
    	encender_display(HIGH,HIGH,HIGH,LOW,LOW,HIGH,HIGH);
    	break;
    case 0:
    	encender_display(HIGH,HIGH,HIGH,HIGH,HIGH,HIGH,LOW);
    	break;
  }
}
~~~

(Esta funcion se de mostrar por el monitor el estado del montacargas y en que piso se encuentra, recibe como parametro una cadena de texto y el numero de piso )

~~~ C++ (lenguaje en el que esta escrito)
void mostrar_piso(const char* mensaje, int numero_piso)
{
  char texto[300]; 
  sprintf(texto, "%s %d", mensaje, numero_piso);
  Serial.println(texto);
}
~~~


## :robot: Link del proyecto

- Diego Uthurburu [ver proyecto](https://www.tinkercad.com/things/kN8JOVuuRoA-parcial-1b-diego-uthurburu/editel?sharecode=AUNr4Hfr5Z8YR_P0749QUUNWtZO-4m-I-0xm1Qz1a5M)

## Diagrama Esquematico:
- [Ver Diagrama](Parcial/Img/esquema.pdf)
---
### Fuentes
- [Consejos para documentar](https://www.sohamkamani.com/how-to-write-good-documentation/#architecture-documentation).

- [Lenguaje Markdown](https://markdown.es/sintaxis-markdown/#linkauto).

- [Markdown Cheatsheet](https://github.com/adam-p/markdown-here/wiki/Markdown-Cheatsheet).

- [Tutorial](https://www.youtube.com/watch?v=oxaH9CFpeEE).

- [Emojis](https://gist.github.com/rxaviers/7360908).

---
