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
  mkdir carpeta0 carpeta0/carpeta1 carpeta0/carpeta2 carpeta0/carpeta2/carpeta2a/ carpeta0/carpeta2/carpeta2a/carpeta2b
  touch carpeta0/archivo0_a carpeta0/archivo0_b carpeta0/carpeta1/archivo1_a carpeta0/carpeta1/archivo1_b carpeta0/carpeta1/archivo1_c carpeta0/carpeta2/archivo2_a carpeta0/carpeta2/archivo2_b carpeta0/carpeta2/carpeta2a/archivo2a_a carpeta0/carpeta2/carpeta2a/carpeta2b/archivo2b_a
  ```



