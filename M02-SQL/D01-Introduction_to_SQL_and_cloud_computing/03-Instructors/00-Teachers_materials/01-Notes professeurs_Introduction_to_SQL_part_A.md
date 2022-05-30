# Week 2A Teacher's Notes

* [About the course](#_1fob9te) 
* [Course Objective](#_3znysh7) 
* [Course Timing](#_2and92p0) 
* [What to prepare](#_tyjcwt) 
* [Part 1 - What is a database](#_60x5xxtyb7eu) 
* [Part 2 - The tools we will use](#_wbb7z0bb9tx0) 
* [Part 3 - Instructions and Basic Clauses](#_34qua6r1j9ka) 
* [Exercise](#_3dy6vkm) 

    * [I) CREATE TABLE](#_hrb5tkqu2bzw) 
    * [II) INSERT INTO](#_oxnv9mf4vqqo) 
    * [III) SELECT](#_qma5emwg3n1e) 
    * [IV) UPDATE](#_50ncifj3u2eb) 
    * [V) ALTER TABLE](#_cs4effz45k9f)
    * [VI) DELETE](#_2snh5g127u92)

* [Other Tips](#_35nkun2) 

# Introduction to SQL & Cloud Computing 🚀

## About the course 📗

During this course, we will talk about Cloud Computing and teach students how to build robust data infrastructure. The goal is for them to understand **Data Lake**, **Data Warehouse**, ETL.

We will also introduce SQL to our students. The main objective of the course is to make students understand the difference between a Database and a Database Management System (DBMS) and the difference between SQL and Relational Database Management System like MySQL, PostgreSQL etc. We will also teach them some database writing queries on Google Cloud Platform.

## Course objective 🏁

- Create a Data Lake
- To know what a database is and how to create them
- Why we use Databases (rather than Excel for example)
- Write our first SQL queries

## Timing of the course 🕛

20 min: Classic Data infrastructure (in the `Introduction_to_Cloud_Computing.ipynb` course)

30 min: Exercise - Create their own Data Lake (in the `Fill_a_datalake.ipynb` exercise)

30 min: Set up their Cloud SQL instance (in the `Introduction_to_SQL_Part_A.ipynb` course)

40 min: Basic clauses (SELECT, UPDATE, ALTER TABLE etc.. in the `Introduction_to_SQL_Part_A.ipynb` course)

40 min: Exercises

## What to prepare 📚

Tell students to create a [GCP account](https://cloud.google.com). They will need to: 

- Have a Gmail address 
- Give credit card information 

Tell them not to worry, GCP will give them $300 credit in addition to 90 days free trial. So **No money will be taken out of their account**. 

(FYI, the whole SQL course will cost around $30)


## Part 1 - Classic Data infrastructure

Here you won't have much time but the goal is to teach students what is a **Data Lake** / **Data Warehouse** / **ETL**. It's important for them to learn that so that they also understand why they have to learn SQL. 

Therefore try to connect SQL with this whole infrastructure. 

Then walk them through creating a GCP account and how to built a Data Lake using Google Cloud Storage. 


## Part 2 - Exercise - Create their own Data Lake

This exercise should relatively easy for students. HOWEVER, **MAKE SURE THEY UPLOAD ALL FILES TO THEIR DATALAKE** as they will need it later on when using Google Big Query. 

(FYI, we will use these files to create SQL Tables of Google Big Query and use these tables to learn SQL in `introduction_to_SQL_part_B` course)

## Part 3 - Set up their Cloud SQL instance 👩💻❔


Now that everything is ready in GCP, you can start talking about SQL. First start with a little bit of theory.  Your goal is to make it clear how a database is structured. After giving a definition of what a Database is here is what you should focus on:

- What is a table
- What is a schema
- What the rows represent
- What the columns represent
- Give the main types of data that can be found

You will notice that we have simply put in the course:

- TEXT
- INTEGER
- DATETIME
- REAL / FLOAT
- NULL

There are many other types of data, so don't be afraid to look around a bit so that you don't get caught off guard by the students.

You will then have to explain the difference between a RDBMS (Relational Database Management System) and SQL. It is important to emphasize this because there is often a lot of confusion for students. SQL is a language whereas RDBMS are the tools that will allow you to manage your databases. These RDBMS are all based on the SQL language.

However, you will see that some RDBMS have SQL clauses that others do not, this is normal. As RDBMS have developed, they have also developed their own SQL code. This is often the reason for the confusion.

We will finish by explaining how Relational Database are useful. It is not bad to compare the performance of the Database with Excel because the students know what it is.

Then show them how to set a Cloud SQL instance (simply follow the tutorial in `Introduction_to_SQL_part_A` ipynb)



## Part 4 - BASIC Clauses 🧰

Now that you have a cloud SQL instance, you will need to connect to it using Google terminal and them type: 

`gcloud sql connect YOURINSTANCENAME --user=root`

You might need to provide a password if you set one when you created your instance. Then you will need to create a Database and use it:


`CREATE DATABASE antoinekrajnc;`

Once this is done, you will have to move to the database by doing :

`USE antoinekrajnc;`

Once this is done, you can start writing your clauses.

## Part 3 - Basic instructions and clauses 📃

So here we will create and structure a database. We're going to imagine that we're a Food Truck chain in Paris and we want to organize our data. It is in this context that you will write your clauses.

Explain the difference between a clause and a statement. A clause is just one line of code (e.g. SELECT ... FROM) whereas a statement or query is a set of clauses (e.g. SELECT ... FROM table):

```sql
SELECT * FROM table

WHERE column = x

ORDER BY column_2 DESC;
```

Be clear about the importance of IDs and the difference between a primary key and a secondary key. This will allow you to lay the groundwork for explaining JOINs.

## Exercise 🖊

During this exercise, we will assume that we are a private driver company similar to UBER. We will call this company &quot;Drivers&quot;. We will need to create a structure for the box database.

## I) CREATE TABLE 📈

Chauffeurs needs to manage its drivers, users and employees and also has data about the cities it wants to expand into.

1. Create a table for Drivers, it should contain the following columns:
  1. ID
  2. First name
  3. Name
  4. Age
  5. Address
  6. Date of license
  7. Number of accidents
  8. Average score given by users

1. Create a Users table with the following columns
  1. ID
  2. First name
  3. Name
  4. Age
  5. Average score given by the drivers

1. Create an Employees table with the following columns:
  1. ID
  2. First name
  3. Name
  4. Number of years of experience
  5. Number of kilometers used at Drivers

1. Create a Cities table with the following columns
  1. ID
  2. Name
  3. Size (in square kilometers)
  4. Number of inhabitants

## II) INSERT INTO

Let's add values to each table to make sure everything works:

1. Insert 5 rows in Drivers (no matter the values)
2. Insert 5 rows in Users (whatever the values are)
3. Insert 5 rows in Cities (no matter what the values are)
4. Insert 5 rows in Employees (no matter the values)

## III) SELECT 🖱

We would like to show our management that the database is working properly so we want to do basic tests.

Now, we would like to show that our database is working properly to our manager to our manager. Let's do some tests:

1. Select all columns in Drivers, Users, Employees and Cities.
2. Select all accidents in Drivers.
3. Select all dates when drivers got their license.

## IV) UPDATE 🔄

We made an error when we inserted our first row into each of our tables.

1. Change the age of the first driver to 28.
2. Change the first name of the first user to John
3. Change the number of years of experience of the first employee to 6 years.

## V) ALTER TABLE 

We just realized that it would be useful to have the average number of cars in each city so that we can evaluate the level of traffic jams and see if it is worthwhile to set up there.

1. Add a Number of Cars column to the Cities table

## VI) DELETE 🚮

One of our employees just left the company, we need to remove him from our database

1. Delete the last employee in the Employees table

## Other Tips 💡

Students will make a lot of syntax mistakes, which is completely normal. Remember to repeat often not to forget semicolons or parentheses etc. It will eventually sink in.

While the students are working, feel free to move around the room to see what's going on and to see if there are any lost students. Sometimes they don't dare raise their hands.

Set up peer programming (two people coding at the same time). Working in a group is very good because you always have someone who can teach the other person something. **USE BREAKOUT ROOMS in ZOOM**

Once the exercises are done, put the solutions in their session folder so they can come back to them when they are done!

Finally, the exercises are long, it's perfectly normal if you can't finish. Either catch up next time or move on to something else for the next class. If there are things you need to skip, skip what the students can learn on their own by reading the lecture notes. Your goal is to give them the keys to understand on their own.

#### FRENCH ####
# Semaine 2A Notes Professeurs

* [A propos du cours](#_1fob9te) 
* [Objectif du cours](#_3znysh7) 
* [Timing du cours](#_2et92p0) 
* [Ce qu'il faut préparer](#_tyjcwt) 
* [Partie 1 - Qu'est ce qu'une base de données](#_60x5xxtyb7eu) 
* [Partie 2 - Les outils que nous allons utiliser](#_wbb7z0bb9tx0) 
* [Partie 3 - Instructions et Clauses fondamentales](#_34qua6r1j9ka) 
* [Exercise](#_3dy6vkm) 

    * [I) CREATE TABLE](#_hrb5tkqu2bzw) 
    * [II) INSERT INTO](#_oxnv9mf4vqqo) 
    * [III) SELECT](#_qma5emwg3n1e) 
    * [IV) UPDATE](#_50ncifj3u2eb) 
    * [V) ALTER TABLE](#_cs4effz45k9f)
    * [VI) DELETE](#_2snh5g127u92)

* [Autre Tips](#_35nkun2) 

# Introduction à SQL 🚀

## À propos du cours 📗

Au cours de ce cours, nous parlerons du Cloud Computing et enseignerons aux étudiants comment créer une infrastructure de données robuste. L'objectif est qu'ils comprennent **Data Lake**, **Data Warehouse**, ETL.

Nous présenterons également SQL à nos étudiants. L'objectif principal du cours est de faire comprendre aux étudiants la différence entre une base de données et un système de gestion de base de données (SGBD) et la différence entre SQL et un système de gestion de base de données relationnelle comme MySQL, PostgreSQL, etc. Nous leur apprendrons également quelques requêtes d'écriture de base de données sur Plateforme Google Cloud.

## Objectif du cours 🏁

- Créer un lac de données
- Savoir ce qu'est une base de données et comment les créer
- Pourquoi utilisons-nous des bases de données (plutôt qu'Excel par exemple)
- Ecrire nos premières requêtes SQL

## Horaire du cours 🕛

20 min : Infrastructure de données classique (dans le cours `Introduction_to_Cloud_Computing.ipynb`)

30 min : Exercice – Créer son propre lac de données (dans l'exercice `Fill_a_datalake.ipynb`)

30 min : Configurer son instance Cloud SQL (dans le cours "Introduction_to_SQL_Part_A.ipynb")

40 min : Clauses de base (SELECT, UPDATE, ALTER TABLE etc.. dans le cours `Introduction_to_SQL_Part_A.ipynb`)

40 min : Exercices

## Que préparer 📚

Dites aux élèves de créer un [compte GCP](https://cloud.google.com). Ils devront :

- Avoir une adresse Gmail
- Donner les informations de carte de crédit

Dites-leur de ne pas s'inquiéter, GCP leur offrira un crédit de 300 $ en plus d'un essai gratuit de 90 jours. Donc **Aucun argent ne sera retiré de leur compte**.

(Pour info, l'ensemble du cours SQL coûtera environ 30 $)


## Partie 1 - Infrastructure de données classique

Ici, vous n'aurez pas beaucoup de temps mais l'objectif est d'apprendre aux étudiants ce qu'est un **Data Lake** / **Data Warehouse** / **ETL**. Il est important pour eux d'apprendre cela afin qu'ils comprennent également pourquoi ils doivent apprendre SQL.

Essayez donc de connecter SQL avec toute cette infrastructure.

Ensuite, expliquez-leur comment créer un compte GCP et comment créer un lac de données à l'aide de Google Cloud Storage.


## Partie 2 - Exercice - Créer son propre lac de données

Cet exercice devrait être relativement facile pour les étudiants. CEPENDANT, **ASSUREZ-VOUS QU'ILS TELECHARGENT TOUS LES FICHIERS DANS LEUR DATALAKE** car ils en auront besoin plus tard lors de l'utilisation de Google Big Query.

(Pour info, nous utiliserons ces fichiers pour créer des tables SQL de Google Big Query et utiliserons ces tables pour apprendre SQL dans le cours `introduction_to_SQL_part_B`)

## Partie 3 - Configurer son instance Cloud SQL 👩💻❔


Maintenant que tout est prêt dans GCP, vous pouvez commencer à parler de SQL. Commencez d'abord par un peu de théorie. Votre objectif est d'expliquer clairement comment une base de données est structurée. Après avoir donné une définition de ce qu'est une base de données, voici ce sur quoi vous devriez vous concentrer :

- Qu'est-ce qu'une table
- Qu'est-ce qu'un schéma
- Ce que représentent les lignes
- Ce que représentent les colonnes
- Donner les principaux types de données que l'on peut trouver

Vous remarquerez que nous avons simplement mis dans le cours :

- TEXTE
- ENTIER
- DATEHEURE
- VRAI / FLOTTEUR
- NUL

Il existe de nombreux autres types de données, alors n'ayez pas peur de regarder un peu autour de vous pour ne pas être pris au dépourvu par les étudiants.

Vous devrez ensuite expliquer la différence entre un SGBDR (Système de Gestion de Base de Données Relationnel) et SQL. Il est important de le souligner car il y a souvent beaucoup de confusion pour les étudiants. SQL est un langage alors que les SGBDR sont les outils qui vous permettront de gérer vos bases de données. Ces SGBDR sont tous basés sur le langage SQL.

Cependant, vous verrez que certains SGBDR ont des clauses SQL que d'autres n'ont pas, c'est normal. Au fur et à mesure que les SGBDR se sont développés, ils ont également développé leur propre code SQL. C'est souvent la raison de la confusion.

Nous terminerons en expliquant en quoi les Bases de Données Relationnelles sont utiles. Il n'est pas mal de comparer les performances de la base de données avec Excel car les étudiants savent de quoi il s'agit.

Montrez-leur ensuite comment définir une instance Cloud SQL (suivez simplement le tutoriel dans `Introduction_to_SQL_part_A` ipynb)



## Partie 4 - Clauses de BASE 🧰

Maintenant que vous disposez d'une instance cloud SQL, vous devez vous y connecter à l'aide du terminal Google et tapez :

`gcloud sql connect YOURINSTANCENAME --user=root`

Vous devrez peut-être fournir un mot de passe si vous en avez défini un lors de la création de votre instance. Ensuite, vous devrez créer une base de données et l'utiliser :


`CRÉER UNE BASE DE DONNÉES antoinekrajnc;`

Une fois cela fait, vous devrez vous déplacer vers la base de données en faisant :

`USE antoinekrajnc;`

Une fois cela fait, vous pouvez commencer à rédiger vos clauses.

## Partie 3 - Instructions et clauses de base 📃

Nous allons donc ici créer et structurer une base de données. Nous allons imaginer que nous sommes une chaîne de Food Truck à Paris et que nous voulons organiser nos données. C'est dans ce contexte que vous rédigerez vos clauses.

Expliquez la différence entre une clause et un énoncé. Une clause n'est qu'une ligne de code (par exemple SELECT ... FROM) alors qu'une instruction ou requête est un ensemble de clauses (par exemple SELECT ... FROM table):

```sql
SELECT * FROM table

O colonne = x

ORDER BY colonne_2 DESC;
```

Soyez clair sur l'importance des identifiants et la différence entre une clé primaire et une clé secondaire

Précisez bien l'importance des ID ainsi que la différence entre une clé primaire et une clé secondaire. Cela vous permettra de poser les jalons pour expliquer les JOIN.

## Exercise 🖊

Durant cet exercice, nous allons supposer que nous sommes une entreprise de chauffeurs privés similaire à UBER. Nous appellerons cette entreprise &quot;Chauffeurs&quot;. Nous allons devoir créer une structure pour la base de données de la boîte.

## I) CREATE TABLE 📈

Chauffeurs doit manager ses drivers, ses utilisateurs et ses employés et possède aussi des données sur les villes dans lesquelles elle veut s'implanter.

1. Créez une table pour les Drivers, elle devra contenir les colonnes suivantes :
  1. ID
  2. Prenom
  3. Nom
  4. Age
  5. Adresse
  6. Date d'obtention du permis
  7. Nombre d'accidents
  8. Note moyenne donnée par les utilisateurs

1. Créez un table Utilisateurs avec les colonnes suivantes
  1. ID
  2. Prenom
  3. Nom
  4. Age
  5. Note moyenne donnée par les drivers

1. Créez une table Employés avec les colonnes suivantes :
  1. ID
  2. Prenom
  3. Nom
  4. Nombre d'années d'expérience
  5. Nombre de kilomètres utilisés chez Chauffeurs

1. Créez un table Villes avec les colonnes suivantes
  1. ID
  2. Nom
  3. Taille (en kilomètre carrés)
  4. Nombre d'habitants

## II) INSERT INTO

Ajoutons des valeurs dans chaque table pour vérifier que tout fonctionne bien :

1. Insérez 5 lignes dans Drivers (qu'importe les valeurs)
2. Insérez 5 lignes dans Utilisateurs (qu'importe les valeurs)
3. Insérez 5 lignes dans Villes (qu'importe les valeurs)
4. Insérez 5 lignes dans Employés (qu'importe les valeurs)

## III) SELECT 🖱

We would like to show our management that the database is working properly so we want to do basic tests.

Maintenant, nous voudrions montrer que notre base de données fonctionne bien à notre manager à notre manager. Faisons quelques tests :

1. Sélectionnez toutes les colonnes dans Drivers, Utilisateurs, Employés et Villes.
2. Sélectionnez tous les accidents dans Drivers.
3. Sélectionnez toutes les dates auxquelles les drivers ont eu leur permis de conduire.

## IV) UPDATE 🔄

Nous avons fait une erreur lorsque nous avons inséré notre première ligne dans chacune de nos tables.

1. Changez l'âge du premier driver à 28 ans.
2. Changez le prénom du premier utilisateur à John
3. Changez le nombre d'années d'expérience du premier employé à 6 ans.

## V) ALTER TABLE 

Nous venons de nous rendre compte qu'il serait utile d'avoir le nombre de voiture moyen dans chaque ville pour qu'on puisse évaluer le niveau de bouchons et voir si cela vaut le coup de s'y implanter.

1. Ajoutez un colonne Nombre de Voitures dans la table Villes

## VI) DELETE 🚮

Un de nos employés vient de quitter la boîte, nous devons l'enlever de notre base de données

1. Effacez le dernier employé dans la table Employés


## Autre Tips 💡

Les étudiants vont faire beaucoup de fautes de syntaxes, ce qui est tout à fait normal. N'oubliez pas de répétez souvent de ne pas oublier les points virgule ou les parenthèses etc. Ca finira par rentrer.

Pendant que les étudiants travaillent, n'hésitez pas à bouger dans la salle pour voir ce qu'il s'y passe et voir s'il y a des étudiants perdus. Ca arrive qu'ils n'osent pas lever la main.

Mettez en place du Pair Programming (deux personnes qui codent en même temps). Travailler en groupe est très bon car vous avez toujours quelqu'un qui peut apprendre quelque chose à l'autre. **UTILISEZ les BREAKOUT ROOMS dans ZOOM**

Une fois que les exercices sont terminés, mettez les solutions dans le dossier de leur session pour qu'ils puissent revenir dessus une fois qu'ils ont finit !

Enfin les exercices sont longs, c'est tout à fait normal si vous n'arrivez pas à finir. Soit vous rattraperez la prochaine fois soit vous passerez à autre chose pour le prochain cours. Si vous devez passer certaines choses, passez ce que les élèves pourront apprendre de manière autonome en lisant les notes du cours. Votre but à vous est de leur donner les clés pour comprendre par eux-mêmes.