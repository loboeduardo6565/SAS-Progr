###### LOOP 

```
/*
DO <INDICE> = <INICIO> TO <FINAL>;
<INSTRUCCIONES>
END;
*/
DATA _NULL_;
	X=0;

	DO i=1 TO 500;
		X=X+1;
	END;
	PUT X;
RUN;

/*Mismo Ejercicio saltando de 10 en 10*/

DATA _NULL_;
	X=0;

	DO i=0 TO 500 BY 10;
		X=i;
	END;
	PUT X;
RUN;
v