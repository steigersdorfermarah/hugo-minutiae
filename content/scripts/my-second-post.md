---
title: "Updaten des Systems"
date: 2021-10-27T17:27:59+07:00
---


## Aktualisieren der alten Türen
Für diesen Schritt empfehlen wir, die Verwendung von ssh zu aktivieren, insbesondere wenn Sie bereits viele Raspberries installiert haben,
ansonsten müssen Sie zu jeder Ihrer Türen gehen und sie händisch aktualisieren.

SEHR WICHTIG: Um die Synchronisation mit den anderen Raspberries zu ermöglichen, d. h. um die Himbeere zum Cluster hinzuzufügen,
müssen wir die neue Raspberry-IP-Adresse jeweils zu den Konfigurationsdateien der bereits laufenden Raspberries hinzufügen. 
Es ist sehr wichtig, dass der erste Raspberry, die Sie aktualisieren, der Clusterkopf ist, also die allererste Tür, die 
Sie eingerichtet haben. Die Reihenfolge der anderen spielt keine Rolle.

Aktualisieren Sie die alten Türen
Für diesen Schritt empfehlen wir wirklich, die Verwendung von ssh zu aktivieren, insbesondere wenn Sie bereits viele Himbeeren installiert haben, ansonsten müssen Sie zu jeder Ihrer Türen gehen und sie aktualisieren.

Gehen Sie nun für jeden Raspberry wie folgt vor, beginnend mit Ihrem 'Head Raspberry':

- Verlassen Sie den Kioskmodus und wechseln Sie zu einem Terminal, indem Sie F3 . drücken
- Mounten Sie den USB-Stick mit den Dateien wie im Installationsskript beschrieben
- Um zu verhindern, dass Sie die Konfigurationsdateien selbst aktualisieren, erhalten Sie die bereits aktualisierten Dateien
für die alten Raspberry zusammen mit den neuen Installationsdateien. Jeder Ordner, den Sie erhalten, heißt „IPAddress_Doorname“
und enthält eine Datei galera.cnf. Diese Dateien auf den alten Raspberry müssen Sie jetzt durch die neuen ersetzen.

{{<highlight go>}}sudo cp -r /media/usb/shdb/setup/<ipAddress_Doorname>/galera.cnf .
{{</highlight>}}
- Geben Sie sudo reboot ein, damit Ihre Änderungen wirksam werden, Sie befinden sich nach dem Neustart automatisch wieder im Kioskmodus (im Allgemeinen können Sie mit STRG+ALT+F1 zurückkehren)

## Neue Tür
Die Schritte sind genau die gleichen wie bei dem ersten Raspberry mit einer Ausnahme:

Diesmal können Sie die Konfigurationsdateien für den neuen Raspberry nicht mehr von dieser Website beziehen.


- Fügen Sie die Tür im Frontend zu einer der bereits laufenden Raspberries hinzu
- Sie erhalten eine Download-Option, die nach dem Hinzufügen der Tür einen Zip-Ordner zurückgibt.
- Entpacken Sie den Ordner und legen Sie die Dateien auf einen Stick
  - Beachten Sie, dass in diesem Ordner auch Dateien zum Aktualisieren der alten Türen enthalten sind. Sie erkennen den Ordner für die neue Tür an der Ordnerbezeichnung „ipAddress_doorname“

Achten Sie beim Ausführen der Installationsskripte darauf, denselben Benutzernamen und dasselbe Kennwort für das Skript setup.sh wie beim ersten Mal zu verwenden.
Es gibt keine Überprüfung, aber es funktioniert nicht, wenn Sie es falsch machen

Wenn Sie mit dem Installationsprozess fertig sind, geben Sie {{<highlight go>}}sudo reboot{{</highlight>}} ein, damit Ihre Änderungen wirksam werden
