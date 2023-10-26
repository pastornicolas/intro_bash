## Entrada estándar, salida estándar y error estándar
En los sistemas GNU/Linux, los comandos toman alguna entrada (*input*) del usuario, ejecutan una acción determinada (*proceso*) y devuelven algun tipo de salida (*output*). El tipo de entrada más básico corersponde a lo ingresado mediante el teclado y se denomina **entrada estándar (stdin)** 

Si la ejecución del comando resulta exitosa, la salida será lo que se conoce como **salida estándar (stdout)** y dependerá en gran medida del tipo de entrada y acción que realice el comando, pero generalmente será alguna salida impresa en la pantalla. Si la ejecución falla por alguna razón, entonces normalmente veremos en la pantalla algún mensaje indicándonos el error, esto es lo que se conoce como **error estándar (stderr)**.

Cada uno de estos canales de información reciben por defecto una identificación numérica:
| Canal  |ID |
|--------|---|
| stdin  | 0 |
| stdout | 1 |
| stderr | 2 |

La imagen a continuación muestra los canales estándares de información:

![inouterr](/pics/inouterr.png)

## Concatenando comandos (pipes)

En muchas situaciones nos será necesario ejecutar un comando dado, obtener su salida estándar y, sobre esta, ejecutar un segundo comando. Para estas situaciones, podremos hacer uso de operador "**|**" conocido como *pipe*, el cual toma la salida estandar de un programa y lo envía como entrada estandar a otro.

Por ejemplo, tomando la estructura de carpetas y archivos creada previamente, si estamos ubicados dentro de ```carpeta0``` podremos hacer: 

```
$ ls | grep "carpeta"
```

La expresión precedente, ejecuta el comando ```ls``` en la ubicación ```carpeta0```, lo que nos dará una lista de las 2 carpetas y 2 archivos dentro de ella. Pero el *pipe* evitará que la misma se imprima en la pantalla y en cambio la pasará como entrada para el comando ```grep``` ([print lines that match patterns](https://man7.org/linux/man-pages/man1/grep.1.html)), por lo que el resultado que veremos en la pantalla será la salida estandar del segundo comando, que tomó como entrada la salida del primer comando.

La utilización de *pipes* no se limita a dos expresiones y puede utilizarse todos las concatenaciones de comando requerida, siempre que las salidas de cada comando sean una entrada válida para el comando posterior.



