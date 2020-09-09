#### Permite crear un dataset y asignarlo a una librería llamada SAS_LIB 

```
libname SAS_LIB "/home/u49736606/SAS_PRACTICA";

data SAS_LIB.dataset;
	length NOMBRE $32 APELLIDO $32 EDAD 8;
	NOMBRE='EDUARDO';
	APELLIDO='LOBO';
	EDAD=35;
run;
```