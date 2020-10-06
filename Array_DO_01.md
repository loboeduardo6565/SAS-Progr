```
/*Permite conocer la posición de un valor en el arreglo indicando su tamaño*/
DATA FILE_ARRAY;
	/*Este IF permite recorrer el arreglo hasta encontrar una igualdad*/
	/*ARRAY FILE_SIZE{6} (13.2, 12.8, 2.1, 20.5, 8.56, 12.7);
	IF 20.5 IN FILE_SIZE THEN SE_ENCUENTRA='SI';
	RUN;*/
	ARCHIVO_205=0;

	/*La palabra DIM fija la dimensión del arreglo para no tener que decir el tamaño del mismo*/
	DO i=1 TO DIM(FILE_SIZE);

		IF FILE_SIZE{i}=20.5 THEN
			ARCHIVO_205=i;
	END;
RUN;
```