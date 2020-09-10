##### Usando Until y While

```
/*
DO UNTIL / DO WHILE
HACER HASTA / HACER MIENTRAS
*/

/* Usando el DO UNTIL para reducir un número*/

DATA _NULL_;
	X=50;

	DO UNTIL(X=0);
		X=X-5;
	END;
	PUT X;
RUN;

/* Usando el DO WHILE para reducir un número*/

DATA _NULL_;
	X=50;

	DO WHILE(X>0);
		X=X-5;
	END;
	PUT X;
RUN;
```