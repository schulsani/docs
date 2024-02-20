---
title: Datenbank
layout: home
parent: Raspberry
nav_order: 3
---
# MySQL Datenbank mit phpMyAdmin installieren und zusätzlichen Nutzer für Node-RED einrichten

## Schritt 1: MySQL und phpMyAdmin installieren

1. Öffnen Sie die Terminalanwendung auf Ihrem System.

2. Installieren Sie MySQL und phpMyAdmin mit den folgenden Befehlen:

```bash

sudo apt update

sudo apt install mysql-server phpmyadmin

```

3. Während der Installation von phpMyAdmin werden Sie nach einem Webserver gefragt. Wählen Sie `apache2` und bestätigen Sie mit der Enter-Taste.

4. Wählen Sie während der Installation von phpMyAdmin "Ja" aus, wenn Sie dazu aufgefordert werden, ein Passwort für den phpMyAdmin-Datenbankadministrator (dbconfig-common) festzulegen.

5. Nach Abschluss der Installation können Sie auf phpMyAdmin über Ihren Webbrowser unter http://localhost/phpmyadmin zugreifen.

## Schritt 2: Einen zusätzlichen Nutzer für Node-RED einrichten

1. Öffnen Sie phpMyAdmin in Ihrem Webbrowser.

2. Melden Sie sich mit den Anmeldeinformationen des Datenbankadministrators an.

3. Klicken Sie auf die Registerkarte "Benutzer" und dann auf "Neuer Benutzer hinzufügen".

4. Geben Sie einen Benutzernamen und ein Passwort für den neuen Benutzer ein. Stellen Sie sicher, dass Sie ein sicheres Passwort verwenden.

5. Unter "Host" wählen Sie "localhost" aus.

6. Klicken Sie auf "Datenbank für Benutzer erstellen und Berechtigungen vergeben" und wählen Sie die gewünschten Datenbankberechtigungen aus. Um Node-RED auf die Datenbank zugreifen zu können, sollten Sie dem Benutzer mindestens SELECT-, INSERT-, UPDATE- und DELETE-Berechtigungen für die entsprechende Datenbank geben.

7. Klicken Sie auf "OK", um den neuen Benutzer zu erstellen.

## Schritt 3: Datenbank "schulsani" einrichten mit den erforderlichen Spalten

1. Klicken Sie auf die Registerkarte "Datenbanken" in phpMyAdmin und dann auf "Neue Datenbank erstellen".

2. Geben Sie "schulsani" als Namen der neuen Datenbank ein und wählen Sie als Kollation "utf8_general_ci" aus.

3. Klicken Sie auf "Erstellen", um die neue Datenbank zu erstellen.

4. Wählen Sie die erstellte Datenbank aus der linken Seitenleiste aus.

5. Klicken Sie auf die Registerkarte "SQL" und fügen Sie den folgenden SQL-Befehl ein, um die erforderlichen Spalten hinzuzufügen:

```sql

CREATE TABLE unfall (

id INT AUTO_INCREMENT PRIMARY KEY,

timestamp TIMESTAMP DEFAULT CURRENT_TIMESTAMP,

type VARCHAR(255),

raum VARCHAR(255)

);

```

6. Klicken Sie auf "OK", um die Tabelle mit den angegebenen Spalten zu erstellen.

Jetzt haben Sie eine MySQL-Datenbank mit dem Namen "schulsani" eingerichtet und einen zusätzlichen Benutzer für Node-RED mit den entsprechenden Berechtigungen erstellt. Die Tabelle "unfall" wurde mit den Spalten "id", "timestamp", "type" und "raum" erstellt.len

