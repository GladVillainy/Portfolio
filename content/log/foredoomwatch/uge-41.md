---
title: "Uge 41 - Controller og sikkerhed"
date: 2026-10-05
project: "foredoomwatch"
---
## Hvad lavede jeg denne uge?

Jeg byggede controller-laget. Jeg lavede et IController interface med syv metoder, hvor getLongId og getStringId er default-metoder, og brugte det til Finding, Host og Software controllerne. Jeg lavede også en FindingMapper og to metoder i FindingDAO, som sorterer findings efter CVSS-score.

Derefter tilføjede jeg sikkerhed. Først lavede jeg en rolle-enum og security-interfaces på User, men senere importerede jeg skolens security-lag og flyttede de relevante klasser over i en security mappe. Jeg omdøbte også MissingInput til ValidationException, tilføjede e -mail validering med regex.

## Hvad lærte jeg?

Jeg lærte, at default metoder i et interface kan fjerne gentaget kode i controllerne, fx når et id skal læses fra URL'en. Jeg lærte også, hvordan roller og JWT bruges til at styre, hvilke endpoints en bruger har adgang til ved brug af enum klassen.

## Hvad var svært?

Det var svært at få sikkerheden til at passe ind i min egen struktur. Jeg havde allerede påbegyndt mit eget sikkerhedslag, så det var svært at importere skolens, og det blev derfor lidt kringlet. Det betød, at jeg blev nød til at erstattet, og at jeg skulle flytte og omdøbe flere klasser.

Der var også en del besvær med secret key. Jeg bruger typisk miljøvariabler, fordi jeg synes, det er mere sikkert, men sikkerhedsklasserne læste nøglen fra config.properties, og det tog lidt tid og finde ud af hvorfor tingne ikke virket.
