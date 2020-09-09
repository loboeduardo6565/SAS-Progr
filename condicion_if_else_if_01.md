#### IF ELSE IF

```
/* Se puede declarar una librería usando el stament LIBNAME + nombre + Path
y guardar un dataset en dicha librería*/

libname MOVIES "/home/u49736606/LIBMOVIE";
data MOVIES.PELICULAS_SCORE;
	length Titulo $32 Anio 8 Duration 8 ScorIMDB 8 ScorRotten 8 ScorAmazon 8;
	/* Se debe indicar el delimitador en este caso la coma  */
	INFILE DATALINES DLM=',';
	input Titulo $ Anio Duration ScorIMDB ScorRotten ScorAmazon;
	datalines;
The Fast and the Furious , 2001, 106, 6.8, 53, 4.6
2 Fast 2 Furious , 2003, 107, 5.9, 36, 4.5
The Fast and the Furious: Tokyo Drift , 2006, 104, 6, 38, 4.5
Fast & Furious , 2009, 107, 6.6, 29, 4.7
Fast Five , 2011, 130, 7.3, 77, 4.8
Fast & Furious 6 , 2013, 130, 7.1, 70, 4.7
Furious 7 , 2015, 137, 7.2, 81, 4.6
The Fate of the Furious , 2017, 147, 6.7, 67, 4.6
Fast & Furious Presents: Hobbs & Shaw , 2019, 147, 6.5, 67, 4.4
;
RUN;

/* Se agregan algunas condiciones con IF luego de importar el dataset desde una librería especifica*/
data PELICULAS;
	SET MOVIES.PELICULAS_SCORE;
	IF ScorIMDB >= 7 THEN OPINION='Muy buena';
	ELSE IF ScorIMDB >=6 AND ScorIMDB <7 THEN OPINION='Buena';
	ELSE OPINION='Mala';
run;
```