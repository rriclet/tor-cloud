# Installation

Image utilisée pour le service caché Tor : https://github.com/torservers/onionize-docker  

1. Installer docker-compose et lancer la commande 
```
docker-compose up -d
```

2. L'accès à Nextcloud est ensuite disponible à l'adresse fournie par la commande :
```
docker exec app_onionize_1 cat /var/lib/tor/onion_services/app/hostname
```

3. Créer un compte admin
4. Sélectionner MariaDb, renseigner les identifiants présents dans `docker-compose.yaml`

# TODO
Script occ : comptes user, expiration des mots de passe

