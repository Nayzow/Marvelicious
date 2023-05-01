# Books service API

API Java Springboot qui renvoie des données relatives à des comics.

## Installation

#### 1. Clonez le dépôt du projet en utilisant la commande

```bash
git clone https://github.com/Nayzow/books-service-backend
```

#### 2. Installation

#### Installation avec Maven

#### 1. À la racine du projet, installez les dépendances en utilisant la commande

```bash
mvn clean install
```

#### 2. Démarrez l'application avec la commande :

```bash
mvn spring-boot:run
```

#### Installation avec Docker

#### 1. Build l'image Docker

```bash
docker build -t books-service-backend .
```

####  2. Run le conteneur Docker

```bash
docker run --name books-service-backend -p 8080:8080 -d books-service-backend
```

### Routes de l'API

### GET

```
/books : renvoie touts les comics.
```

```
/books/{id} : renvoie le comic avec un id donné.
```

```
/books/{id}/statements : renvoie tous les comics disponibles lié à un comic avec un id donné.
```

```
/books/{id}/comments : renvoie tous les commentaires lié à un comic avec un id donné.
```

```
/series : renvoie toutes les séries de comics.
```

```
/series/{id} : renvoie la série de comics avec un id donné.
```

```
/series/{id} : renvoie tous les comics lié à une série avec un id donné.
```

```
/editors : renvoie touts les éditeurs de comics.
```

```
/editors/{id} : renvoie l'éditeur de comics avec un id donné.
```

```
/editors/{id}/series : renvoie toutes les séries de comics lié à un éditeur avec un id donné.
```

```
/statements : renvoie les états de touts les comics.
```

```
/statements/{id} : renvoie l'état d'un comics à partir d'un id donné.
```

```
/borrowings : renvoie toutes les emprunts des utilisateurs.
```

```
/borrowings/{id} : renvoie un emprunt avec un id donné.
```

```
/users : renvoie touts les utilisateurs.
```

```
/users/{id} : renvoie un utilisateur avec un id donné.
```

```
/users/{id} : renvoie tous les emprunts lié à un utilisateur avec un id donné.
```

```
/login : renvoie l'utilisateur avec le username et le mot de passe correspondant.
```

### POST

```
/books : Ajouter un comic.
```

```
/statements : Ajouter un état de comic.
```

```
/borowings : Ajouter un emprunts.
```

```
/comments : Ajouter un commentaire.
```

```
/editors : Ajouter un éditeur
```

```
/series : Ajouter une série de comics.
```

```
/users : Ajouter un utilisateur.
```

#### DELETE

```
/books/{id} : Supprimer un comic.
```

```
/statements/{id} : Supprimer un état de comic.
```

```
/borowings/{id} : Supprimer un emprunt.
```

```
/comments/{id} : Supprimer un commentaire.
```

```
/editors/{id} : Supprimer un éditeur
```

```
/series/{id} : Supprimer une série de comics.
```

```
/users/{id} : Supprimer un utilisateur.
```
