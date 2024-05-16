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

- `MYSQL_ROOT_PASSWORD`: Chemin vers le fichier contenant le mot de passe root de MySQL (utilisé avec Docker Secrets).
- `MYSQL_PASSWORD`: Chemin vers le fichier contenant le mot de passe utilisateur de MySQL (utilisé avec Docker Secrets).
- `WORDPRESS_DB_PASSWORD`: Chemin vers le fichier contenant le mot de passe de la base de données WordPress (utilisé avec Docker Secrets).

Dans les bonnes pratiques, les variables suivantes devrait être placé dans le fichier `.env`

- `MYSQL_DATABASE`: Nom de la base de données MySQL.
- `MYSQL_USER`: Nom d'utilisateur pour MySQL.
- `WORDPRESS_DB_NAME`: Nom de la base de données utilisée par WordPress.

## Secrets

Docker Compose vous permet d'utiliser des secrets sans avoir à utiliser de variables d'environnement pour stocker des informations.
Les données secrètes sont stockées dans des fichiers dans le dossier `secret/` et sont référencées par Docker Secrets.

- `secret/mysql_password.txt`: Contient le mot de passe utilisateur de MySQL.
- `secret/mysql_root_password.txt`: Contient le mot de passe root de MySQL.
- `secret/wordpress_db_password.txt`: Contient le mot de passe de la base de données WordPress.

## Commandes

Pour lancer l'application, utilisez la commande suivante :

```sh
docker-compose up -d
```

