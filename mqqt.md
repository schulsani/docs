---
# snazzyDocs - DO NOT REMOVE OR EDIT BELOW THIS LINE
title: MQQT
id: JKN-9FVD-U3Y-B59
slug: mqqt
isVisible: true
lastUpdated: '2024-02-20 11:54:35'
---
\# Installation eines Mosquitto-Servers auf einem Raspberry Pi

<br />

\## Schritt 1: Installation von Mosquitto

<br />

Führen Sie die folgenden Befehle aus, um Mosquitto auf Ihrem Raspberry Pi zu installieren:

<br />

\`\`\`bash

sudo apt update

sudo apt install mosquitto mosquitto-clients

\`\`\`

<br />

\## Schritt 2: Konfiguration von Mosquitto

<br />

Bearbeiten Sie die Mosquitto-Konfigurationsdatei:

<br />

\`\`\`bash

sudo nano /etc/mosquitto/mosquitto.conf

\`\`\`

<br />

Fügen Sie die folgenden Zeilen hinzu, um die Benutzer "Pager" und "nodered" zu konfigurieren:

<br />

\`\`\`

allow\_anonymous false

password\_file /etc/mosquitto/passwd

\`\`\`

<br />

Speichern und schließen Sie die Datei, indem Sie \`Ctrl + X\`, dann \`Y\` und \`Enter\` drücken.

<br />

\## Schritt 3: Benutzer hinzufügen

<br />

Führen Sie die folgenden Befehle aus, um die Benutzer "Pager" und "nodered" hinzuzufügen und ihre Passwörter festzulegen:

<br />

\`\`\`bash

sudo mosquitto\_passwd -c /etc/mosquitto/passwd Pager

sudo mosquitto\_passwd /etc/mosquitto/passwd nodered

\`\`\`

<br />

Geben Sie die Passwörter ein, wenn Sie dazu aufgefordert werden.

<br />

\## Schritt 4: Autostart-Konfiguration

<br />

Bearbeiten Sie die Autostart-Konfigurationsdatei für Mosquitto:

<br />

\`\`\`bash

sudo nano /etc/init.d/mosquitto

\`\`\`

<br />

Fügen Sie den folgenden Inhalt hinzu:

<br />

\`\`\`bash

# !/bin/bash

\### BEGIN INIT INFO

\# Provides: mosquitto

\# Required-Start: $remote\_fs $syslog

\# Required-Stop: $remote\_fs $syslog

\# Default-Start: 2 3 4 5

\# Default-Stop: 0 1 6

\# Short-Description: mosquitto MQTT v3.1 message broker

\# Description: mosquitto is a MQTT v3.1 message broker

\### END INIT INFO

<br />

DESC="Mosquitto MQTT v3.1 message broker"

NAME=mosquitto

DAEMON=/usr/sbin/$NAME

PIDFILE=/var/run/$NAME.pid

SCRIPTNAME=/etc/init.d/$NAME

<br />

\# Exit if the package is not installed

\[ -x "$DAEMON" \] || exit 0

<br />

. /lib/lsb/init-functions

<br />

case "$1" in

start)

log\_daemon\_msg "Starting $DESC" "$NAME"

start-stop-daemon --start --quiet --oknodo --background --pidfile $PIDFILE --make-pidfile --exec $DAEMON -- -c /etc/mosquitto/mosquitto.conf

log\_end\_msg $?

;;

stop)

log\_daemon\_msg "Stopping $DESC" "$NAME"

start-stop-daemon --stop --quiet --oknodo --pidfile $PIDFILE --exec $DAEMON

log\_end\_msg $?

;;

restart|force-reload)

$0 stop

sleep 1

$0 start

;;

\*)

echo "Usage: $SCRIPTNAME {start|stop|restart|force-reload}" &gt;&2

exit 1

;;

esac

<br />

exit 0

\`\`\`

<br />

Speichern und schließen Sie die Datei, indem Sie \`Ctrl + X\`, dann \`Y\` und \`Enter\` drücken.

<br />

\## Schritt 5: Autostart aktivieren

<br />

Führen Sie die folgenden Befehle aus, um den Autostart für Mosquitto zu aktivieren:

<br />

\`\`\`bash

sudo chmod +x /etc/init.d/mosquitto

sudo update-rc.d mosquitto defaults

\`\`\`

<br />

\## Schritt 6: Neustart

<br />

Starten Sie den Raspberry Pi neu, um die Änderungen zu übernehmen:

<br />

\`\`\`bash

sudo reboot

\`\`\`

<br />

Nach dem Neustart sollte Mosquitto automatisch gestartet werden und die Benutzer "Pager" und "nodered" können sich mit ihren entsprechenden Passwörtern über MQTT verbinden.