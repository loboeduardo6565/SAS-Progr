

##### Creando una librería desde un archivo de excel 
```
option validvarname=v7; /*Obliga a que los nombres de tablas y columnas leídas de excel cumplan con las convenciones de nomenclatura SAS*/
libname NAME xlsx "/home/u49736606/Ruta/File.xlsx"; /*Se debe indicar el Engine*/

proc contents data=NAME.LIBRO;
run;

libname NAME clear; /*Se elimina como buena práctica el libref*/
```