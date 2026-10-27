---
title: "Driving School Management System - Week 7"
weight: 8
date: 2026-10-13
draft: false
---

# Driving School Management System

Et portfolio projekt hvor vi gennem semesteret udvikler et backend system til administration af en køreskole.

## Development Log

### Week 7 – Security

I uge 7 arbejdede vi med sikkerhed i REST API'er, hvor fokus var på at beskytte vores applikation mod uautoriseret adgang.

Vi lærte om authentication, authorization, password hashing med BCrypt og JSON Web Tokens (JWT).

Formålet var at forstå, hvordan man kan sikre, at brugere kun får adgang til de funktioner og oplysninger, de har tilladelse til.

Som en del af undervisningen arbejdede vi med en Hotel API, hvor vi fik erfaring med sikkerhed i Java, Javalin, Hibernate og PostgreSQL.

Vi arbejdede efterfølgende videre på vores Driving School Management System, hvor vi implementerede sikkerhed ved hjælp af BCrypt og JWT.

## Det har vi arbejdet med

- Lært om authentication og authorization
- Arbejdet med BCrypt til password hashing
- Lært hvorfor passwords ikke bør gemmes i plain text
- Arbejdet med JSON Web Tokens (JWT)
- Lært om JWT's opbygning og funktion
- Arbejdet med User og Role entities
- Arbejdet med sikkerhed i REST API'er
- Implementeret password hashing i DriveApp
- Implementeret JWT authentication
- Arbejdet med brugerroller og adgangskontrol
- Beskyttet endpoints mod uautoriseret adgang
- Arbejdet med sikkerhed i Javalin

## Resultat

Ved slutningen af uge 7 havde vi fået en bedre forståelse for, hvordan sikkerhed fungerer i backend applikationer.

I vores Driving School Management System implementerede vi BCrypt til sikker opbevaring af passwords og JWT til authentication.

Det betyder, at brugere kan logge ind og modtage en token, som bruges til at identificere dem ved efterfølgende requests.

Vi arbejdede samtidig med authorization, så forskellige brugerroller kun har adgang til de funktioner, de har tilladelse til.

Samlet set har arbejdet med sikkerhed gjort vores backend mere sikker og givet os praktisk erfaring med authentication, authorization og beskyttelse af REST API'er.