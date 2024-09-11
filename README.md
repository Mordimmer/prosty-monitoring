# Projekt na przedmiot "POS"

Celem programu jest utworzenie prostego systemu monitorowania systemów, napisany w co najmniej dwóch językach. 

[Demo](https://pos.mycka.net/)

## Serwer
Napisany w nodejs

### Zależności
```bash
sudo apt-get update
sudo apt-get install nodejs npm apache2 mariadb-server php php-mysqli libapache2-mod-php
npm install express mysql2 body-parser
```
### Baza danych

```mysql
CREATE DATABASE monitoring;
CREATE USER 'monitoring_user'@'localhost' IDENTIFIED BY 'password';
GRANT ALL PRIVILEGES ON monitoring.* TO 'monitoring_user'@'localhost';
FLUSH PRIVILEGES;
```

### Uruchomienie
```bash
node server.js
```

## Klient
Napisany w pythonie

### Dodanie klienta z poziomu serwera
Trzeba pamiętać o dodaniu klucza ssh na klienta. 
```bash
./add_client.sh hostname ip
```

### Zależności
```bash
sudo apt-get update
sudo apt-get install python3-full python3-pip
pip install schedule --break-system-packages
```

### Uruchomienie ręczne
```bash
python3 client.py
```
