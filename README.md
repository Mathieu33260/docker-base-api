# Préparation et lancement de l'api

### Prérequis

Vous aurez besoin de **[Docker](https://www.docker.com/get-started)** installé sur votre machine.

### Clone des différents repos

Commencez par clôner les différents repos du projet, tous dans le même dossier que l'on nommera **testapi**

```sh
$ git clone git@github.com:Mathieu33260/docker-base-api.git
$ git clone git@github.com:Mathieu33260/api.git
```

### Configuration du projet

Rendez vous ensuite dans le dossier docker-base-api, et lancez le docker-compose.

```sh
$ cd docker-base-api
$ docker-compose up -d
```

Il faut maintenant modifier votre fichier hosts pour rediriger l'IP du container.
Ajoutez cette ligne :

```sh
127.0.0.1 test.api
```

Puis rentrez ces commandes :

```sh
$ docker exec -it testapi-php-fpm bash
cp .env.dist .env
composer install
php bin/console doctrine:schema:create
```

### Requêter l'api

Le projet maintenant configuré, l'api tourne sur :
**http://test.api**

### Documentation de l'api

La documentation de l'api se trouve sur : 
**http://test.api/doc**

