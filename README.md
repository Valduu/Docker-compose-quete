# QUETE Docker Compose Wordpress 

## Structure du projet

wordpress/ <br>
├── compose.yml <br>
├── .env <br>
├── secret/ <br>
│ ├── mysql_password.txt <br>
│ ├── mysql_root_password.txt <br>
│ ├── wordpress_db_password.txt <br>
└── README.md <br>

## Variables d'environnement

Le fichier `.env` contient les variables d'environnement utilisées par Docker Compose.

- `MYSQL_DATABASE`: Nom de la base de données MySQL.
- `MYSQL_USER`: Nom d'utilisateur pour MySQL.
- `WORDPRESS_DB_NAME`: Nom de la base de données utilisée par WordPress.
- `MYSQL_ROOT_PASSWORD_FILE`: Chemin vers le fichier contenant le mot de passe root de MySQL (utilisé avec Docker Secrets).
- `MYSQL_PASSWORD_FILE`: Chemin vers le fichier contenant le mot de passe utilisateur de MySQL (utilisé avec Docker Secrets).
- `WORDPRESS_DB_PASSWORD_FILE`: Chemin vers le fichier contenant le mot de passe de la base de données WordPress (utilisé avec Docker Secrets).

## Secrets

Les valeurs sensibles sont stockées dans des fichiers dans le dossier `secrets/` et sont référencées par Docker Secrets.

- `secrets/mysql_root_password.txt`: Contient le mot de passe root de MySQL.
- `secrets/mysql_password.txt`: Contient le mot de passe utilisateur de MySQL.
- `secrets/wordpress_db_password.txt`: Contient le mot de passe de la base de données WordPress.

## Commandes

Pour lancer les services, utilisez la commande suivante :

```sh
docker-compose up -d
```

Pour arrêter les services, utilisez la commande suivante :

```sh
docker-compose down
```

### 6. Dockerfiles (optionnel)

Si des personnalisations spécifiques sont nécessaires pour les images `wordpress` ou `mysql`, ajoute des Dockerfiles dans les répertoires `wordpress/` et `db/` respectivement. Sinon, tu peux les ignorer et utiliser directement les images officielles.

Avec cette configuration, l'application WordPress est mieux structurée, les variables d'environnement sont séparées, et les secrets sont gérés de manière sécurisée avec Docker Secrets.
