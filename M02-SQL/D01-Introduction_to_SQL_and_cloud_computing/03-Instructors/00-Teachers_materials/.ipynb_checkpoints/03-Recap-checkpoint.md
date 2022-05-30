
Hello @chaîne, 
J’espère que votre premier cours d’SQL s’est bien passé pour tous. Pour vous résumer ce qu’on a vu:

# :un: - SQL Introduction
- Les données sont des éléments stockés dans des colonnes, elles même stockées dans des
tables qui sont enfin stockées dans des databases.

- Elles sont de différent type, qu'il faut préciser. Nous avons vu les types suivants :

`TEXT (mots)`
`INTEGER (nombre entier)`
`DATETIME (date)`
`REAL / FLOAT (nombre réel)`
`NULL (donnée vide)`

- SQL et ses déclinaisons (notamment MySQL, PostgreSQL) sont très employés pour la
production, la manipulation et l'analyse de bases de données.

- SQL n'est pas "case sensitive", mais mettre vos clauses en majuscule rendra vos scripts plus lisibles
- `;` finit une instruction. Les espaces, tabulations et saut de ligne servent uniquement à rendre votre code lisible

- La clef d'un code qui tourne est la rigueur et la pratique. Il faut prêter une attention toute particulière à la syntaxe: `,` , `()` , `;`

- Nous avons vu pour l'instant les clauses suivantes (cf cours pour le détail) :
`CREATE DATABASE`
`USE`
`CREATE TABLE`
`INSERT INTO ... VALUES`
`SELECT ... FROM`
`UPDATE ... SET ... WHERE ...`
`ALTER TABLE ... ADD COLUMN ...`
`ALTER TABLE ... DROP COLUMN ...`
`DELETE FROM ... WHERE ...`

Vous trouverez les réponses du TD d'hier ci-dessous:
https://docs.google.com/document/d/1mkrY5Sy6EJsGvc1DAqgl6E3zaf2KFeQeapF09Vdve0c/edit

Je vous invite à pratiquer encore un peu et à me contacter si vous avez des questions.



# :deux: - Introduction to SQL

Nous avons vus deux clauses : `WHERE` et  `ORDER BY`
Ainsi que de nombreux opérateurs:
`= , < , > , <= , >= , != , IS , AND , OR , BETWEEN,AND, LIKE`

`WHERE` permet de spécifier à votre script quelles sont des lignes qui vous intéressent.
Il est donc *suivi d'une condition* : `WHERE colonne1 = x`
Dans ces conditions, les opérateurs standards sont utilisables: `= , > , < , >= , <=`

`!=` Signifie *différent de*.

`IS` permet de comparer le *type* de la donnée (integer, text, real...)

`AND` et `OR` permettent de cumuler ou d'assouplir vos conditions. Si mélange des deux, les parenthèses s'imposent !

`SELECT * FROM IMDB.movies`
`WHERE (title_year > 1990 AND title_year < 2000) OR imdb_score < 4 ;`

_Donne moi un film des années 90, ou un très mauvais film_

`BETWEEN AND` sert à définir un intervalle. C'est plus élégant que `> AND <` et ça fonctionne avec les données de type texte (ordre alphabétique classique). 
Ne pas oublier le `AND` (intervalle défini par deux jalons).

`SELECT * FROM IMDB.movies`
`WHERE (title_year BETWEEN 1990 AND 2000) OR imdb_score < 4 ;`

_Même instruction que ci-dessus_

`LIKE` permet de comparer *des morceaux de texte* (et non pas la totalité du texte comme
avec :smiley: % est le caractère "joker" : il se substitue à une suite de caractère indifféremment de son contenu et de sa longueur. Sa place en revanche est très importante:
`WHERE actor_1_name LIKE '%John'` tous ceux qui finissent par John
`WHERE actor_1_name LIKE 'John%'` _tous ceux qui commencent par John_
`WHERE actor_1_name LIKE '%John'` _tous ceux qui contiennent John_

:warning: Important : dans un champs texte, la donnée est case sensitive (contrairement à SQL):
`'John' != 'john'`

`ORDER BY` est une clause permettant de donner un ordre au lignes afin d'utiliser celles qui sont les plus pertinentes. Elle peut être assortie de deux compléments: `DESC` et `LIMIT`

`DESC` indique que le tri est décroissant (du min au max). Le tri croissant est présent par défaut. Il est possible de le rendre explicite via la commande `ASC`
 
`LIMIT` permet de donner un nombre de lignes max à sortir via le `ORDER BY`
La commande ressemble alors à ça :

`SELECT * FROM IMDB.movies`
`WHERE title_year BETWEEN 1990 AND 2000`
`ORDER BY imdb_score DESC`
`LIMIT 15;`

_On sélectionne les 15 meilleurs films des années 1990_


A noter que la clause `WHERE` arrive avant `ORDER BY` (par logique d'efficacité de calcul, il est préférable d'extraire avant de trier).

Enfin le mot de commande `AS` va vous permettre de donner un alias à vos variables et tables. Cette commande va s'avérer de plus en plus utile au fur et à mesure de notre progression ensemble.

`SELECT movie_title AS Title, title_year AS Year, imdb_score AS Score`
`FROM IMDB.movies AS Mesfilms`
`WHERE Year BETWEEN 1990 AND 2000`

Voilà, comme d'habitude je suis dispo pour les questions, et le corrigé va arriver.
Je vous parle souvent de ressources complémentaires que je peux vous pousser pour ceux qui avancent très vite. N'hésitez pas à me le rappeler par MP !

Super journée ! :visage_légèrement_souriant:


