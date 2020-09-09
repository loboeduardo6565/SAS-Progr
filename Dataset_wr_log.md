#### Permite crear un dataset y muestra su salida en el log 
###### PUT permite escribir la salida en consola
```
data _null_;
	length NOMBRE $32 ANHO_NACIMIENTO 8 EDAD 8 ANHO_ACTUAL 8;
	ANHO_NACIMIENTO=1984;
	ANHO_ACTUAL=year(today());
	EDAD=35;
	NOMBRE='Eduardo';
	put NOMBRE "tiene, " EDAD "años.";
run;
```

