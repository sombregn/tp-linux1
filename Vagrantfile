Vagrant.configure("2") do |config|

  config.vm.define "server" do |webserver|

    webserver.vm.box = "ubuntu/focal64"  # Ubuntu 20.04
    webserver.vm.box_check_update = false
    webserver.vm.boot_timeout = 800

    # Forwarder les ports pour Nginx et MySQL
    webserver.vm.network "forwarded_port", guest: 80, host: 9190   # Nginx
    webserver.vm.network "forwarded_port", guest: 3306, host: 9090  # MySQL

    # Réseau privé avec IP statique
    webserver.vm.network "private_network", type: "static", ip: "192.168.0.10"

    # Synchronisation du dossier Angular
    webserver.vm.synced_folder "./angular-signals-app-v01/dist/angular-signals-app/browser", "/home/vagrant/angular-app"

    webserver.vm.provider "virtualbox" do |vb|
      vb.gui = false
      vb.name = "tplinux1"
      vb.memory = "1024"
      vb.cpus = 1
    end

    # Provision pour installer Nginx et MySQL
    webserver.vm.provision "shell", inline: <<-SHELL
  sudo apt-get update
  sudo apt-get -f install -y

  # Installer Nginx
  sudo apt-get install -y nginx
  sudo systemctl start nginx  

  # Configurer Nginx pour servir Angular
  cat <<EOF | sudo tee /etc/nginx/sites-available/angular-app
server {
    listen 80;
    server_name localhost;
    root /home/vagrant/angular-app;
    index index.html;
    location / {
        try_files \$uri /index.html;
    }
}
EOF

  sudo ln -s /etc/nginx/sites-available/angular-app /etc/nginx/sites-enabled/
  sudo systemctl restart nginx

  # Installer MySQL avec un mot de passe root prédéfini
  echo "mysql-server mysql-server/root_password password password" | sudo debconf-set-selections
  echo "mysql-server mysql-server/root_password_again password password" | sudo debconf-set-selections
  sudo apt-get install -y mysql-server
  sudo systemctl start mysql

  # Configurer MySQL pour accepter les connexions distantes
  sudo sed -i "s/bind-address.*/bind-address = 0.0.0.0/" /etc/mysql/mysql.conf.d/mysqld.cnf
  sudo systemctl restart mysql

  # Créer un utilisateur root accessible depuis l'extérieur
  sudo mysql -e "CREATE USER 'root'@'%' IDENTIFIED BY 'password';"
  sudo mysql -e "GRANT ALL PRIVILEGES ON *.* TO 'root'@'%' WITH GRANT OPTION;"
  sudo mysql -e "FLUSH PRIVILEGES;"
SHELL


  end
end
