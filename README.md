# Docker_course
Course on Docker


## Initiation de Docker

### Architecture générale de Docker

Docker est composé de : 
- Docker Engine
- Docker Client
- Image
- Conteneur
- Librairie d'Images

### Docker Engine

Il s'occupe de :
- Exécution des conteneurs
- Isolation
- Gestion des ressources

### Docker Client

Le client s'occupe uniquement de réaliser des actions sur le Docker Engine.
Il peut être installé sur la même machine ou sur une machine distante

### Images

Les images sont des modèles d'applications fournis par les éditeurs et/où la communauté.
Elles sont en lectures seules et peuvent être stockées localement ou sur des registries. (par défaut: hub.docker.com)

### Conteneur

Espace d'exécution isolé. Il contient tout pour exécuter l'application (binaire et dépendances)

### Registres

Les registres servent à stocker des images de façon locale ou à distance
Les images peuvent être disponibles publiquement ou de façon privées

### Fonctionnement


                                    ---------------------               ----------------------       
                                    |    Docker Host    |               |  Docker Registry   |
                                    |                   |               |                    |
                                    |   -------------   |               |    -----------     |
      -------------------           |  |Docker Engine|  |               |   |  Image 1  |    |
      |  Docker Client  |  ------>  |   -------------   |  -------->    |    -----------     |
      -------------------           |   -------------   |  <--------    |    -----------     |
                                    |  | Conteneur 1 |  |               |   |  Image 2  |    |
                                    |   -------------   |               |    -----------     |
                                    |   -------------   |               |    -----------     |
                                    |  | Conteneur 2 |  |               |   |  Image 3  |    |
                                    |   -------------   |               |    -----------     |
                                    ---------------------               ----------------------


## Utiliser Docker

### Exploiter les images Docker

#### Afficher les images présentes sur la machine :

```$> docker images```

#### Rechercher les images sur le registry de Docker

```$> docker search nom_image```

ex: ```$> docker search nginx```

#### Télécharger une image Docker

```$> docker pull nom_image ```

ex: ```$> docker pull nginx```

#### ⚠️ Si aucun tag n'est précisé, l'image prend le tag par défaut : *latest* 

ex : ```nginx:latest```

#### Supprimer une image de Docker

```$> docker rmi image_name:tag```

exemple: ```$> docker rmi nginx:latest```

⚠️ Si une image ne veut pas se supprimer, il y a possiblement conflit avec un container. En effet, une image ne peut être supprimée si elle est utilisée par un container, même si celui-ci n'est pas en fonctionnement.  Il faut obligatoirement forcer sa suppression.

```$> docker rmi -f image_name:latest``` 

#### Lister les containers

```$> docker ps```

ou 

```$> docker ps -a``` 

Pour afficher tous les containers, y compris ceux qui ne sont pas en fonctionnement.  
