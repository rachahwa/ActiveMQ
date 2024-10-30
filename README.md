# ActiveMQ

# ActiveMQ avec Docker

## Qu'est-ce qu'ActiveMQ ?

[Apache ActiveMQ](https://activemq.apache.org/) est un broker de messages open-source, codé en Java qui permet la communication entre différentes applications via des messages et de synchroniser les données d'entreprise. Il prend en charge les protocoles de messagerie les plus populaires, tels que AMQP, MQTT et STOMP. 

## Prérequis

Avant de commencer, assurez-vous d'avoir installé :

- [Docker](https://www.docker.com/get-started)
- [Docker Compose](https://docs.docker.com/compose/)

 ## Qu'est-ce que Docker ?

[Docker](https://www.docker.com/) est la plateforme de conteneurisation la plus utilisée. 

## Interface graphique de Docker

Docker propose une interface graphique, appelée **Docker Desktop**, qui simplifie la gestion des conteneurs. On peut facilement y visualiser les conteneurs en cours d'exécution ou encore parcourir les images.

Ayant travaillé directement sur mon Mac en local, l'interface m'a simplifié le travail. En effet, cela est dû aux problèmes de *binding* de ports : *lorsque l'on lie un port d’un conteneur à un port de la machine hôte, ce port de la machine hôte devient occupé par le service du conteneur*. Cela signifie que l'on *ne peut pas exécuter un autre service sur ce même port de la machine hôte tant que le conteneur est en cours d'exécution*. Il faut alors *utiliser un autre port ou le libérer*.


## Lancer ActiveMQ avec Docker

Voici comment lancer ActiveMQ à l'aide de Docker pour chacune des cas du TP ActiveMQ:

### Étape 1 : Récupérer le fichier `docker-compose.yml`

Pour récupérer le projet, commencez par cloner le dépôt avec la commande suivante :

```bash
git clone https://github.com/thibferr76/classes/blob/main/activemq_tp-cyber.zip
```
Vous y trouverez 4 fichiers d'ActiveMQ que vous pourrez distinguer avec les années.

Dans le terminal, naviguez vers le répertoire où se trouve votre fichier `docker-compose.yml` de l'année souahité et exécutez la commande suivante :

```bash
docker-compose up -d
```

`docker-compose up` est une commande qui démarre votre application Docker et tous les services définis dans le fichier `docker-compose.yml`. Elle peut effectuer plusieurs tâches, notamment :

- Créer des images Docker
- Créer des réseaux et des volumes
- Démarrer des conteneurs
- Lier les conteneurs ensemble

### Étape 2 : Vérifier les conteneurs en cours d'exécution

Pour vérifier que vos conteneurs ActiveMQ sont bien lancés, utilisez la commande suivante :

```bash
docker container ls
```

Cette commande m'a été et pourra vous être assez utile, puisqu'elle permet d'identifier rapidement quel conteneur est actif.

Ou encore celle-ci qui permet de visualiser tous les conteneurs qu'ils soient actifs ou pas:

```bash
docker ps -a
```

### Étape 3 : Accéder à l'interface d'ActiveMQ

Une fois que vous avez lancé ActiveMQ avec `docker-compose up -d`, vous pouvez accéder à l'interface web d'ActiveMQ depuis votre navigateur via l'URL suivante :

`http://localhost:8161`

**Identifiants de connexion par défaut :**

- **Nom d'utilisateur** : `admin`
- **Mot de passe** : `admin`

https://github.com/rachahwa/ActiveMQ/issues/2#issue-2625124003)
https://private-user-images.githubusercontent.com/184439226/381703357-8976776e-5929-4e68-ba6a-f883444b290e.png?jwt=eyJhbGciOiJIUzI1NiIsInR5cCI6IkpXVCJ9.eyJpc3MiOiJnaXRodWIuY29tIiwiYXVkIjoicmF3LmdpdGh1YnVzZXJjb250ZW50LmNvbSIsImtleSI6ImtleTUiLCJleHAiOjE3MzAzMTY5ODEsIm5iZiI6MTczMDMxNjY4MSwicGF0aCI6Ii8xODQ0MzkyMjYvMzgxNzAzMzU3LTg5NzY3NzZlLTU5MjktNGU2OC1iYTZhLWY4ODM0NDRiMjkwZS5wbmc_WC1BbXotQWxnb3JpdGhtPUFXUzQtSE1BQy1TSEEyNTYmWC1BbXotQ3JlZGVudGlhbD1BS0lBVkNPRFlMU0E1M1BRSzRaQSUyRjIwMjQxMDMwJTJGdXMtZWFzdC0xJTJGczMlMkZhd3M0X3JlcXVlc3QmWC1BbXotRGF0ZT0yMDI0MTAzMFQxOTMxMjFaJlgtQW16LUV4cGlyZXM9MzAwJlgtQW16LVNpZ25hdHVyZT0wOWY3OTUyYzI2NmMxNWY3Y2I4NjQ3MGU5Nzk3MzExODNiODhlZmFhYzIwYTM0ZWU1MDNlOTIxOTdiYmNhYjBlJlgtQW16LVNpZ25lZEhlYWRlcnM9aG9zdCJ9.vkNGzMFXxrjpNMF6yDPSuXZoaY-XNKTMy08EMukEWJY
