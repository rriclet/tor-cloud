# Introduction 

Ce projet a but pour d'être installé sur un Raspberry Pi.

Tutoriel d'installation de Raspbian Lite OS et activation de SSH :
https://www.instructables.com/Install-and-Setup-Raspbian-Lite-on-Raspberry-Pi-3/

- Installez `git`, `docker` ainsi que `docker-compose` sur votre Raspberry.
- Ajoutez un stockage via USB à votre Raspberry (clé USB, disque dur externe...)

# Installation du projet

1. Faites un `git clone` de ce projet dans un dossier de votre Raspberry (par exemple dans `/media/foo/`) 

2. Modifier la variable d'environement `ONIONSERVICE_NAME` par le nom de votre groupe d'ami.e.s dans le fichier `docker-compose.yaml`.

3. Installer docker-compose et lancer la commande dans le dossier où se trouve le ficher `docker-compose.yaml` 
```
docker-compose up -d
```

4. Le nom de domaine pour accéder à Nextcloud est ensuite disponible à l'adresse fournie par la commande suivante :
```
docker exec app_onionize_1 cat /var/lib/tor/onion_services/app/hostname
```

5. Créer un compte admin

6. Sélectionner MariaDb, renseigner les identifiants présents dans `docker-compose.yaml` (l'hôte à renseigner est `db`, comme le nom du service)

# Fonctionnalités basiques

https://docs.nextcloud.com/server/19/admin_manual/configuration_files/encryption_configuration.html

https://www.techrepublic.com/article/how-to-create-a-group-calendar-in-nextcloud/

Image utilisée pour le service caché Tor : https://github.com/torservers/onionize-docker  
(l'architecture `armhf` n'est pas disponible sur Docker Hub, c'est pourquoi j'ai créé manuellement l'image utilisée dans le `docker-compose.yaml`) 
