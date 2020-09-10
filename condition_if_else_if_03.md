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

/* Se verifica el ranking de las peliculas, Se llevan a 100 el Score de IMDB y se compara con el de Rotten Tomatoes*/
DATA PELICULAS;
	LENGTH PAG_MEJOR_SCORE $32 ScorIMDB2 8;
	SET MOVIES.PELICULAS_SCORE;
	ScorIMDB2 = (100 * ScorIMDB) / 10; 
	IF ScorIMDB2 > ScorRotten THEN PAG_MEJOR_SCORE= 'IMDB';
	ELSE IF ScorRotten > ScorIMDB2 THEN PAG_MEJOR_SCORE= 'Rotten Tomatoes';
	ELSE PAG_MEJOR_SCORE='Mismo Ranking';
run;
```