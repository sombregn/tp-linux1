# Nom et Prenom: BAH Alpha Souleymane
# 🚀 Linux, Vagrant, Nginx

Ce projet vise a mettre en place un env linux provisioner depuis vagrant via des conn ssh.
1. Intaller nginx sur votre système ubuntu
2. Puis déployer une mini application front
3. Ajouter le port forwading pour mysql 3306 pour guest et 3306 pour host 
3. mysql server sur le même serveur
4. Connecter vous sur le serveur mysql à partir de la machine via ssh

---


## 🎯 Objectif
L'objectif de ce projet est de créer une VM via vagrant et installer un serveur ubuntu.

---

## 📦 Prérequis
Avant de commencer, assurez-vous d'avoir les éléments suivants installés sur votre machine :

- **VirtualBox** (Pour la VM) ou tout autres ... 
- **Vagrant** (Pour la gestion de la VM)
- **Git Bash** (Pour exécuter les commandes plus facilement sous Windows) ou autres **PowerShell** etc

---


### 1. Créer un dossier de travail
- **mkdir le nom que vous  voulez**
- **Par exemple: mkdir vagrant-linux**
- **cd nom creer**
- **Par exemple: cd vagrant-linux**
 
 ### 2. Setup du VagrantFile 
 Ajouter le fichier Vagrantfile
- **cmd> vagrant init**
- **Un file vagrant vous sera initialisé automatiquement dans ce file vous travailler.**

### 3. Validation du Vagrant file
- **cmd> vagrant validate**

### 4. Démarrage du Vagrant File:
- **cmd> vagrant up**

### 📌 Ce que fait cette commande :
- **Télécharge l’image Ubuntu 20.04 ou selon la version précisé si elle n’existe pas encore.**
- **Crées et configures les VMs.**

### 🎯 Vérifications après l’installation
**-🔗 1. Se connecter à la VM via SSH**
- **cmd> vagrant ssh web & db**
- **🔥 2. Tester le tomcat**
- **Ouvrez un navigateur et entrez** 
- **http://localhost:...** 
- **N'oublions pas le nom de notre port** 
- **🗄 3. Accéder à MySQL**
- **mysql -u root -p -h 127.0.0.1 -P 3306**
Pour voir les tables et les insertions.

### 📌 Conclusion**
- **✅ Nous avez maintenant des machines virtuelles sous Ubuntu 20.04 avec Tomcat , MySQL, Maven, Java configurés**
- **📝 Remarque**
- **Voir toutes captures dans le dossier captures**
![Capture d’écran 2025-02-25 100418](https://github.com/user-attachments/assets/dc826652-8bd3-49f1-be8b-e4a026a62287)
![image-02 2025-02-18 161856](https://github.com/user-attachments/assets/7c839aef-5af1-440f-8d8f-4b4ca751b8af)
