---
title: "FOG – Carport Ordering System"
date: 2026-06-01
description: "Java/Javalin/Thymeleaf/PostgreSQL webapp til bestilling af carports."
summary: "2. semesters eksamensprojekt – en fuld webapplikation til carport-bestilling."
tags: ["Java", "Javalin", "Thymeleaf", "PostgreSQL"]
code: "FOG-S2"
icon: "fog"
weight: 2
featureimage: "fog.svg"
---
Projekt Carport er en webapplikation udviklet for Johannes Fog A/S, hvor kunden selv kan tilpasse og bestille en carport. Formålet var at besvare spørgsmålet: hvordan automatiserer man en salgsproces, uden at fjerne sælgeren fra den?

Kunden angiver bredde, længde, højde, tagtype og om der ønskes et skur, og sender herefter en forespørgsel. Systemet beregner automatisk styklisten ud fra kravene i bygselv-vejledningen CP01 og genererer en SVG-tegning af konstruktionen. Sælgeren fastsætter selv prisen og sender et tilbud til kunden via mail. Først når kunden har betalt, frigives stykliste og tegning — et krav Fog selv stillede, da der ligger et reelt stykke arbejde i at producere dem.

Systemets omdrejningspunkt er ordren, som binder kunden, carporten og styklistens ordrelinjer sammen. Applikationen er skrevet i Java med Javalin, Thymeleaf og PostgreSQL, og er opdelt i lag med hver sit ansvarsområde: controllers, persistence, entities, app, validators, utility, config og exceptions.

Den vigtigste læring fra projektet var, at datamodellen skal være besluttet i fællesskab og gennemtænkt til ende, inden kodningen begynder. Vi opdagede først sent, at databasen ikke var fuldt normaliseret, og at en refaktorering på det tidspunkt ville være for tidskrævende.

[Se koden på GitHub](https://github.com/GladVillainy/Carport2SemesterExam)