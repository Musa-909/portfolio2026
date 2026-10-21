---
title: "Driving School Management System - Week 4"
weight: 4
date: 2026-09-13
draft: false
---

# Driving School Management System

Et portfolio projekt hvor vi gennem semesteret udvikler et backend system til administration af en køreskole.

## Development Log

### Week 4 – Concurrency

I uge 4 arbejdede vi med Concurrency i Java, hvor fokus var på at forstå, hvordan flere opgaver kan udføres samtidigt ved hjælp af threads.

Vi lærte, hvordan threads fungerer, og hvordan man kan bruge dem til at håndtere flere opgaver i en applikation.

Vi arbejdede også med ExecutorService, som gør det muligt at administrere flere threads.

Et vigtigt emne var race conditions, som kan opstå, når flere threads forsøger at ændre de samme data samtidigt.

I vores Driving School Management System arbejdede vi med at forhindre, at flere elever kunne booke den samme køretime.

## Det har vi arbejdet med

- Lært om Concurrency og Multithreading i Java
- Arbejdet med threads og hvordan de fungerer
- Arbejdet med ExecutorService
- Lært om race conditions
- Arbejdet med synchronized metoder
- Implementeret concurrency i vores booking system
- Oprettet en test med to elever, der forsøger at booke samme køretime
- Brugt ExecutorService med to threads
- Brugt synchronized på bookLesson metoden for at undgå dobbeltbookinger

## Resultat

Ved slutningen af uge 4 har vi fået en bedre forståelse for, hvordan Concurrency fungerer i Java, og hvordan flere threads kan arbejde samtidigt.

I vores Driving School Management System har vi arbejdet med booking systemet, hvor to elever forsøger at booke den samme køretime på samme tidspunkt.

Ved hjælp af ExecutorService og synchronized har vi sikret, at kun én elev kan gennemføre bookingen.

Det har givet os en bedre forståelse for, hvordan Concurrency kan bruges i backend udvikling, og hvordan man kan undgå problemer med race conditions.