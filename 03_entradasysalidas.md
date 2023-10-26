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

## Redirecciones de entrada y salida 

Además de poder concatenar comandos con el uso de los pipes, podemos estar interesados en **redirigir la salida y/o el error estándar hacia un archivo** en vez de que el mismo sea mostrado en la pantalla, así como también podríamos querer **pasar como entrada a un programa algo contenido en un archivo**.

Para estos casos utilizaremos el operador "**>**", que puede tomar diferentes formas de acuerdo a la función que necesitemos.

### Redirección de salida estándar a un archivo

En su forma más sencilla, la redireccion de la salida estandar a un archivo puede realizarse de la siguiente forma:

```$ echo "Enviar esta salida del comando 'echo' hacia un archivo" > archivo_receptor```

El comando ```echo``` ([display a line of text](https://man7.org/linux/man-pages/man1/echo.1.html)) nos permitiría normalmente imprimir en la pantalla la expresión que le pasemos como argumento. Pero en este caso, al ejecutarlo no veremos salida alguna en la pantalla. Esto es porque la *stdout* está siendo redirigida hacia el archivo. Si quisieramos ver el contendio del mismo, podremos utilizar el comando ```cat``` ([concatenate files and print on the standard output](https://www.man7.org/linux/man-pages/man1/cat.1.html)), usando ```$ cat archivo_receptor```.

Como se puede notar, al momento de redirigir la *stdout* a un archivo el mismo se crea para alojar el flujo de información que está recibiendo. Si el archivo existiera previamente el mismo **sería sobreescrito con la información**, lo cual es importante recordar para no sobreescribir un archivo al redireccionar nueva informacaión utilizando el mismo nombre de archivo.

Si quisieramos almacenar un archivo ya existente la *stdout* de una nueva ejecución de un comando, o de otro diferente, podremos hacer uso del operador "**>>**":

```$ echo "Enviar una segunda salida y anexarla en el archivo ya existente" >> archivo_receptor```

Si ahora realizamos ```$ cat archivo_receptor```, veremos que la nueva ejecución no sobreescribio el contenido, sino que se añadió una segunda línea con la segunda salida del comando ```echo```.

### Redirección del error estándar









