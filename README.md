# Cloud Architecture ITBA 2024

Repositorio para el curso de Cloud Architecture ITBA 2024.

## Descripción del Dataset

Utilizaremos los datasets de IMDB que posee las siguientes tablas:

### title.akas.tsv.gz
- **titleId (string)**: un tconst, un identificador único alfanumérico del título
- **ordering (integer)**: un número para identificar de manera única las filas de un titleId dado
- **title (string)**: el título localizado
- **region (string)**: la región para esta versión del título
- **language (string)**: el idioma del título
- **types (array)**: conjunto enumerado de atributos para este título alternativo. Uno o más de los siguientes: "alternative", "dvd", "festival", "tv", "video", "working", "original", "imdbDisplay". Se pueden agregar nuevos valores en el futuro sin previo aviso
- **attributes (array)**: términos adicionales para describir este título alternativo, no enumerados
- **isOriginalTitle (boolean)**: 0: no es el título original; 1: es el título original

### title.basics.tsv.gz
- **tconst (string)**: identificador único alfanumérico del título
- **titleType (string)**: el tipo/formato del título (por ejemplo, película, corto, serie de TV, episodio de TV, video, etc.)
- **primaryTitle (string)**: el título más popular / el título utilizado por los cineastas en materiales promocionales en el momento del lanzamiento
- **originalTitle (string)**: título original, en el idioma original
- **isAdult (boolean)**: 0: título no adulto; 1: título adulto
- **startYear (YYYY)**: representa el año de lanzamiento de un título. En el caso de las series de TV, es el año de inicio de la serie
- **endYear (YYYY)**: año de finalización de la serie de TV. '\N' para todos los demás tipos de títulos
- **runtimeMinutes**: tiempo de ejecución principal del título, en minutos
- **genres (string array)**: incluye hasta tres géneros asociados con el título

### title.crew.tsv.gz
- **tconst (string)**: identificador único alfanumérico del título
- **directors (array of nconsts)**: director(es) del título dado
- **writers (array of nconsts)**: escritor(es) del título dado

### title.episode.tsv.gz
- **tconst (string)**: identificador alfanumérico del episodio
- **parentTconst (string)**: identificador alfanumérico de la serie de TV principal
- **seasonNumber (integer)**: número de temporada a la que pertenece el episodio
- **episodeNumber (integer)**: número de episodio del tconst en la serie de TV

### title.principals.tsv.gz
- **tconst (string)**: identificador único alfanumérico del título
- **ordering (integer)**: un número para identificar de manera única las filas de un titleId dado
- **nconst (string)**: identificador único alfanumérico del nombre/persona
- **category (string)**: la categoría de trabajo en la que estaba la persona
- **job (string)**: el título del trabajo específico, si corresponde, de lo contrario '\N'
- **characters (string)**: el nombre del personaje interpretado, si corresponde, de lo contrario '\N'

### title.ratings.tsv.gz
- **tconst (string)**: identificador único alfanumérico del título
- **averageRating**: promedio ponderado de todas las calificaciones individuales de los usuarios
- **numVotes**: número de votos que ha recibido el título

### name.basics.tsv.gz
- **nconst (string)**: identificador único alfanumérico del nombre/persona
- **primaryName (string)**: nombre por el cual la persona es más frecuentemente acreditada
- **birthYear**: en formato YYYY
- **deathYear**: en formato YYYY si corresponde, de lo contrario '\N'
- **primaryProfession (array of strings)**: las tres profesiones principales de la persona
- **knownForTitles (array of tconsts)**: títulos por los cuales la persona es conocida

## Preguntas de negocio
* ¿Cuántos títulos hay en cada idioma?
* ¿Cuál es el título de mayor runtimeMinutes?
* ¿Cuáles son el top 3 de los títulos con mayor rating?
* ¿Cuál es el actor más antiguo?
