## Moviéndonos por el sistema
Como vimos previamente, el comando ```pwd``` nos muestra en que directorio nos encontramos. Ahora bien, si quiseramos saber que otros archivos o carpetas se encuentran en la ubicación actual, podemos listar el contenido del directorio con el comand ```ls``` ([list directory content](https://man7.org/linux/man-pages/man1/ls.1.html)). 

Así, con el ejemplo de la estructura de directorios:
 ```
carpeta0/
├── archivo0_a
├── archivo0_b
├── carpeta1
│   ├── archivo1_a
│   ├── archivo1_b
│   └── archivo1_c
└── carpeta2
     ├── archivo2_a
     ├── archivo2_b
     └── carpeta2a
         ├── archivo2a_a
         └── carpeta2b
             └── archivo2b_a     
```
Si realizáramos ```ls``` dentro de la carpeta0, veríamos:
``` archivo0_a  archivo0_b  carpeta1  carpeta2 ```

Para poder movernos dentro de una carpeta necesitamos invocar al comando ```cd``` ([change directory](https://man7.org/linux/man-pages/man1/cd.1p.html)) e indicarle la ruta (relativa o absoluta) a la que deseamos movernos. Por ejemplo:

```
$ cd carpeta1
$ ls
```

Nos debería mostrar ahora:
```
archivo1_a  archivo1_b  archivo1_c
```

Para volver al directorio inmediatamente superior, podemos utilizar ```cd ..```

## Creando carpetas y archivos

Con los comandos ```touch```([change file timestamps](https://man7.org/linux/man-pages/man1/touch.1.html)) y ```mkdir``` ([make directories](https://man7.org/linux/man-pages/man1/mkdir.1.html)) podemos crear archivos y carpetas vacías, respectivamente.

- A modo de ejercicio, intente crear la estructura de directorios y archivos que se muestra arriba.

<details>
  <summary>Ver respuesta</summary>
  
  ```
  $ mkdir carpeta0 carpeta0/carpeta1 carpeta0/carpeta2 carpeta0/carpeta2/carpeta2a/ carpeta0/carpeta2/carpeta2a/carpeta2b
  $ touch carpeta0/archivo0_a carpeta0/archivo0_b carpeta0/carpeta1/archivo1_a carpeta0/carpeta1/archivo1_b carpeta0/carpeta1/archivo1_c carpeta0/carpeta2/archivo2_a carpeta0/carpeta2/archivo2_b carpeta0/carpeta2/carpeta2a/archivo2a_a carpeta0/carpeta2/carpeta2a/carpeta2b/archivo2b_a
  ```
</details>

## Eliminando archivos y carpetas

En caso de necesitarlo, podemos utilizar el comando ```rm```([remove directory entries](https://man7.org/linux/man-pages/man1/rm.1p.html) para eliminar archivos y carpetas. Para elimar archvios solo es necesario indicar la ruta a los mismos y podemos eliminar de a un solo archivo o múltiples archivos a la vez. En el caso de querer eliminar directorios, debemos indicarle al comando que se ejecute de forma *recursiva* con el párametro **-r** o **-R**. Intente ejecutar el siguiente comando dentro de carpeta0 y observe lo que sucede.
```
$ rm carpeta1/archivo1_c
$ rm -R carpeta0/carpeta2/carpeta2a/carpeta2b
```

<details>
  <summary>Ver respuesta</summary>

La estructura ahora se verá como esto:

  ``` 
carpeta0
├── archivo0_a
├── archivo0_b
├── carpeta1
│   ├── archivo1_a
│   └── archivo1_b   
└── carpeta2
     ├── archivo2_a
     ├── archivo2_b
     └── carpeta2a
         └── archivo2a_a         
```
</details>

## Copiando y moviendo (i.e. "cortar y pegar")

Las operaciones de **copiado** se realizan con el comando ```cp``` ([copy files and directories](https://man7.org/linux/man-pages/man1/cp.1.html)). La sintáxis básica es **cp *origen* *destino***. Por ejemplo:
```
$ cp carpeta0/archivo0a carpeta0/carpeta2/
$ cp -R carpeta0/carpeta1 carpeta0/carpeta2/carpeta2a
```
Notar que en el caso de operar sobre directorios, debemos indicarle al comando que se eejcute *recursivamente* al igual que lo hicimos al eliminar directorios. 

Por otro lado, si deseamos realizar el equivalente a un "cortado y pegado" de un archivo o directorio, deberemos usar el comand ```mv``` ([move (rename) files](https://man7.org/linux/man-pages/man1/mv.1.html)). La sintáxis básica en este caso también es **mv *origen* *destino***. Por ejemplo:
```
~/carpeta0$ mv archivo0_a carpeta1/archivo0_a_movido
~/carpeta0$ mv carpeta1/ carpeta2/
```
Notar que en este caso el comando no tiene la opción de ejecutarse *recursivamente*. Ahora bien, ¿qué sucede en la ejecución del primer comando? Reflexione sobre esto considerando el nombre del comando, ¿por qué cree que mover y renombrar un archivo o carpeta es la misma operación?








