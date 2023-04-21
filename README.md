# Marvelicious

## Description

L'application web Marvelicious est une librarie de comics en ligne qui propose un système de location.

La documentation de l'API Springboot et de l'application web Angular, ainsi que leur code source, sont disponibles sur leurs liens respectifs sur Github. Une image Docker de chaque projet est également accessible sur Docker Hub via les liens fournis.

La configuration YAML pour le déploiement des services est également présentée ci-dessous. Enfin, un APM Elastic a été installé dans l'application web pour permettre sa supervision.

## Présentation

![presentation.gif](resources%2Fpresentation.gif)

## Documentation

### Frontend :
- Web App Angular (Typescript)
- Github : https://github.com/Nayzow/marvelicious/tree/main/frontend
- Docker Hub : https://hub.docker.com/r/nayzow/marvelicious-frontend

### Backend :
- Api Springboot (Java)
- Github : https://github.com/Nayzow/marvelicious/tree/main/backend
- Docker Hub : https://hub.docker.com/r/nayzow/marvelicious-backend

### Database :
- Database MySQL
- Github : https://github.com/Nayzow/marvelicious/tree/main/database
- Docker Hub : https://hub.docker.com/r/nayzow/marvelicious-database

### Serveur :

L'application web tourne sur un serveur nginx dont le proxy redirige les requêtes à l'url :

```
/api
```

Vers l'url de l'api définit dans le fichier de l'application web Angular :

```
nginx.conf
```

## Déploiement

Le déploiement est configuré pour tourner en local. Pour déployer le projet, il suffit de récupérer le fichier "docker-compose.yaml" avec le code ci-dessous :

```yaml
version: '3'
services:
  database:
    image: nayzow/marvelicious-database
    ports:
      - "3306:3306"
      
  api:
    image: nayzow/marvelicious-backend
    ports:
      - "8080:8080"
    depends_on:
      - database
    restart: always

  app:
    image: nayzow/marvelicious-frontend
    ports:
      - "80:80"
```

Lien du fichier de déploiement : https://github.com/Nayzow/marvelicious/blob/main/docker-compose.yaml

Et ensuite d'effectuer cette commande dans le répertoire courant du fichier "docker-compose.yaml" :

```bash
docker-compose up
```

L'application Web est désormais disponible à l'adresse http://localhost

L'API est désormais disponible à l'adresse http://localhost:8080

Vous pouvez également copier la configuration YAML dans la section custom stack sur Portainer ou sur un autre service d'orchéstration de containers.

## Production

Pour que le projet tourne dans un environnement de production il faut lancer l'application en mode production aprés avoir configurer la variable d'environnement "apiUrl" pour les requêtes cotés client dans l'application Angular, par exemple :

```typescript
export const environment = {  
  production: true,  
  apiUrl: 'http://<YOUR_IP>/api'  
};
```

Dans le fichier :

```
src/environnements/environnement.ts 
```

## Supervision

Version de l'apm elastic pour superviser les containers :

```json
"elastic-apm-node": "^3.43.0"
```
