---
title: "Driving School Management System - Week 2"
weight: 2
date: 2026-09-04
draft: false
---

# Driving School Management System

Et portfolio projekt hvor vi gennem semesteret udvikler et backend system til administration af en køreskole.

## Development Log

### Week 2 – JPA Relations

I uge 2 arbejdede vi videre på vores **Driving School Management System** med fokus på relationer mellem entities i JPA.

Formålet var at udvide projektets datamodel, så forskellige dele af systemet kan forbindes med hinanden. I et køreskolesystem kan det eksempelvis være relationer mellem elever, kørelærere, køretimer og andre relevante oplysninger.

Fokus i denne uge var derfor på **JPA relations, DAO interfaces, JPQL queries og tests**.

## Det har vi arbejdet med

- Arbejdet med relationer mellem JPA entities
- Lært og anvendt relationstyper som:
  - `@OneToOne`
  - `@OneToMany`
  - `@ManyToOne`
  - `@ManyToMany`
- Arbejdet med forskellen mellem unidirectional og bidirectional relations
- Arbejdet med `mappedBy`
- Arbejdet med cascade types
- Udvidet projektets datamodel med relationer mellem relevante entities
- Arbejdet videre med DAO pattern
- Oprettet DAO interfaces til CRUD operationer
- Arbejdet med JPQL queries
- Hentet data på tværs af relaterede entities
- Arbejdet med joins gennem JPQL
- Oprettet tests til DAO funktionalitet

## Resultat

Ved slutningen af uge 2 har vi udvidet projektets datamodel med relationer mellem entities.

Vi har fået en bedre forståelse for, hvordan JPA bruges til at beskrive sammenhænge mellem objekter i Java og tabeller i databasen.

Vi har samtidig arbejdet videre med DAO pattern og JPQL, så data kan oprettes, hentes og behandles gennem en mere struktureret backend.

Resultatet er, at vores **Driving School Management System** nu har en mere realistisk databasestruktur, hvor forskellige entities kan forbindes med hinanden.

Dette giver et bedre fundament for de kommende uger, hvor projektet skal udvides med blandt andet data integration og eksterne API'er.