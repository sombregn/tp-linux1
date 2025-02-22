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
-**cd nom creer**
- **Par exemple: cd vagrant-linux**
- 
 ### 2. Setup du VagrantFile 
 Ajouter le fichier Vagrantfile
- **cmd> vagrant init**
- **Un file vagrant vous sera initialisé automatiquement dans ce file vous travailler.**
- 
### 3. Validation du Vagrant file
-**cmd> vagrant validate**

### 4. Démarrage du Vagrant File:
-**cmd> vagrant up**

###📌 Ce que fait cette commande :
- **Télécharge l’image Ubuntu 20.04 si elle n’existe pas encore.**
**Crée et configure la VM.**
**Installe Nginx et MySQL automatiquement.**
**Configure Nginx pour servir notre application Angular.**
**Configure MySQL pour accepter des connexions depuis l’extérieur**

### 🎯 Vérifications après l’installation
**🔗 1. Se connecter à la VM via SSH**
**cmd> vagrant ssh**
**🔥 2. Tester Nginx**
**Ouvrez un navigateur et entrez** 
**http://localhost:8089** n'oublions pas le nom de notre port 
**🗄 3. Accéder à MySQL**
**mysql -u root -p -h 127.0.0.1 -P 3306**

**📌 Conclusion**
**✅ Nous avez maintenant une machine virtuelle sous Ubuntu 20.04 avec Nginx et MySQL configurés**
**✅ Notre application Angular est servie via Nginx**
**✅ MySQL est accessible depuis l’extérieur sur le port 3306**
**✅ Vous pouvez gérer votre serveur avec Vagrant facilement**
**📝 Remarque**
**voir toutes captures dans le dossier captures**
![Capture d'écran 2025-02-20 234638](https://github.com/user-attachments/assets/bd5be247-a8e6-4dc5-95df-076be37b3c47)
![listofDB](https://github.com/user-attachments/assets/c212cfb9-2820-408c-866e-969fc8c17c2f)
![IHM2](https://github.com/user-attachments/assets/65c47be6-7000-484b-ad8d-a6d0ce26892e)
![IHM](https://github.com/user-attachments/assets/c450aa7e-f2b4-4629-8559-783d25e8c97a)
![Capture d'écran 2025-02-20 234946](https://github.com/user-attachments/assets/7b3c8848-ab14-4058-a08d-3e35c1222e13)

