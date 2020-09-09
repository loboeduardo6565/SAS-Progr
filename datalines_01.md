##### Datalines
###### Permite importar en un dataset cualquier dato con algún delimitador 

```
data alumnos;
/*Las variables alfanumericas permiten un tamaño de 32 caracteres y los numericos de 8*/
length nombre $32 edad 8 pais $32 modulo 8;
/* Se debe indicar con un $ cuando la variable es alfanumerica*/
input nombre $ edad pais $ modulo;
datalines;
Mario 35 Venezuela 2
María 33 Venezuela 2
Mariana 3 Venezuela 0 
Marcelo 35 Argentina 0
Maximo 32 Argentina 0
Marcela 31 Argentina 0
;
RUN;
```