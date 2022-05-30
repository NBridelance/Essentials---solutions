# Week 2B Teacher's Notes

* [About the course](#_1fob9te)
* [Course Objectives](#_3znysh7)
* [Course Timing](#_2and92p0)
* [What to prepare](#_tyjcwt)
    * [Part 1 - WHERE](#_12iziwv5ifzf)
    * [Part 2 - AND / OR](#_rwalk477oa8)
    * [Part 3 - BETWEEN](#_bq1bsceigr5h)
    * [Part 4 - LIKE](#_9gjp1avugggg)
    * [Part 5 - ORDER BY](#_23pr12ihwre5)
    * [Part 6 - AS](#_d6lihkt2qvi1)
* [Other Tips](#_1t3h5sf)

# Introduction to SQL - Part B 🚀

## About the course 📗

In this course, we will build very simple ETL that will transfer data from Google Cloud Storage to Google Big Query. Then we will see database reading clauses and we will do a lot of practice.

## Course objectives 🏁

- Transfer Data from Google Cloud Storage to Big Query
- Filter results with WHERE
- Create conditions with AND and OR
- Create ranges with BETWEEN
- Search for specific patterns with LIKE
- Sort results with ORDER BY


## Timing of the course 🕛

30 min: From Datalake to Data Warehouse

30 min: Basic reading clauses

90 min: Exercise


## What to prepare 📚

Tell students to read `From_Datalake_to_Datawarehouse.ipynb` course in advance so that they can start doing the exercise `ETL_to_Big_Query.ipynb`. Of course, you will do the exercises in class as well but it's good that you save a little bit of time if students already know what to do. 


## Part 1 - From Datalake to Data Warehouse 

Here, your goal is to explain what an ETL is and you will illustrate that using Big Query and *Data Transfer*. Follow exactly the tutorials in `ETL_to_Big_Query.ipynb`. 

Again, **YOU WILL NEED THE DATASETS LATER ON IN THE COURSE**. Therefore, you need to make sure students were able to transfer them all. 

It can be a little tedious and repetitive but let them know that it's also how they are going to memorize. 

## Part 2 - Basic Reading clause 📍


### Where

Explaining a clause is relatively simple so we don't have much to add in each part. Nevertheless, here are the few points that students have a little trouble with so it's good to emphasize:

- Explain the different operators

### AND / OR ⚖

Students in general know the difference between AND and OR but it is still good to re-specify. A good way to explain it quickly is to draw the following diagram:

![](RackMultipart20210716-4-1fih9qv_html_4095d172ea326d0f.gif)

### BETWEEN 👉👈

In this part, it's good to start creating an interval with WHERE and then tell the students that there is an easier way to do it with BETWEEN. So you can do:

```sql
SELECT movie_title FROM IMDB.movies
WHERE title year 1980 AND title year 1990;
```

Then

```sql
SELECT movie_title FROM IMDB.movies
WHERE title_year BETWEEN 1980 AND 1990;
```

### LIKE 👍

It's good to look for patterns in strings and that's why LIKE comes into play.

Be careful though, depending on the DBMS, LIKE can become ILIKE. It is good to specify this to the students.

LIKE is case sensitive, so be sure to put the capital letters in the right place.

### ORDER BY 📈

Nothing to add

### AS 🔃

Working with aliases and important in Google Big Query but not in all DBMS. So it will be good to make this clear to students, the same way it is written in the part &quot;What to prepare&quot;.

 On the other hand, do not go into too much detail right away since they have not yet seen the aggregation functions or the JOINs. Just point out that they have to be careful with this and that they will understand why in the next class.

## Other tips 💡

Sometimes you may get your code wrong or lose track. This is completely normal, it's not at all the same to explain code and write it in front of people as it is for yourself. So don't panic if you find yourself making a mistake in front of your students, just explain that you made a mistake and why and move on.

In any case, don't do the foolish thing of letting one of your mistakes go because you are afraid of losing face. If your students notice the mistake and want to understand, they will eventually find that you made a mistake.

Depending on your class, you will have some people who go faster than others. Since the exercises are relatively easy, some may finish before others. In this case, ask them to register on [HackerRank](http://hackerrank.com/) and do the exercises we have marked. The exercises are not easy so look at the platform before you go to class.

Once the exercises are finished, put the solutions in their session folder so they can come back to them when they are done!

#### FRENCH ####
# Week 2B Notes Professeurs

* [A propos du cours](#_1fob9te)

* [Objectifs du cours](#_3znysh7)

* [Timing du cours](#_2et92p0)

* [Ce qu'il faut préparer](#_tyjcwt)

    * [Partie 1 - WHERE](#_12iziwv5ifzf)
    * [Partie 2 - AND / OR](#_rwalk477oa8)
    * [Partie 3 - BETWEEN](#_bq1bsceigr5h)
    * [Partie 4 - LIKE](#_9gjp1avugggg)
    * [Partie 5 - ORDER BY](#_23pr12ihwre5)
    * [Partie 6 - AS](#_d6lihkt2qvi1)

* [Autres Tips](#_1t3h5sf)

# Introduction à SQL - Partie B 🚀

## A propos du cours 📗

Dans ce cours, nous allons créer un ETL très simple qui transférera les données de Google Cloud Storage vers Google Big Query. Ensuite, nous verrons des clauses de lecture de base de données et nous ferons beaucoup de pratique.

## Objectifs du cours 🏁

- Transférer des données de Google Cloud Storage vers Big Query
- Filtrer les résultats avec WHERE
- Créer des conditions avec AND et OR
- Créer des gammes avec BETWEEN
- Recherche de motifs spécifiques avec LIKE
- Trier les résultats avec ORDER BY


## Horaire du cours 🕛

30 min : De Datalake à Data Warehouse

30 min : Clauses de lecture de base

90 min : Exercice


## Que préparer 📚

Dites aux étudiants de lire le cours `From_Datalake_to_Datawarehouse.ipynb` à l'avance afin qu'ils puissent commencer à faire l'exercice `ETL_to_Big_Query.ipynb`. Bien sûr, vous ferez aussi les exercices en classe mais c'est bien de gagner un peu de temps si les élèves savent déjà quoi faire.


## Partie 1 - De Datalake à Data Warehouse

Ici, votre objectif est d'expliquer ce qu'est un ETL et vous allez l'illustrer en utilisant Big Query et *Data Transfer*. Suivez exactement les tutoriels dans `ETL_to_Big_Query.ipynb`.

Encore une fois, ** VOUS AUREZ BESOIN DES ENSEMBLES DE DONNÉES PLUS TARD DANS LE COURS **. Par conséquent, vous devez vous assurer que les étudiants ont pu tous les transférer.

Cela peut être un peu fastidieux et répétitif, mais faites-leur savoir que c'est aussi la façon dont ils vont mémoriser.

## Partie 2 - Clause de lecture de base 📍


### WHERE

Expliquer une clause est relativement simple, nous n'avons donc pas grand-chose à ajouter dans chaque partie. Néanmoins, voici les quelques points avec lesquels les étudiants ont un peu de mal donc il est bon de souligner :

- Expliquer les différents opérateurs

### AND / OR

Les étudiants en général connaissent la différence entre ET et OU, mais il est toujours bon de re-spécifier. Une bonne façon de l'expliquer rapidement est de dessiner le schéma suivant :

![](RackMultipart20210716-4-1fih9qv_html_4095d172ea326d0f.gif)

### BETWEEN 👉👈

Dans cette partie, il est bon de commencer à créer un intervalle avec WHERE, puis de dire aux élèves qu'il existe un moyen plus simple de le faire avec BETWEEN. Vous pouvez donc faire :

```sql
SELECT movie_title FROM IMDB.movies
WHERE title year 1980 AND title year 1990;
```

Then

```sql
SELECT movie_title FROM IMDB.movies
WHERE title_year BETWEEN 1980 AND 1990;
```

### LIKE

Il est bon de rechercher des motifs dans les cordes et c'est pourquoi LIKE entre en jeu.

Attention cependant, selon les SGBD, LIKE peut devenir ILIKE. Il est bon de le préciser aux élèves.

LIKE est sensible à la casse, alors assurez-vous de mettre les majuscules au bon endroit.

### ORDER BY 📈

Rien à ajouter

### AS

Travailler avec des alias et important dans Google Big Query mais pas dans tous les SGBD. Il sera donc bon de faire comprendre cela aux étudiants, de la même manière qu'il est écrit dans la partie &quot;Ce qu'il faut préparer&quot;.

 En revanche, n'entrez pas trop dans les détails tout de suite car ils n'ont pas encore vu les fonctions d'agrégation ou les JOIN. Faites simplement remarquer qu'ils doivent faire attention à cela et qu'ils comprendront pourquoi au cours suivant.

## Autres astuces 💡

Parfois, vous pouvez vous tromper dans votre code ou perdre le fil. C'est tout à fait normal, ce n'est pas du tout la même chose d'expliquer du code et de l'écrire devant des gens que pour soi. Alors ne paniquez pas si vous vous retrouvez à faire une erreur devant vos élèves, expliquez simplement que vous avez fait une erreur et pourquoi et passez à autre chose.

Dans tous les cas, ne faites pas la bêtise de laisser passer une de vos erreurs parce que vous avez peur de perdre la face. Si vos élèves remarquent l'erreur et veulent comprendre, ils finiront par découvrir que vous avez fait une erreur.

En fonction de votre classe, vous aurez des personnes qui iront plus vite que d'autres. Comme les exercices sont relativement faciles, certains peuvent finir avant d'autres. Dans ce cas, demandez-leur de s'inscrire sur [HackerRank](http://hackerrank.com/) et de faire les exercices que nous avons notés. Les exercices ne sont pas faciles alors regardez la plate-forme avant d'aller en classe.

Une fois les exercices terminés, rangez les solutions dans leur dossier de session pour qu'ils puissent y revenir lorsqu'ils auront terminé !