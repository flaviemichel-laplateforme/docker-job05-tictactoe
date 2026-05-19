# PROJET TIC TAC TOE : jeu du morpion

## Création d'un Dockerfile

![Dockerfile](images\Dockerfile.png)

## Construction de l'image

### Erreur lors du build (oublie de sauvegarder le Dockerfile)

![Erreur build](images\docker-build-t-erreur.png)

### Docker build réussi

![build réussi](images\docker-build-reussi.png)

### Docker desktop images jeu-morpion

![Docker desktop images](images\Docker-desktop-jeu-morpion-images.png)

## Création du volume

### Je crée un espace de stockage physique géré par Docker qui survivra à la suppression du conteneur et je vérifie que le volume existe bien .

![docker volume create game-results et docker volume ls](images\creation-volume-et-liste.png)

### Docker desktop - Volumes game-results

![Docker desktop - volumes](images\Docker-desktop-volumes.png)

## Lancement du conteneur en liant le volume

### C'est ici que j'assemble tout : je lance le conteneur (jeu-morpion) sur le port 8080, et on lie notre volume (game-results) au dossier du serveur web (/var/www/html).

![docker run](images\docker-run-id-conteneur.png)
