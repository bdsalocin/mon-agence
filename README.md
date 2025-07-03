lien trello : https://trello.com/invite/b/686631a63f7d4332d5e6c8c1/ATTIc4b0551a236a58b8b48712bbd35747741EB618B3/projet-docker-compose-mon-agence-🐳

# Mon Agence

## Description

Projet Docker Compose “Mon Agence” comprenant :

- Un frontend statique servi par Apache (httpd)
- Un backend simple basé sur Alpine Linux
- Une base de données MySQL 8.0
- Une interface phpMyAdmin pour gérer la base MySQL

## Structure du projet

```
mon-agence/
├── backend/
│   ├── app.sh
│   └── Dockerfile
├── frontend/
│   ├── Dockerfile
│   ├── index.html
│   └── style.css
├── docker-compose.yml
└── README.md
```

## Prérequis

- Docker installé
- Docker Compose installé

## Instructions pour lancer le projet

1. Cloner le dépôt :

```bash
git clone <URL_DU_DEPOT>
cd mon-agence
```

2. Construire et lancer les conteneurs :

```bash
docker compose up --build
```

3. Accéder au frontend dans votre navigateur à l'adresse :  
   [http://localhost:8080](http://localhost:8080)

4. Accéder à phpMyAdmin pour gérer la base de données :  
   [http://localhost:8081](http://localhost:8081)

   - Serveur : `database`
   - Utilisateur : `user`
   - Mot de passe : `password`

## Services dans docker-compose.yml

- **frontend** : serveur Apache servant `index.html`
- **backend** : conteneur Alpine avec script `app.sh` (exécution simple)
- **database** : base MySQL 8.0 avec utilisateur et mot de passe configurés
- **phpmyadmin** : interface graphique pour MySQL exposée sur le port 8081

## Commandes utiles

- Lister les conteneurs en cours :

```bash
docker ps
```

- Voir les logs d'un conteneur :

```bash
docker logs <nom_du_conteneur>
```

- Arrêter tous les conteneurs :

```bash
docker compose down
```

## Contribution

N’oubliez pas de travailler sur des branches spécifiques pour vos modifications :

```bash
git checkout -b ma-branche
```

Committez vos changements :

```bash
git add .
git commit -m "Description des changements"
git push origin ma-branche
```

Faites une Pull Request pour fusionner dans la branche principale.

## Remarques

- Pour éviter l’erreur Apache sur le nom de serveur, vous pouvez configurer `ServerName` dans le Dockerfile du frontend si besoin.
- La base de données est initialisée automatiquement avec les paramètres du docker-compose.yml.
- phpMyAdmin est configuré pour se connecter au service `database`.

---

Merci d’utiliser ce projet “Mon Agence” !  
N’hésitez pas à me contacter pour toute question.
