FastProfile Backend

FastProfile est une application web moderne qui permet aux utilisateurs de créer et partager une page de présentation personnalisée (bio page) avec photo, description, liens et aperçu en temps réel.
Ce dépôt contient le backend de FastProfile, développé pour être sécurisé, scalable et facile à maintenir.

Table des matières

-  Aperçu du projet

-  Fonctionnalités principales

-  Architecture

-  Technologies utilisées

-  Installation et configuration

-  Exécution du projet

-  Tests

-  Bonnes pratiques

-  Roadmap

-  Licence

1-Aperçu du projet

Le backend de FastProfile fournit une API robuste qui gère :

  -L’authentification et la gestion des utilisateurs.

  -La création et la modification des profils.

  -L’ajout, la mise à jour et la suppression de liens.

  -La génération et le rendu des pages publiques.

  -Le support d’un système de thèmes et l’historique des modifications.

Fonctionnalités principales

  Authentification sécurisée (JWT ou OAuth2).

  CRUD complet pour les profils et liens utilisateurs.

  Gestion des thèmes (clair, sombre, personnalisé).

  Historisation des modifications (logs/versionning).

  API REST documentée et extensible (OpenAPI/Swagger).

  Support temps réel (WebSockets) pour l’aperçu en direct.

Architecture

Le backend suit une architecture modulaire et claire :

fastprofile-backend/
│── app/
│   ├── api/           # Routes et contrôleurs
│   ├── models/        # Modèles de données (User, Link, ProfilePage, Theme, History)
│   ├── services/      # Logique métier
│   ├── db/            # Connexion et ORM
│   ├── core/          # Configurations, sécurité, middlewares
│   └── tests/         # Tests unitaires et d’intégration
│
├── .env.example       # Variables d’environnement
├── requirements.txt   # Dépendances Python
└── main.py            # Point d’entrée de l’application

Technologies utilisées

Langage : Python 3.10+

Framework web : FastAPI (ou Django REST selon choix)

ORM : Tortoise ORM / SQLAlchemy

Base de données : PostgreSQL (recommandé)

Authentification : OAuth2 + JWT

Documentation API : OpenAPI/Swagger auto-générée

Tests : Pytest

Installation et configuration

Cloner le projet

git clone https://github.com/username/fastprofile-backend.git
cd fastprofile-backend


Créer un environnement virtuel

python -m venv venv
source venv/bin/activate   # Linux/Mac
venv\Scripts\activate      # Windows


Installer les dépendances

pip install -r requirements.txt


Configurer les variables d’environnement
Créer un fichier .env en copiant .env.example :

DATABASE_URL=postgresql://user:password@localhost:5432/fastprofile
SECRET_KEY=your-secret-key
ACCESS_TOKEN_EXPIRE_MINUTES=60

Exécution du projet

Démarrer le serveur en local :

uvicorn main:app --reload


Accéder à la documentation API interactive :

http://127.0.0.1:8000/docs

Tests

Lancer les tests unitaires et d’intégration avec pytest :

pytest

Bonnes pratiques

Respecter la convention PEP8.

Ajouter des tests pour toute nouvelle fonctionnalité.

Documenter clairement chaque endpoint.

Ne jamais pousser les fichiers .env dans le dépôt.

Roadmap

 Intégration d’un cache (Redis) pour l’aperçu temps réel.

 Support GraphQL en complément de REST.

 Gestion avancée des rôles et permissions.

 Support multilingue.

 CI/CD avec GitHub Actions.

Licence

Ce projet est distribué sous licence MIT.
Vous êtes libre de l’utiliser, le modifier et le distribuer dans le respect des termes de la licence.
