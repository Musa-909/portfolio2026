---
title: "Driving School Management System - Week 3"
weight: 3
date: 2026-09-09
draft: false
---

# Driving School Management System

Et portfolio projekt hvor vi gennem semesteret udvikler et backend system til administration af en køreskole.

## Development Log

### Week 3 – Data Integration

I uge 3 arbejdede vi videre på vores **Driving School Management System** med fokus på Data Integration.

Formålet var at lære, hvordan vores Java applikation kan kommunikere med eksterne API'er og arbejde med data i JSON format.

I vores projekt valgte vi at integrere **Gemini API**, så systemet kan sende data til en ekstern service og modtage et svar tilbage.

## Det har vi arbejdet med

- Arbejdet med REST API'er
- Arbejdet med URI og endpoints
- Lært hvordan JSON bruges til at udveksle data
- Arbejdet med DTO'er (Data Transfer Objects)
- Arbejdet med konvertering mellem JSON og Java objekter
- Arbejdet med serialization og deserialization
- Brugt Jackson til behandling af JSON
- Arbejdet med `ObjectMapper`
- Oprettet DTO classes til API response:
  - `Candidate`
  - `Content`
  - `GeminiResponse`
  - `Part`
- Integreret Gemini API i projektet
- Oprettet `DrivingAiService`
- Sendt requests til et eksternt API fra Java
- Modtaget og behandlet JSON responses
- Oprettet `DrivingAiServiceTest` til at teste integrationen

## Resultat

Ved slutningen af uge 3 har vi integreret et eksternt API i vores **Driving School Management System**.

Vi har fået forståelse for, hvordan en Java applikation kan sende requests til et REST API og modtage data tilbage i JSON format.

Ved hjælp af DTO'er og Jackson kan JSON data konverteres til Java objekter, som derefter kan bruges i applikationen.

Vi har samtidig implementeret `DrivingAiService`, som håndterer kommunikationen med Gemini API, og lavet tests af funktionaliteten.

Resultatet er, at projektet nu ikke kun arbejder med vores egen database, men også kan hente og behandle data fra en ekstern service. Det giver os et godt fundament for at arbejde videre med API'er og flere backend funktioner i de kommende uger.