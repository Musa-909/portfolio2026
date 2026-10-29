---
title: "Exam Portfolio"
date: 2026-10-27
draft: false
showDate: false
showReadingTime: false
showWordCount: false
showAuthor: false
---

# Driving School Management System – DriveApp

DriveApp er vores semesterprojekt, hvor vi har udviklet et backend system til administration af en køreskole. Projektet er udviklet i samarbejde mellem Musa Sayed og Amaan Mahomed.

Formålet er at gøre det nemmere at administrere elever, kørelærere, køretimer og bookinger gennem et samlet system. Elever kan registrere sig, logge ind, se ledige køretimer og oprette bookinger. Kørelærere har adgang til administrative funktioner.

Vi har udviklet projektet i Java med Javalin, Hibernate/JPA og PostgreSQL. Vi har også integreret en AI-assistent baseret på Google Gemini, implementeret sikkerhed med JWT og BCrypt, skrevet automatiserede tests og deployet vores REST API.

Denne side dokumenterer udviklingen fra uge 1 til uge 8 og viser, hvordan vi har anvendt semesterets læringsmål.

---

## Projektlinks

**GitHub Repository:** [DriveApp – GitHub](https://github.com/Musa-909/DriveApp)

**Deployed API:** [DriveApp](https://driveapp.website)

**Health Check:** [GET /api/health](https://driveapp.website/api/health)

---

## Projektudvikling

| Kursusemne | Hvordan vi har anvendt det i DriveApp | Undervisningsmateriale |
|---|---|---|
| **01 JPA Basics** | Vi har brugt Hibernate/JPA og DAO-klasser til at gemme og administrere data i PostgreSQL. | [JPA Basics](https://3sem.kursusmaterialer.dk/backend/jpa-basics/) |
| **02 JPA Relations** | Vi har oprettet relationer mellem elever, kørelærere, køretimer og bookinger. | [JPA Relations](https://3sem.kursusmaterialer.dk/backend/jpa-relations/) |
| **03 Data Integration** | Vi har brugt DTO'er, JSON og Java HttpClient til at udveksle data med Google Gemini. | [Data Integration](https://3sem.kursusmaterialer.dk/backend/data-integration/) |
| **04 Concurrency** | Vi har brugt `CompletableFuture` til asynkrone HTTP-requests til Google Gemini. | [Concurrency](https://3sem.kursusmaterialer.dk/backend/concurrency/) |
| **05 REST API Intro** | Vi har udviklet et REST API med Javalin, routes, controllers og HTTP-metoder. | [REST API Intro](https://3sem.kursusmaterialer.dk/backend/rest-intro/) |
| **06 REST & Test** | Vi har brugt JUnit, REST Assured og Testcontainers til automatiserede tests. | [REST & Test](https://3sem.kursusmaterialer.dk/backend/rest-test/) |
| **07 Security** | Vi har implementeret JWT, BCrypt og rollebaseret adgangskontrol. | [Security](https://3sem.kursusmaterialer.dk/backend/security/) |
| **08 Deployment & DevOps** | Vi har brugt GitHub Actions, Docker, Docker Hub og DigitalOcean til deployment. | [Deployment & DevOps](https://3sem.kursusmaterialer.dk/backend/deployment/) |

---

# Week 1 – Project Setup, JPA & CRUD

I den første uge begyndte vi udviklingen af DriveApp og oprettede projektets grundlæggende struktur. Vi brugte Maven, JPA, Hibernate og PostgreSQL til at arbejde med persistente Java-objekter.

### Det har vi implementeret

- Oprettet Java-projektet med Maven
- Konfigureret Hibernate/JPA og databaseforbindelse
- Arbejdet med Student og Instructor entities
- Oprettet DAO-klasser til databaseoperationer
- Implementeret CRUD-operationer med EntityManager

### Resultat

Vi fik etableret backendens databasegrundlag og et DAO-lag, som senere kunne bruges af vores REST API.

---

# Week 2 – JPA Relations, JPQL & Testing

I uge 2 arbejdede vi med relationer mellem Student, Instructor, Lesson og Booking. Vi brugte JPA til at forbinde vores entities og arbejdede med JPQL og automatiserede DAO-tests.

### Det har vi implementeret

- Oprettet relationer mellem vores entities
- Arbejdet med `@OneToMany`, `@ManyToOne` og foreign keys
- Udvidet DAO-klasserne med databaseforespørgsler
- Arbejdet med JPQL
- Skrevet JUnit-tests af databasefunktionalitet

### Resultat

Datamodellen kunne nu repræsentere forbindelserne mellem køreskolens elever, kørelærere, køretimer og bookinger.

---

# Week 3 – Data Integration & Gemini AI

I uge 3 arbejdede vi med JSON, DTO'er og integration med eksterne API'er. Vi integrerede Google Gemini som en AI-assistent til spørgsmål om køreteori, trafikregler og trafiksikkerhed.

### Det har vi implementeret

- Oprettet `DrivingAiService`
- Brugt Java HttpClient til kommunikation med Gemini
- Arbejdet med Jackson, ObjectMapper og JSON
- Oprettet DTO'er til AI-requests og Gemini-responses
- Arbejdet med `Candidate`, `Content`, `Part` og `GeminiResponse`
- Skrevet `DrivingAiServiceTest`

### Resultat

DriveApp kan sende spørgsmål til Gemini og returnere et svar gennem vores backend. Senere har vi også tilføjet et beskyttet AI-endpoint og automatiserede API-tests.

---

# Week 4 – Concurrency & Booking System

I uge 4 arbejdede vi med concurrency, threads og race conditions. Vi undersøgte blandt andet, hvordan samtidige bookingforsøg kan skabe problemer i et bookingsystem.

### Det har vi implementeret

- Arbejdet med `Runnable`, `ExecutorService` og `synchronized`
- Undersøgt samtidige bookingforsøg og race conditions
- Arbejdet med kontrol af eksisterende bookinger
- Brugt `CompletableFuture` til asynkrone HTTP-requests i AI-integrationen

### Resultat

Vi fik erfaring med både samtidighedsproblemer ved booking og asynkron kommunikation med en ekstern service. I den nuværende kode anvendes `CompletableFuture` i AI-integrationen, mens bookingvalidering håndteres i backendens bookingfunktionalitet.

---

# Week 5 – REST API, Javalin & Documentation

I uge 5 gjorde vi backendens funktioner tilgængelige via HTTP med Javalin. Vi organiserede koden i routes, controllers, DAO-klasser og DTO'er.

### Det har vi implementeret

- Oprettet StudentRoutes, InstructorRoutes, LessonRoutes og BookingRoutes
- Oprettet controllers til de fire områder
- Implementeret GET, POST, PUT og DELETE, hvor det er relevant
- Arbejdet med request- og response-DTO'er
- Implementeret HTTP-statuskoder og JSON-fejlbeskeder
- Dokumenteret vores API i README

### Resultat

DriveApp fik et REST API, som kan bruges til at administrere elever, kørelærere, køretimer og bookinger.

---

# Week 6 – REST Testing & Integration Tests

I uge 6 fokuserede vi på automatiserede tests af både REST API og databaseoperationer.

### Det har vi implementeret

- Skrevet API-tests med JUnit og REST Assured
- Testet endpoints for Student, Instructor, Lesson og Booking
- Testet DAO-klasser med Testcontainers og PostgreSQL
- Arbejdet med gyldige og ugyldige requests
- Oprettet `AiApiTest`, som kan teste AI-endpointet med et simuleret svar
- Arbejdet med `DrivingAiServiceTest`, som tester den eksterne Gemini-integration

### Resultat

Vi kan teste store dele af vores backend automatisk. API-testene kan starte Javalin på en ledig port, og AI-endpointet kan testes uden at kontakte Gemini.

---

# Week 7 – Security, BCrypt & JWT

I uge 7 implementerede vi authentication og authorization. Formålet var at beskytte API'et og give elever og kørelærere forskellige rettigheder.

### Det har vi implementeret

- Implementeret BCrypt password hashing
- Oprettet login for både elever og kørelærere
- Implementeret JWT-tokens og sikkerhedsfilter
- Arbejdet med rollerne STUDENT og INSTRUCTOR
- Implementeret rolle- og ejerskabskontrol på relevante endpoints
- Skrevet tests af JWT og BCrypt

### Resultat

Registrering, login og health check er offentlige, mens øvrige API-endpoints kræver JWT. Elever kan administrere deres egne oplysninger, mens kørelærere har adgang til flere administrative funktioner.

---

# Week 8 – Deployment & DevOps

I uge 8 arbejdede vi med at gøre DriveApp tilgængelig uden for vores lokale udviklingsmiljø.

### Det har vi implementeret

- Oprettet Dockerfile og Docker Compose-konfiguration
- Arbejdet med Docker images, containers og Docker Hub
- Oprettet GitHub Actions workflow til CI/CD
- Arbejdet med automatiseret build og tests
- Deployet backend på DigitalOcean
- Arbejdet med PostgreSQL, miljøvariabler, domæne og HTTPS
- Brugt Caddy og Watchtower i deploymentopsætningen

### Deployment

Vores API er tilgængeligt på [DriveApp – Deployed API](https://driveapp.website).

### Resultat

Vi har fået erfaring med processen fra lokal Java-udvikling til en deployet backend med automatiserede workflows.

---

# DriveApp – System Features

## Student Management

Elever kan registrere sig, logge ind og arbejde med deres egne oplysninger. Systemet anvender rolle- og ejerskabskontrol for at begrænse adgangen.

## Instructor Management

Kørelærere kan logge ind og har adgang til administrative funktioner, herunder håndtering af elever og køretimer.

## Lesson & Booking Management

Systemet understøtter oprettelse og administration af køretimer og bookinger. Elever kan se ledige køretimer via `GET /api/lessons/available` og oprette bookinger. Backend kontrollerer blandt andet, at en køretime ikke allerede er booket.

## AI Assistant

Vi har integreret Google Gemini gennem `DrivingAiService`. En bruger med gyldigt JWT kan sende spørgsmål til `POST /api/ai/driving-advice` og modtage et AI-genereret svar.

## Authentication & Authorization

Vi bruger BCrypt til passwords, JWT til authentication og roller til authorization. Adgangskontrol beskytter relevante endpoints.

## Automated Testing

Projektet indeholder DAO-tests, REST API-tests, security-tests og AI-tests. Vi bruger blandt andet JUnit, REST Assured og Testcontainers.

---

# Project Architecture

DriveApp er udviklet som en Java-backend med en lagdelt struktur.

### Routes og Controllers

Javalin routes forbinder HTTP-requests med controllers, som håndterer requests og responses.

### Services

`DrivingAiService` håndterer kommunikationen med Google Gemini og anvender Java HttpClient og `CompletableFuture`.

### DAO

DAO-klasserne håndterer databaseoperationer med Hibernate/JPA og PostgreSQL.

### Entities

De centrale entities er `Student`, `Instructor`, `Lesson` og `Booking`.

### DTO

DTO'er styrer, hvilke oplysninger vores API modtager og returnerer, så eksempelvis passwords ikke indgår i almindelige response-DTO'er.

### Security

`Filter` og `JWTToken` bruges til at validere tokens og håndhæve adgangskontrol.

---

# API Oversigt

| Område | Eksempler på endpoints | Adgang |
|---|---|---|
| Health | `GET /api/health` | Offentlig |
| Registrering og login | `POST /api/students`, `POST /api/students/login`, `POST /api/instructors/login` | Offentlig |
| Elever | `GET /api/students`, `GET/PUT/DELETE /api/students/{id}` | JWT og adgangskontrol |
| Kørelærere | `GET/POST /api/instructors`, `GET/PUT/DELETE /api/instructors/{id}` | Rollebaseret |
| Køretimer | `GET/POST /api/lessons`, `GET/PUT/DELETE /api/lessons/{id}`, `GET /api/lessons/available` | JWT, kørelærer ved ændringer |
| Bookinger | `GET/POST /api/bookings`, `GET/PUT/DELETE /api/bookings/{id}` | JWT og adgangskontrol |
| AI | `POST /api/ai/driving-advice` | JWT |

---

# Samlet resultat

Gennem 3. semester har vi udviklet DriveApp fra et mindre Java-projekt til et backend-system med database, REST API, AI-integration, sikkerhed, automatiserede tests og deployment.

Vi har arbejdet med JPA, Hibernate, PostgreSQL, Javalin, DTO'er, JSON, Java HttpClient, `CompletableFuture`, BCrypt, JWT, JUnit, REST Assured, Testcontainers, Docker og GitHub Actions.

Projektet har givet os erfaring med hele udviklingsprocessen fra datamodel og backend-logik til testing, security og deployment. DriveApp samler dermed semesterets centrale backend-emner i et samlet projekt.
