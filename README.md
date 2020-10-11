# Installation de Jenkins

## Informations utiles
Jenkins est un outil open source d'intégration continue, fork de l'outil Hudson après les différends entre son auteur, Kohsuke Kawaguchi, et Oracle. Écrit en Java, Jenkins fonctionne dans un conteneur de servlets tel qu’Apache Tomcat, ou en mode autonome avec son propre serveur Web embarqué.

### Il est recommandé d'installer Java avant d'installer Jenkins

```
sudo apt-get install default-jdk
```
### Récupération de la clé
```
wget -q -O - https://pkg.jenkins.io/debian-stable/jenkins.io.key | sudo apt-key add –
```

### Ajout du répository Jenkins dans le système
```
sudo sh -c 'echo deb http://pkg.jenkins.io/debian-stable binary/ > /etc/apt/sources.list.d/jenkins.list'
```

### Mettre à jour la base de données des paquets
```
sudo apt update
```

### Installation de Jekins
```
sudo apt install jenkins -y
```

### Démarrage du service Jenkins
```
sudo systemctl start jenkins
```

### Etat du service Jenkins
```
sudo systemctl status jenkins
```
Résultat
```
jenkins.service - LSB: Start Jenkins at boot time
     Loaded: loaded (/etc/init.d/jenkins; generated)
     Active: active (exited) since Sun 2020-10-11 14:55:36 UTC; 4min 26s ago
       Docs: man:systemd-sysv-generator(8)
      Tasks: 0 (limit: 1164)
     Memory: 0B
     CGroup: /system.slice/jenkins.service
```

### Voir le mot de passe initial
```
sudo cat /var/lib/jenkins/secrets/initialAdminPassword
```


## Remarque
* Si tout est bien passé, vous n'avez qu'à ouvrir votre navigateur avec le port 8080
* Si vous l'avez installé en local, utilisez cette adresse 127.0.0.1:8080
* Si vous l'avez installé dans une machine virtuelle, utilisez l'adresse publique avec le port ci-dessus
** N'oubliez pas le groupe de sécurité si vous utilisez une machine virtuelle dans le cloud (exemple AWS : Security group)


