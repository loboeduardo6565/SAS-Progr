#### Muestra el funcionamiento de un loop

```
data _null_;
	length NOMBRE $32 ANHO_NACIMIENTO 8 EDAD 8 ANHO_ACTUAL 8;
	ANHO_NACIMIENTO=1984;
	ANHO_ACTUAL=year(today());
	EDAD=35;
	NOMBRE='Eduardo';

	do i=1 to 5;
		put "En el, " ANHO_ACTUAL", " NOMBRE " tendrá " EDAD " años.";
		output;
		EDAD=(EDAD /2) + EDAD;
		ANHO_ACTUAL=(EDAD /2) + ANHO_ACTUAL;
	end;
run;
```