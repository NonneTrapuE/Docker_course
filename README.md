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


                                    ---------------------               ---------------------       
                                    |    Docker Host    |
                                    |                   |
                                    |                   | 
      -------------------           |                   |
      |  Docker Client  |  ------>  |                   |
      -------------------           |                   | 
                                    |                   |
                                    |                   |
                                    |                   | 
                                    |                   |
                                    |                   |
                                    ---------------------               ---------------------



