---
title: "ForeDoomWatch - Asset and Vulnerability Tracker"
date: 2026-08-20
description: "Under progress"
summary: "3. semesters eksamensprojekt – en fuld applikation til at holde styr på assets og vulnerabilities"
tags: ["Java", "JPA", "REST API", "PostgreSQL"]
code: "ForeDoomWatch-S3"
icon: "network"
weight: 1
featureimage: "foredoomwatch.png"
---
ForeDoomWatch er en backend-applikation til sårbarheds- og asset-håndtering. Formålet var at besvare spørgsmålet: hvordan finder man ud af, om den software man rent faktisk kører, indeholder kendte sårbarheder? NVD offentliggør alle kendte CVE'er, men NVD ved ikke hvad man ejer. Det er her foredoom-watch kommer i spil.

En bruger registrerer sine maskiner og den software med tilhørende version, der kører på hver enkelt maskine. Systemet slår denne software op mod NVD's CVE-API og opretter et finding for hvert match. En finding er ikke blot en forbindelse mellem software og sårbarhed, men et selvstændigt objekt med sin egen livscyklus, hvor status kan ændres fra OPEN til IN_PROGRESS til RESOLVED. Det er altså findingen der udgør selve arbejdsgangen i systemet.

[Se koden på GitHub](https://github.com/GladVillainy/ForeDoomWatch)