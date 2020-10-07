

##### Creando una librería desde un archivo de excel 
```
option validvarname=v7; /*Obliga a que los nombres de tablas y columnas leídas de excel cumplan con las convenciones de nomenclatura SAS*/
libname NP xlsx "/home/u49736606/EPG194/data/np_info.xlsx"; /*Se debe indicar el Engine*/

proc contents data=NP.PARKS;
run;

libname np clear; /*Se elimina como buena práctica el libref*/
```