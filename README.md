# DockerProject

## Présentation du projet
En-dehors de notre alternance, nous souhaitons développer une application Web pour un projet professionnel. Nous sommes aux prémices du projet et nous avons décidé de se servir de cette application Web pour notre TP de devops.  
## Architecture du projet  
L’application est une application Web classique, nous utilisons :  - Un Front - Une API - Une Base de données (pas pour le TP)  
### Le front  
Technologie utilisée : React  
### L’API  
Technologie utilisée : Express  
### La Base de données
Pour le TP la BDD sera uniquement un tableau dans le front  
## Fonctionnement souhaité CI/CD
Sur notre Github nous avons :  
- Une branche main 
- Une branche develop  

Notre CI-CD sur le front et le back effectue les actions suivantes :
- Lors d’un push sur la main et la develop :
    - Récupère le code de notre repositorie
    - Configure Buildx
    - Connexion au registre de conteneurs GitHub
    - Construction et publication de l'image Docker (avec le tag qui change selon le push main ou develop ex: event-wishes-back:develop-latest)
- Lors d'un push sur une autre branche que la main ou la develop :
    - Récupère le code de notre repositorie
    - Configure Buildx
    - Connexion au registre de conteneurs GitHub
    - Construction de l'image Docker

## Portainer
On indique à notre portainer le chemin vers notre repository dockerProject qui contient notre docker_compose qui récupère les images build du front et du back.

Pour que portainer puisse pull nos images on créé un registre qui pointe vers notre registery github pour ensuite déclarer nos 2 images dans portainer.
