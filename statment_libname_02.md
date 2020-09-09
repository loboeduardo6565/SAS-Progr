##### Exportar un dataset con SET y asignarlo a una librería llamada SAS_LIB 


```
/* Se puede declarar una librería usando el stament LIBNAME + nombre + Path 
y guardar un dataset en dicha librería*/

libname LIBRERIA "/home/u49736606/UDEMYLIB";
data LIBRERIA.alumnos_avances;
	set alumnos;
	modulo = modulo + 2;
run;
```
