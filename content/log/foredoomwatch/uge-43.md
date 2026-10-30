---
title: "Uge 43 - Deployment og dokumentation"
date: 2026-10-19
project: "foredoomwatch"
---
## Hvad lavede jeg denne uge?

Tirsdag lavede jeg en Main-klasse, som sætter applikationen i gang og initialiserer de forskellige dele. Jeg tilføjede også Dockerfile og en GitHub Actions workflow.

Lørdag importerede domænemodellen og mit ERD, jeg opdaget dog en fejl med ERD, jeg ikke havde lagt mærke til, at Host havde to fremmednøgler til Software. Derefter skrev jeg README'en, og jeg fjernede en user-controller, som ikke blev brugt. 

## Hvad lærte jeg?

Jeg lærte, hvordan en pipeline i GitHub Actions bygger og tester projektet, så man kan holde øje med fejl, og ikke manuelt skal ind og teste. Jeg lærte også, at et diagram kan afsløre fejl i koden, som jeg ikke selv havde set, fordi to fremmednøgler er nemme at overse i entiteterne, men tydelige i et ERD.

## Hvad var svært?

Det var svært at få workflow og tests til at virke sammen i GitHub Actions. Jeg rettede workflow-filen flere gange, og testene fejlede flere gange. Fejlen var at EntityManagerFactory lukket pga jeg bruget emf.close, jeg løste det ved at bruge app.stop() i stedet for at lukke EntityManagerFactory selv.

## Hvad gør jeg anderledes næste gang?

Jeg vil være mere opmærksom på, hvor jeg placerer JPA og Hibernate relationerne. Det er en ny teknologi, vi er blevet introduceret til i dette semester, og fejl er selvfølgelig en del af læringen.