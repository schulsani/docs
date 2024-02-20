---
# snazzyDocs - DO NOT REMOVE OR EDIT BELOW THIS LINE
title: Webserver
id: Q6A-73WS-QFS-I07
slug: webserver
isVisible: true
lastUpdated: '2024-02-20 05:49:27'
---
### <span style="color:rgb(10, 10, 10);"># Installation von Apache2 und Kopieren von Inhalten aus GitHub</span>

<div><p><br></p></div>

<div><p>## Apache2 Installation</p></div>

<div><p><br></p></div>

<div><p>1. Öffnen Sie die Terminalanwendung auf Ihrem System.</p></div>

<div><p>2. Geben Sie den folgenden Befehl ein, um Apache2 zu installieren:</p></div>

<div><p><br></p></div>

<div><p>```</p></div>

<div><p>sudo apt-get update</p></div>

<div><p>sudo apt-get install apache2</p></div>

<div><p>```</p></div>

<div><p><br></p></div>

<div><p>3. Warten Sie, bis die Installation abgeschlossen ist. Apache2 sollte nun erfolgreich auf Ihrem System installiert sein.</p></div>

<div><p><br></p></div>

<div><p>## Kopieren von Inhalten aus GitHub</p></div>

<div><p><br></p></div>

<div><p>1. Öffnen Sie erneut das Terminal.</p></div>

<div><p>2. Navigieren Sie zum Verzeichnis, in das Sie den Inhalt von GitHub herunterladen möchten. Verwenden Sie dazu den Befehl `cd`, um das gewünschte Verzeichnis zu erreichen.</p></div>

<div><p>3. Klonen Sie das GitHub-Repository mit dem folgenden Befehl:</p></div>

<div><p><br></p></div>

<div><p>```</p></div>

<div><p>git clone https://github.com/schulsani/Server</p></div>

<div><p>```</p></div>

<div><p><br></p></div>

<div><p>4. Wechseln Sie in das Apache HTML-Verzeichnis. Standardmäßig befindet sich dieses unter `/var/www/html`. Verwenden Sie den Befehl `cd`, um dorthin zu navigieren.</p></div>

<div><p>5. Kopieren Sie den Inhalt des Apache-Ordners aus dem geklonten Repository in das HTML-Verzeichnis mit dem Befehl `cp`:</p></div>

<div><p><br></p></div>

<div><p>```</p></div>

<div><p>cp -r Server/Apache/* /var/www/html/</p></div>

<div><p>```</p></div>

<div><p><br></p></div>

<div><p>6. Überprüfen Sie anschließend, ob die Dateien erfolgreich kopiert wurden, indem Sie in Ihrem Webbrowser auf `http://localhost` navigieren.</p></div>

<div><p><br></p></div>

<div><p>---</p></div>

<div><p><br></p></div>

<div><p>Dieser Wiki-Eintrag führt Schritt für Schritt durch die Installation von Apache2 und das Kopieren von Inhalten aus einem GitHub-Repository in die HTML-Verzeichnisse.</p></div>

<br />