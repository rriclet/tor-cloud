[Français](https://github.com/rriclet/tor-cloud/blob/master/README.fr.md) 👈

# Introduction 

This project is meant to be installed on a Raspberry Pi.

Raspbian Lite OS installation tutorial & SSH activation :
https://www.instructables.com/Install-and-Setup-Raspbian-Lite-on-Raspberry-Pi-3/

- Install `git`, `docker` as well as `docker-compose` on your Raspberry.
- Add an external USB storage to your Raspberry (USB flash drive, external hard drive...)

# Prject installation

1. `git clone` this project in a folder on your Raspberry (for example in `/media/foo/`) 

2. Edit the `ONIONSERVICE_NAME` environment variable with the name of your team in the file `docker-compose.yaml`.

3. Run this command in the folder where the `docker-compose.yaml` file is located 
```
docker-compose up -d
```

4. The .onion domain name to access Nextcloud is given by this command :
```
docker exec app_onionize_1 cat /var/lib/tor/onion_services/app/hostname
```

5. Go to the Nextcloud webpage and create an admin account 

6. Select MariaDb, fill the form with credentials found in `docker-compose.yaml` (the databse host is `db`, the Docker service name)

# Basic functionalities

https://docs.nextcloud.com/server/19/admin_manual/configuration_files/encryption_configuration.html

https://www.techrepublic.com/article/how-to-create-a-group-calendar-in-nextcloud/

Image used for the Tor hidden service : https://github.com/torservers/onionize-docker  
(the `armhf` architecture is not available on Docker Hub, that's why I manually created the image used in `docker-compose.yaml`) 
