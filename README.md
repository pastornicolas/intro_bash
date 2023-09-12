# intro_bash
Introducción al uso de la interfaz de línea de comando de sistemas GNU/Linux.

## La terminal
La forma más básica de interacción entre un usuario y un sistema informático es a través de una **interfaz de línea de comando** ([CLI](https://es.wikipedia.org/wiki/Interfaz_de_l%C3%ADnea_de_comandos)). En los sistemas GNU/Linux utilizamos para ello un programa específico conocido como [emulador de terminal](https://es.wikipedia.org/wiki/Emulador_de_terminal), también llamado simplemente **terminal**.

![pic1](/pics/terminal.png)

En la imagen previa, el síbolo **$** se conoce como *prompt* y nos indica que la terminal se encuentra a la espera de órdenes. Así mismo, vemos que antes del prompt el sistema nos brinda información muy útil, en dos campos separados con **:**
- Por un lado, tenemos la información del **nombre de usuario** que se encuentra conectado y en que **máquina** se encuentra activo. Esta información es la que corresponde con *user@host*.
- Por el otro lado, la terminal nos indica en **dónde** nos encontramos en ese momento, es decir, cual es la ruta al directorio (i.e. "carpeta") en el cual se encuetra activa. Esta es la información contenida en la expresión *~/path_to_folder/*.

Para ejecutar una orden bastará con invocar a un programa dado, teniendo siempre en cuenta la siguiente sintáxis básica:

![pic2](/pics/orden.png)

Donde:
- El **comando** es el programa que es el programa que estamos invocando.
- Los **parámetros** son una o más opciones que modifican el comportamiento del programa.
- La **entrada** es un archivo sobre el que queremos realizar la acción.

## El sistema jerárquico de archivos en los sistemas GNU/Linux
![pic3](/pics/linux-filesystem22.jpg)

Los sistemas GNU/Linux poseen una [estructura de archivos jerárquica] (https://es.wikipedia.org/wiki/Filesystem_Hierarchy_Standard), donde **/** es la **raíz** del sistema, siendo este el punto de partida de esta estructura.
Es importante resaltar que el caracter **/** es el mismo que es utilizado en las rutas para separar los subdirectorios correspondientes. En esta estructura, el directorio **/home** es de particular interés, ya que allí se ubican los directorios de trabajo de cada usuario que posea el sistema.

De este modo, la ruta **/home/pedro/Documentos/midocumento.txt** nos está indicando que el archivo "midocumento.txt" se encuentra en el direcotorio "Documentos", dentro del directorio */home* del usuario "pedro". Ahora bien, si abrimos una terminal nueva, por defecto esta nos mostrará la siguiente ruta:

```user@host:~$```

Para conocer el directorio en el que nos encontramos, podremos invocar al comando ```pwd``` ([print working directory](https://man7.org/linux/man-pages/man1/pwd.1.html)), el cual nos mostrará algo similar a:

```/home/user```

Con esto podemos ver que el caracter **~** es una forma abreviada del directorio */home/user* del usuario activo.

## Rutas absolutas y relativas
Existen dos formas de expresar una ruta en los sistemas GNU/Linux:
- Las **rutas absolutas** son aquellas en las que explícitamente se indica todo el trayecto realizado desde la ráiz (**/**) del sistema hasta la ubicación en cuestión. Por ejemplo, la ruta anterior al archivo "midocumento.txt" es una ruta absoluta, ya que en la misma se explicita toda la ruta desde la raíz hasta el archivo. Esto aplica incluso si la misma ruta fuera expresada de la forma abreviada ```~/Documentos/midocumento.txt```.
- Las **rutas relativas** por su parte, nos muestran la ubicación de un archivo o directorio en sentido relativo al directorio de trabajo en curso. Generalmente, las mismas empiezan con uno o dos caracteres de punto ".", teniendo la expresión ```./``` el significado literal de "en este directorio", es decir, en el directorio actual; mientras que la expresión ```../``` indica el directorio padre en la jerarquía, del directorio actual.

Como ejemplo, tomando como referencia la imagen del sistema jerárquico, tenemos:
- ```/usr/bin/R``` indicaría la *ruta abosulta* al binario ejecutable de R instalado en el directorio ```/usr/bin```
- Ahora bien, si el directorio de trabajo activo fuera este último, la *ruta relativa* expresada como ```../include```, indicaría el directorio bajo ```/usr/include```, así como la ruta ```../../var```, indicaría de forma relativa la ubicación del directorio ```/var```

### Para pensar un poquito
Imagine que dentro del directorio ```/home/pedro/Documentos```, posee la siguiente estructura de directorios:
 ```
carpeta0/
├── archivo0_a
├── archivo0_b
├── carpeta1
│   ├── archivo1_a
│   ├── archivo1_b
│   └── archivo1_c
└── carpeta2
     ├── archivo2_a
     ├── archivo2_b
     └── carpeta2a
         ├── archivo2a_a
         └── carpeta2b
             └── archivo2b_a     
```
- ¿Cuál sería la ruta absoluta al archivo "archivo1_c"?

<details>
  <summary>Ver respuesta</summary>

  ```
  /home/pedro/Documentos/carpeta0/carpeta1/archivo1_c
  ```
</details>

- ¿Como sería la ruta relativa desde el directorio "carpeta2b" hacia el archivo "archivo1_c"?

<details>
  <summary>Ver respuesta</summary>

  ```
  ../../../carpeta1/archivo1_c
  ```
</details>




## Licencia
© 2023 Nicolás Pastor y colaboradores. Bajo licencia [Creative Commons Attribution-NonCommercial-ShareAlike 4.0 International License][cc-by-nc-sa].

[![CC BY-NC-SA 4.0][cc-by-nc-sa-image]][cc-by-nc-sa]

[cc-by-nc-sa]: http://creativecommons.org/licenses/by-nc-sa/4.0/
[cc-by-nc-sa-image]: https://licensebuttons.net/l/by-nc-sa/4.0/88x31.png


