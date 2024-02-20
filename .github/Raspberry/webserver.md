---
title: Webserver
layout: home
parent: Raspberry
 
nav_order: 2
---
# Installation von Apache2 und Kopieren von Inhalten aus GitHub

## Apache2 Installation

1. Öffnen Sie die Terminalanwendung auf Ihrem System.

2. Geben Sie den folgenden Befehl ein, um Apache2 zu installieren:

```

sudo apt-get update

sudo apt-get install apache2

```

3. Warten Sie, bis die Installation abgeschlossen ist. Apache2 sollte nun erfolgreich auf Ihrem System installiert sein.

## Kopieren von Inhalten aus GitHub

1. Öffnen Sie erneut das Terminal.

2. Navigieren Sie zum Verzeichnis, in das Sie den Inhalt von GitHub herunterladen möchten. Verwenden Sie dazu den Befehl `cd`, um das gewünschte Verzeichnis zu erreichen.

3. Klonen Sie das GitHub-Repository mit dem folgenden Befehl:

```

git clone https://github.com/schulsani/Server

```

4. Wechseln Sie in das Apache HTML-Verzeichnis. Standardmäßig befindet sich dieses unter `/var/www/html`. Verwenden Sie den Befehl `cd`, um dorthin zu navigieren.

5. Kopieren Sie den Inhalt des Apache-Ordners aus dem geklonten Repository in das HTML-Verzeichnis mit dem Befehl `cp`:

```

cp -r Server/Apache/* /var/www/html/

```

6. Überprüfen Sie anschließend, ob die Dateien erfolgreich kopiert wurden, indem Sie in Ihrem Webbrowser auf `http://localhost` navigieren.

---

Dieser Wiki-Eintrag führt Schritt für Schritt durch die Installation von Apache2 und das Kopieren von Inhalten aus einem GitHub-Repository in die HTML-Verzeichnisse.

