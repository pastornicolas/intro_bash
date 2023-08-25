# intro_bash
Introducción al uso de la interfaz de línea de comando de sistemas GNU/Linux.

## La terminal
La forma más básica de interacción entre un usuario y un sistema informático es a través de una **interfaz de línea de comando** ([CLI](https://es.wikipedia.org/wiki/Interfaz_de_l%C3%ADnea_de_comandos)). En los sistemas GNU/Linux utilizamos para ello un programa específico conocido como [emulador de terminal](https://es.wikipedia.org/wiki/Emulador_de_terminal), también llamado simplemente **terminal**.

![pic1](/pics/terminal.png)

En la imagen previa, el síbolo **$** se conoce como *prompt* y nos indica que la terminal se encuentra a la espera de órdenes. Así mismo, vemos que antes del prompt el sistema nos brinda información muy útil, en dos campos separados con **:**
- Por un lado, tenemos la información del **nombre de usuario** que se encuentra conectado y en que **máquina** se encuentra activo. Esta información es la que corresponde con *user@host*.
- Por el otro lado, la terminal nos indica en **dónde** nos encontramos en ese momento, es decir, cual es la ruta al directorio (i.e. "carpeta") en el cual se encutra activa. Esta es la información contenida en la expresión *~/path_to_folder/*.

Para ejecutar una orden bastará con invocar a un programa dado, teniendo siempre en cuenta la siguiente sintáxis básica:

![pic2](/pics/orden.png)

Donde:
- El **comando** es el programa que es el programa que estamos invocando.
- Los **parámetros** son una o más opciones que modifican el comportamiento del programa.
- La **entrada** es un archivo sobre el que queremos realizar la acción.

## Licencia
© 2023 Nicolás Pastor y colaboradores. Bajo licencia [Creative Commons Attribution-NonCommercial-ShareAlike 4.0 International License][cc-by-nc-sa].

[![CC BY-NC-SA 4.0][cc-by-nc-sa-image]][cc-by-nc-sa]

[cc-by-nc-sa]: http://creativecommons.org/licenses/by-nc-sa/4.0/
[cc-by-nc-sa-image]: https://licensebuttons.net/l/by-nc-sa/4.0/88x31.png


