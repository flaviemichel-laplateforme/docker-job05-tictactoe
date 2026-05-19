# PROJET TIC TAC TOE : jeu du morpion - Tic Tac toe - job 05 - Persistance avec les Volumes Docker

## 🎯 Objectif

Héberger un jeu de morpion (Tic Tac Toe) sur un serveur web conteneurisé et utiliser un **Volume Docker** pour rendre l'historique des parties persistant.

---

## Création d'un Dockerfile ( Construction de l'image optimisée )

J'ai rédigé un `Dockerfile` basé sur `php:8.2-apache` en utilisant la commande `COPY --chown` pour optimiser les calques et donner les droits d'écriture en une seule passe.
J'ai ensuite construit l'image :
\`\`\`bash
docker build -t jeu-morpion .
\`\`\`

![Dockerfile](images\Dockerfile.png)

## Construction de l'image

### Erreur lors du build (oublie de sauvegarder le Dockerfile)

![Erreur build](images\docker-build-t-erreur.png)

### Docker build réussi

![build réussi](images\docker-build-reussi.png)

### Docker desktop images jeu-morpion

![Docker desktop images](images\Docker-desktop-jeu-morpion-images.png)

## Création et vérification du volume

J'ai créé le volume persistant `game-results` chargé de stocker le fichier JSON :
\`\`\`bash
docker volume create game-results
docker volume ls
\`\`\`

![docker volume create game-results et docker volume ls](images\creation-volume-et-liste.png)

### Docker desktop - Volumes game-results

![Docker desktop - volumes](images\Docker-desktop-volumes.png)

## Lancement du conteneur en liant le volume

### C'est ici que j'assemble tout : je lance le conteneur (jeu-morpion) sur le port 8080, et on lie notre volume (game-results) au dossier du serveur web (/var/www/html).

![docker run](images\docker-run-id-conteneur.png)

### Conteneur app-morpion sur Docker desktop

![app-morpion](images\Docker-desktop-conteneur-app-morpion.png)

## Ouverture du jeu du morpio Tic Tac Toe sur http://localhost:8080

![jeu morpion](images\tic-tac-toe-8080.png)

## Le terminal qui affiche le tableau JSON avec les résultats des parties.

![results.json](images\terminal-commande-pour-afficher-results.json.png)

## Stopper le conteneur proprement

![docker stop app-morpion](images\docker-stop-app-morpion.png)

### Arrêt de app-morpion dans Docker desktop ( On voit bien que le bouton n'est plus vert )

![docker stop app-morpion - desktop](images\Docker-desktop-stop-app-morpion.png)
