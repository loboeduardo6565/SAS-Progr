#### Stament DATALINES

```
/* El Stament DATALINES permite importar data desde un texto libre a un dataset, especificando 
a través del stament INPUT las variables en el orden que se espera e identificando con el simbolo
$ cuando se trata de un caracter alfanumérico  */

data alumnos;
	length nombre $32 edad 8 pais $32 modulo 8;
	input nombre $ edad pais $ modulo;
	datalines;
Mario 35 Venezuela 2
María 33 Venezuela 2
Camila 3 Venezuela 0 
Carlos 35 Argentina 0
Fernanda 32 Argentina 0
Andreina 31 Argentina 0
María 35 Argentina 0
Fernando 32 Argentina 0
Andres 31 Argentina 0
;
RUN;

/* Se puede importar un dataset en otro dataset con el statment SET  */
/* Se puede vincular un dataset a una librería colocando el nombre de la librería antes del nombre del dataset seguido e un punto  */
data UDEMYLIB.alumnos_avances;
	set alumnos;
	modulo = modulo + 2;
run;
```