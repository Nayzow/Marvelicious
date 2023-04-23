# Marvelicious database

Base de donnée MySql pour stocker les données du projet. La base de données contient des comics lié à séries et auteur, ainsi que des utilisateurs pouvant commenter et emprunter des comics.

## Informations

Le script SQL pour la création de la base de donnée se situe dans le dossier resources.

```
database : library
login : root
password : test
```

## Installation

#### 1. Build l'image

```bash
docker build -t marvelicious-database .
```

#### 2. Lancer le container à partir de l'image

```bash
docker run --name marvelicious-database -p 3306:3306 -d marvelicious-database
```

## UML

![uml.png](resources%2Fuml.png)