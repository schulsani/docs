---
title: Node Red
layout: home
parent: Raspberry
grand_parent: Setup
nav_order: 6
---


## Installation von Node-RED auf einem Raspberry Pi

1. **Voraussetzungen:**
   - Raspberry Pi mit Raspbian OS (oder einem ähnlichen Betriebssystem) im Netzwerk verbunden.
   - Zugriff auf die Befehlszeile des Raspberry Pi (entweder über SSH oder direkt).

2. **Öffnen Sie das Terminal:**
   Öffnen Sie ein Terminalfenster auf Ihrem Raspberry Pi oder verbinden Sie sich über SSH.

3. **Aktualisieren Sie Ihr System:**
   Führen Sie die folgenden Befehle aus, um sicherzustellen, dass Ihr System auf dem neuesten Stand ist:

   ```bash
   sudo apt update
   sudo apt upgrade
   ```

4. **Installieren Sie Node.js und npm:**
   Node-RED benötigt Node.js und npm. Installieren Sie diese mit dem folgenden Befehl:

   ```bash
   sudo apt install -y nodejs npm
   ```

5. **Installieren von Node-RED:**
   Verwenden Sie npm, um Node-RED global zu installieren:

   ```bash
   sudo npm install -g --unsafe-perm node-red
   ```

6. **Starten Sie Node-RED:**
   Nachdem die Installation abgeschlossen ist, starten Sie Node-RED mit dem Befehl:

   ```bash
   node-red
   ```

7. **Zugriff auf Node-RED Dashboard:**
   Öffnen Sie einen Webbrowser und navigieren Sie zu `http://<raspberry-pi-ip>:1880`, um auf die Node-RED-Oberfläche zuzugreifen.

## Importieren eines Flows von GitHub

1. **Flow-Datei herunterladen:**
   Gehen Sie zu https://github.com/schulsani/server/blob/main/nodered/flows.json und klicken Sie auf den "Raw"-Button, um die Rohdatei des Flows anzuzeigen. Speichern Sie die Datei auf Ihrem Computer.

2. **Importieren Sie den Flow in Node-RED:**
   - Klicken Sie in der Node-RED-Oberfläche auf das Menüsymbol (oben rechts).
   - Wählen Sie "Import" > "Clipboard".
   - Öffnen Sie die heruntergeladene `flows.json`-Datei und fügen Sie den Inhalt in das Textfeld ein.
   - Klicken Sie auf "Import".

Nachdem Sie den Flow importiert haben, sollten die MQTT- und MySQL-Nodes bereits enthalten sein.

## Verbindung mit MQTT- und MySQL-Server

1. **MQTT-Server verbinden:**
   - Öffnen Sie den MQTT-Node in der Arbeitsfläche.
   - Konfigurieren Sie die MQTT-Einstellungen im Node entsprechend den zuvor generierten Anmeldeinformationen für den MQTT-Server.

2. **MySQL-Server verbinden:**
   - Öffnen Sie den MySQL-Node in der Arbeitsfläche.
   - Konfigurieren Sie die MySQL-Einstellungen im Node mit den Anmeldeinformationen für den MySQL-Server.

3. **Deploy:**
   Klicken Sie auf "Deploy", um die Änderungen zu übernehmen und den Flow auszuführen.

