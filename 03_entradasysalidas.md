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

Por ejemplo, tomando la estructura de carpetas y archivos creada previamente y estando ubicadon dentro de ```carpeta0``` podremos hacer: 

```
$ ls | grep "carpeta"
```


