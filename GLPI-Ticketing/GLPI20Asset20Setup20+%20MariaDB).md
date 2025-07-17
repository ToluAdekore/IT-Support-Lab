
# 📦 GLPI IT Asset Management Setup (Apache + MariaDB)

This guide outlines the setup of **GLPI (Gestionnaire Libre de Parc Informatique)** — an open-source IT asset management and helpdesk platform — on **Ubuntu 24.04.2 LTS** using **Apache**, **MariaDB**, and **PHP 8.2+**.

---

## 🧱 Stack

- OS: Ubuntu Server 24.04.2 LTS
- Web server: Apache2
- Database: MariaDB 10.x
- PHP: v8.2
- GLPI: v10.x

---

## ⚙️ Step-by-Step Installation

### 1. 🛠️ Update System

```bash
sudo apt update && sudo apt upgrade -y
```

---

### 2. 🌐 Install Apache

```bash
sudo apt install apache2 -y
sudo systemctl enable apache2
sudo systemctl start apache2
```

---

### 3. 🐬 Install MariaDB

```bash
sudo apt install mariadb-server -y
sudo mysql_secure_installation
```

**Create GLPI database:**

```sql
sudo mysql -u root -p

CREATE DATABASE glpidb;
CREATE USER 'glpiuser'@'localhost' IDENTIFIED BY 'securepassword';
GRANT ALL PRIVILEGES ON glpidb.* TO 'glpiuser'@'localhost';
FLUSH PRIVILEGES;
EXIT;
```

---

### 4. 🐘 Install PHP + Extensions

```bash
sudo apt install php php-mysql php-curl php-intl php-gd php-imap php-xmlrpc php-ldap php-apcu php-xml php-mbstring php-bz2 php-zip libapache2-mod-php -y
```

✅ Verify PHP version:
```bash
php -v
```

---

### 5. 📦 Download & Extract GLPI

```bash
cd /tmp
wget https://github.com/glpi-project/glpi/releases/download/10.0.14/glpi-10.0.14.tgz
tar -xvzf glpi-10.0.14.tgz
sudo mv glpi /var/www/html/
```

---

### 6. 🔒 Set Permissions

```bash
sudo chown -R www-data:www-data /var/www/html/glpi
sudo chmod -R 755 /var/www/html/glpi
```

---

### 7. 🌍 Configure Apache

Create a GLPI virtual host:

```bash
sudo nano /etc/apache2/sites-available/glpi.conf
```

Paste this:

```
<VirtualHost *:80>
    ServerAdmin admin@example.com
    DocumentRoot /var/www/html/glpi
    ServerName yourserver.local

    <Directory /var/www/html/glpi>
        AllowOverride All
    </Directory>

    ErrorLog ${APACHE_LOG_DIR}/glpi_error.log
    CustomLog ${APACHE_LOG_DIR}/glpi_access.log combined
</VirtualHost>
```

Then:

```bash
sudo a2ensite glpi.conf
sudo a2enmod rewrite
sudo systemctl reload apache2
```

---

### 8. 🌐 Complete Web Installer

Visit:  
```
http://<your-server-ip>/glpi
```

Then follow the web wizard:
- Choose language  
- Accept license  
- Select **Install**  
- Enter MariaDB credentials:
  - DB: `glpidb`
  - User: `glpiuser`
  - Pass: `securepassword`  
- Finish installation  
- Remove `/install` folder when prompted

---

### 9. 🔐 Default Logins

| Role | Username | Password |
|------|----------|----------|
| Super-Admin | glpi | glpi |
| Technician | tech | tech |
| Normal User | normal | normal |

Change passwords immediately after logging in.

---

## 🧪 Post-Setup Config (Optional)

- ✅ Enable email notifications  
- ✅ Create users and assign profiles  
- ✅ Define categories, entities, and SLA  
- ✅ Install FusionInventory for agent-based inventory collection  
- ✅ Enable automatic backups and snapshotting

---

## 📸 Screenshots

| Web Installer | Dashboard | Tickets |
|---------------|-----------|---------|
| ![](../Screenshots/installer.png) | ![](../Screenshots/dashboard.png) | ![](../Screenshots/tickets.png) |

---

## ✅ Outcome

GLPI is now deployed and configured on your Ubuntu server, ready to manage IT assets, users, support tickets, and more.

> This forms the backend for your helpdesk simulation lab documented in `GLPI-Ticketing`.
