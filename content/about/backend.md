---
title: 'Backend'
date: 2021-10-27T17:27:59+07:00
---

Das Backend von NestJ stellt einerseits die Daten für das Frontend über die REST-Api bereit und übernimmt über MQTT auch
die Kommunikation mit der Fingerabdrucksensor-Steuerungssoftware. Dies wird zB benötigt zum Beibehalten der Protokolle, 
zum Abrufen der Fingerabdrücke für einen neuen Benutzer und zum Überprüfen, ob der Benutzer Zugang für eine Tür hat, 
wenn er versucht, einzutreten.

![](../../static/backend.jpg)
