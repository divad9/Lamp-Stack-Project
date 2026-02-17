# LAMP Stack Project Documentation

## Project Overview

This project demonstrates the deployment of a **LAMP stack** — a widely-used open-source web development environment consisting of:

| Component | Role |
|-----------|------|
| **L**inux | Operating System |
| **A**pache | Web Server |
| **M**ySQL | Database Management |
| **P**HP | Server-side Scripting |

The goal of this project was to set up a fully functional LAMP stack on a Linux server and serve a dynamic PHP web page, confirming that all components are correctly installed and communicating with each other.

---

## Screenshots

### PHP Info Page (Browser)
> _Replace with your screenshot of the PHP page in the browser_

![PHP Info Page](screenshots/PHP-final.jpg)

---

### Terminal — Final Command Output
> _Replace with your screenshot of the bash terminal showing the last line of code_

![Terminal Output](screenshots/fc.jpg)

---

## Code Snippets

### 1. PHP Test Page (`/var/www/html/index.php`)

This file was created to confirm PHP is working correctly with Apache:

```php
<?php
phpinfo();
?>
```

---

### 2. Apache Virtual Host Configuration (`/etc/apache2/sites-available/000-default.conf`)

```apache
<VirtualHost *:80>
    ServerAdmin webmaster@localhost
    DocumentRoot /var/www/html

    ErrorLog ${APACHE_LOG_DIR}/error.log
    CustomLog ${APACHE_LOG_DIR}/access.log combined
</VirtualHost>
```

---

### 3. Key Bash Commands Used

```bash
# Update package index
sudo apt update

# Install Apache
sudo apt install apache2 -y

# Install MySQL
sudo apt install mysql-server -y

# Install PHP and required modules
sudo apt install php libapache2-mod-php php-mysql -y

# Restart Apache to apply changes
sudo systemctl restart apache2

# Create PHP test file
echo "<?php phpinfo(); ?>" | sudo tee /var/www/html/index.php
```

---

## How to Verify the Stack is Running

1. Open a browser and navigate to `http://your-server-ip/index.php`
2. You should see the **PHP Info** page confirming PHP is active and loaded by Apache
3. Confirm MySQL is running with: `sudo systemctl status mysql`

---

## Author

> David Babayo

---

*Project submitted as part of a LAMP Stack deployment exercise.*
