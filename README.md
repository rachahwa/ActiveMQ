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


<img width="1259" alt="Capture d’écran 2024-10-30 à 21 18 27" src="https://github.com/user-attachments/assets/718b8d87-7dc5-4680-ac5c-a88c23d32066">



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


**Scan du réseau :**

Dans mon cas l'adresse ip est la même pour les 4 cas :

<img width="639" alt="nmap2015" src="https://github.com/user-attachments/assets/a6e3118d-a826-44f5-802c-522409b25798">

Le port pour ActiveMQ est le 8161



**Adresse IP :**

Cette commande vous permet de trouver l'adresse IP locale de votre machine, ce qui est essentiel pour accéder à l'interface web d'ActiveMQ :
```bash
ifconfig
```

Évidemment, si vous travaillez sur linux, la commande est la suivante :
```bash
ip a
```



**Interface web :**

Une fois que vous avez lancé ActiveMQ avec `docker-compose up -d`, trouvé le port et l'adresse ip, vous pouvez accéder à l'interface web d'ActiveMQ depuis votre navigateur via l'URL suivante :

`http://localhost:8161`



**Identifiants de connexion par défaut :**

- **Nom d'utilisateur** : `admin`
- **Mot de passe** : `admin`

<img width="1440" alt="admin" src="https://github.com/user-attachments/assets/8941410e-eb1d-470a-8f84-447b94f5e37d">



