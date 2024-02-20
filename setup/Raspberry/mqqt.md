---
title: MQTT
layout: home
nav_order: 3
parent: Raspberry
grand_parent: Setup
---
# Installation eines Mosquitto-Servers auf einem Raspberry Pi

## Schritt 1: Installation von Mosquitto

Führen Sie die folgenden Befehle aus, um Mosquitto auf Ihrem Raspberry Pi zu installieren:

```bash

sudo apt update

sudo apt install mosquitto mosquitto-clients

```

## Schritt 2: Konfiguration von Mosquitto

Bearbeiten Sie die Mosquitto-Konfigurationsdatei:

```bash

sudo nano /etc/mosquitto/mosquitto.conf

```

Fügen Sie die folgenden Zeilen hinzu, um die Benutzer "Pager" und "nodered" zu konfigurieren:

```

allow_anonymous false

password_file /etc/mosquitto/passwd

```

Speichern und schließen Sie die Datei, indem Sie `Ctrl + X`, dann `Y` und `Enter` drücken.

## Schritt 3: Benutzer hinzufügen

Führen Sie die folgenden Befehle aus, um die Benutzer "Pager" und "nodered" hinzuzufügen und ihre Passwörter festzulegen:

```bash

sudo mosquitto_passwd -c /etc/mosquitto/passwd Pager

sudo mosquitto_passwd /etc/mosquitto/passwd nodered

```

Geben Sie die Passwörter ein, wenn Sie dazu aufgefordert werden.

## Schritt 4: Autostart-Konfiguration

Bearbeiten Sie die Autostart-Konfigurationsdatei für Mosquitto:

```bash

sudo nano /etc/init.d/mosquitto

```

Fügen Sie den folgenden Inhalt hinzu:

```bash

!/bin/bash

### BEGIN INIT INFO

# Provides: mosquitto

# Required-Start: $remote_fs $syslog

# Required-Stop: $remote_fs $syslog

# Default-Start: 2 3 4 5

# Default-Stop: 0 1 6

# Short-Description: mosquitto MQTT v3.1 message broker

# Description: mosquitto is a MQTT v3.1 message broker

### END INIT INFO

DESC="Mosquitto MQTT v3.1 message broker"

NAME=mosquitto

DAEMON=/usr/sbin/$NAME

PIDFILE=/var/run/$NAME.pid

SCRIPTNAME=/etc/init.d/$NAME

# Exit if the package is not installed

[ -x "$DAEMON" ] || exit 0

. /lib/lsb/init-functions

case "$1" in

start)

log_daemon_msg "Starting $DESC" "$NAME"

start-stop-daemon --start --quiet --oknodo --background --pidfile $PIDFILE --make-pidfile --exec $DAEMON -- -c /etc/mosquitto/mosquitto.conf

log_end_msg $?

;;

stop)

log_daemon_msg "Stopping $DESC" "$NAME"

start-stop-daemon --stop --quiet --oknodo --pidfile $PIDFILE --exec $DAEMON

log_end_msg $?

;;

restart|force-reload)

$0 stop

sleep 1

$0 start

;;

*)

echo "Usage: $SCRIPTNAME {start|stop|restart|force-reload}" >&2

exit 1

;;

esac

exit 0

```

Speichern und schließen Sie die Datei, indem Sie `Ctrl + X`, dann `Y` und `Enter` drücken.

## Schritt 5: Autostart aktivieren

Führen Sie die folgenden Befehle aus, um den Autostart für Mosquitto zu aktivieren:

```bash

sudo chmod +x /etc/init.d/mosquitto

sudo update-rc.d mosquitto defaults

```

## Schritt 6: Neustart

Starten Sie den Raspberry Pi neu, um die Änderungen zu übernehmen:

```bash

sudo reboot

```

Nach dem Neustart sollte Mosquitto automatisch gestartet werden und die Benutzer "Pager" und "nodered" können sich mit ihren entsprechenden Passwörtern über MQTT verbinden.