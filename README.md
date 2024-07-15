|| [Prerequisites](#prerequisites) ||
[Deployment](#deployment) ||
[Authors](#authors) ||

# jenkins-CICD-spring-boot-app

![alt text](<CICD Jenkins.png>)

Ce projet démontre comment configurer `un pipeline CI/CD` en utilisant Jenkins pour une application `Spring Boot` conteneurisée avec Docker. Nous allons également configurer `SonarCloud` pour l'analyse de la qualité du code et utiliser des `conteneurs MySQL` pour les environnements de staging et de production.

Structure du pipeline:

Récupération du code ==> 
 Construction de l'image Docker ==>
 Analyse de code SonarCloud ==>
 Tests unitaires ==>
 Déploiement en Staging ==>
 Tests d'intégration ==>
 Déploiement en Production ==>
 Surveillance.





## Technologies


- [Docker](https://www.docker.com/get-started)

- [Jenkins](https://www.jenkins.io/download/)

- [Git](https://git-scm.com/downloads)

- [SonarCloud](https://sonarcloud.io/)

- [Maven](https://maven.apache.org/download.cgi)



## Features



- `Checkout` : Récupération du code source depuis le dépôt Git.

- `SonarQube Analysis` : Analyse de la qualité du code avec SonarCloud.

- `Build Docker Images` : Construction des images Docker pour l'application Spring Boot et la base de données MySQL.

- `Test` : Exécution des tests unitaires.

- `Push to DockerHub` : Poussée des images Docker vers DockerHub.

- `Deploy to Staging` : Déploiement des conteneurs sur l'environnement de staging.

- `Deploy to Production` : Déploiement des conteneurs sur l'environnement de production.
## Prerequisites


- Un serveur Jenkins en cours d'exécution.

- Docker installé sur votre serveur Jenkins.

- Un compte GitHub pour stocker votre code d'application Flask.

- avoir un compte sonarcloud 
## Installation



In your command prompt download the repo with the commands:
```bash
  git clone https://github.com/AnselmeG300/jenkins-CICD-spring-boot-app.git

  cd jenkins-CICD-spring-boot-app
  
  code . 
```

    
## Deployment


1. **Créer un `référentiel Git` pour votre application**:

    a - Créez un `nouveau référentiel Git` sur GitHub ou un autre fournisseur d'hébergement de code.

    b - Clonez le référentiel sur votre machine de développement.

    c - Ajoutez vos fichiers de code au référentiel Git et effectuez des commits.


2.  **Configurer Jenkins** :

    a - Accédez à l'interface Web de Jenkins.

    b - Créez un nouveau projet en sélectionnant `Nouveau projet`.

    c - Ajoutez vos identifiants DockerHub dans les Crédits Jenkins.

    d - Ajoutez votre token SonarCloud dans les Crédits Jenkins :
        
        - Configurer SonarCloud : Dans Jenkins, allez dans "Manage Jenkins" > "Configure System" et ajoutez SonarCloud sous "SonarQube Servers".


    e - Donnez un nom à votre projet, par exemple `PayMyBuddy`.

    f - Sélectionnez `Git` comme `système de contrôle de version`.

    g - Saisissez `l'URL du référentiel` Git de votre application.

    f - Définissez les informations d'identification Git si nécessaire.



3. **Créer un pipeline de construction** :

    a - Sélectionnez l'onglet `Pipeline`.

    b - Cliquez sur `Nouveau pipeline`.

    c - Choisissez `Pipeline Scripted`.

    d - Collez le script `Jenkinsfile` de ce dépot git dans l'éditeur de script.



4. **Enregister et exécuter le pipeline** :

    a - Enregistrez le pipeline Jenkins.

    b - Démarrez le pipeline `manuellement` ou configurez un déclencheur pour qu'il s'exécute `automatiquement` chaque fois que vous poussez du code vers le référentiel Git.


A. `Déploiement manuellement` : 
- Accédez à l'interface Web de Jenkins.
- Sélectionnez votre projet Flask.
- Cliquez sur le bouton "Build Now" pour lancer le pipeline manuellement.

B. `Déploiement automatique` : 
- Configurez un webhook dans votre fournisseur d'hébergement de code (GitHub, GitLab, etc.) pour envoyer une notification à Jenkins chaque fois que vous poussez du code vers le référentiel.
- Jenkins déclenchera automatiquement le pipeline lorsqu'il recevra une notification de webhook.

**```Conclusion```**

Vous avez maintenant `un pipeline CI-CD` fonctionnel pour une application `Flask` utilisant `Jenkins et Docker`. Ce pipeline construira votre image Docker, effectuera des tests, ferra le push de l'image sur DockerHub et déploira l'application sur l'environnement de staging ou de production.



Pour plus de détailles consultez la video suivante : [Jenkins-CI-CD-spring-boot-app](https://youtu.be/0R0g8xvpgtM?si=jxs63dXDIZpRINLj)


## Authors

- [@AnselmeG300](https://github.com/AnselmeG300/terraform-cloud.git)


## License

[MIT](https://choosealicense.com/licenses/mit/)


## Badges

Add badges from somewhere like: [shields.io](https://shields.io/)

[![MIT License](https://img.shields.io/badge/License-MIT-green.svg)](https://choosealicense.com/licenses/mit/)
[![GPLv3 License](https://img.shields.io/badge/License-GPL%20v3-yellow.svg)](https://opensource.org/licenses/)
[![AGPL License](https://img.shields.io/badge/license-AGPL-blue.svg)](http://www.gnu.org/licenses/agpl-3.0)
