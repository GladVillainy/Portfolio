---
title: "CUPCAKE – CupCake Ordering System"
date: 2026-06-01
description: "Java/Javalin/Thymeleaf/PostgreSQL webapp til bestilling af carports."
summary: "2. semesters eksamensprojekt – en fuld webapplikation til carport-bestilling."
tags: ["Java", "Javalin", "Thymeleaf", "PostgreSQL"]
code: "CUPCAKE-S2"
icon: "CupCake"
weight: 2
featureimage: "CupCake.png"
---
Olsker Cupcakes er en webapplikation bygget som en online bestillingsløsning for et cupcake-bageri. Formålet var at besvare spørgsmålet: hvordan lader man kunden sammensætte sin egen vare, når varen ikke findes på forhånd?

En cupcake er nemlig ikke et produkt i sig selv, men en kombination af en bund og en top, som hver især har sin egen pris. Kunden vælger de to dele, hvorefter systemet beregner prisen og lægger cupcaken i en indkøbskurv. Ved betaling omdannes kurven til en ordre, hvor hver enkelt cupcake gemmes som en ordrelinje med reference til den valgte bund og top. Betalingen trækkes fra kundens saldo, som administratoren kan fylde op.

Systemet skelner mellem to roller: kunden, der bestiller, og administratoren, der har adgang til ordreoversigt og kundeadministration. Applikationen er skrevet i Java med Javalin som webframework, Thymeleaf til rendering og PostgreSQL som database.

[Se koden på GitHub](https://github.com/GladVillainy/CupCakeSemester2SP2)