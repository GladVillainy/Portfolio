---
title: "IDS-Light"
date: 2026-08-01
description: "Et regelbaseret intrusion detection system."
summary: "Selvstændigt sikkerhedsprojekt bygget som IDS med regelbaseret detektion."
tags: ["Security", "Java", "Log analysis", "CSV", "CLI"]
code: "IDS-S1"
icon: "shield"
weight: 3
---
IDS Light er et konsolbaseret intrusion detection system skrevet i Java. Formålet var at besvare spørgsmålet: hvordan opdager man et misbrug, når man kun har adgang til systemets egne logdata?

Systemet er bygget oven på et eksisterende streamingtjeneste-projekt, som fungerer som det overvågede system. Hver gang en bruger logger ind eller sletter linjer i en fil, registreres hændelsen som en log entry. Herefter vurderes hændelsen mod tre regler: gentagne mislykkede loginforsøg, login uden for arbejdstid, og sletning af flere linjer end en fastsat grænse.

Overtrædes en regel, oprettes en trussel med type, bruger, tidsstempel, beskrivelse og en alvorlighedsgrad — mild, moderat eller alvorlig og brugeren låses. Både log entries og trusler persisteres i CSV filer, så tidligere hændelser kan gennemses efterfølgende. Det er altså trusselshistorikken, der udgør systemets egentlige værdi.

[Se koden på GitHub](https://github.com/GladVillainy/SP4-IDS-Light)
