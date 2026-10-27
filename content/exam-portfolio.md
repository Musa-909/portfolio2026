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

DriveApp er vores semesterprojekt, hvor vi har udviklet et backend system til administration af en køreskole.

Formålet med projektet er at gøre det nemmere at administrere elever, kørelærere, køretimer og bookinger gennem et samlet system.

Vi har udviklet projektet i Java og brugt PostgreSQL som database. Gennem semesteret har vi løbende udvidet systemet med de teknologier og emner, vi har arbejdet med i undervisningen.

Systemet indeholder blandt andet funktioner til håndtering af elever, kørelærere, køretimer og bookinger. Vi har også integreret en AI-assistent, som kan hjælpe med spørgsmål om køreteori og trafikregler.

Derudover har vi arbejdet med REST API, automatiserede tests, sikkerhed og deployment.

Denne side dokumenterer udviklingen af DriveApp fra uge 1 til uge 8 og viser, hvordan vi har anvendt semesterets læringsmål i vores eget projekt.

---

## Project Links

**GitHub Repository:**

[DriveApp – GitHub](https://github.com/Musa-909/DriveApp)

**Deployed API:**

[DriveApp](https://driveapp.website)

**Exam Video:**

Coming soon

---

## Projektudvikling

| Kursusemne | Hvordan vi har anvendt det i DriveApp | Undervisningsmateriale |
|---|---|---|
| **01 JPA Basics** | Vi har brugt Hibernate/JPA og DAO-klasser til at gemme og administrere data i PostgreSQL. | [JPA Basics](https://3sem.kursusmaterialer.dk/backend/jpa-basics/) |
| **02 JPA Relations** | Vi har oprettet relationer mellem elever, kørelærere, køretimer og bookinger. | [JPA Relations](https://3sem.kursusmaterialer.dk/backend/jpa-relations/) |
| **03 Data Integration** | Vi har brugt DTO'er, JSON og Java HttpClient til at udveksle data og kommunikere med Google Gemini. | [Data Integration](https://3sem.kursusmaterialer.dk/backend/data-integration/) |
| **04 Concurrency** | Vi har brugt `CompletableFuture` til at håndtere asynkrone HTTP-requests til Google Gemini. | [Concurrency](https://3sem.kursusmaterialer.dk/backend/concurrency/) |
| **05 REST API Intro** | Vi har udviklet vores REST API med Javalin, routes, controllers og HTTP-metoder. | [REST API Intro](https://3sem.kursusmaterialer.dk/backend/rest-intro/) |
| **06 REST & Test** | Vi har brugt JUnit og REST Assured til at teste vores API-endpoints og funktionalitet. | [REST & Test](https://3sem.kursusmaterialer.dk/backend/rest-test/) |
| **07 Security** | Vi har implementeret JWT authentication, BCrypt password hashing og rollebaseret adgangskontrol. | [Security](https://3sem.kursusmaterialer.dk/backend/security/) |
| **08 Deployment & DevOps** | Vi har brugt GitHub Actions, Docker, Docker Hub og DigitalOcean til at deploye vores backend. | [Deployment & DevOps](https://3sem.kursusmaterialer.dk/backend/deployment/) |
---

# Week 1 – Project Setup, JPA & CRUD

I den første uge begyndte vi udviklingen af DriveApp.

Vi startede med at planlægge projektets grundlæggende struktur og oprette forbindelsen mellem vores Java-applikation og PostgreSQL.

Vi brugte JPA og Hibernate til at håndtere kommunikationen med databasen, så vi kunne arbejde med Java-objekter i stedet for at skrive SQL til alle databaseoperationer.

### Det har vi implementeret

- Oprettet vores Java-projekt med Maven
- Konfigureret JPA og Hibernate
- Oprettet forbindelse til PostgreSQL
- Arbejdet med vores første entities
- Oprettet Student og Instructor
- Oprettet DAO-klasser til databaseoperationer
- Implementeret CRUD-operationer
- Arbejdet med EntityManager
- Konfigureret HibernateConfig
- Testet vores databaseforbindelse

### Resultat

Vi fik etableret projektets grundlæggende backend og databaseforbindelse.

Gennem vores DAO-lag kunne vi oprette, hente, opdatere og slette oplysninger i databasen.

Det gav os et fundament, som vi kunne bygge videre på gennem resten af semesteret.

---

# Week 2 – JPA Relations, JPQL & Testing

I uge 2 fortsatte vi med at udvikle databasestrukturen i DriveApp.

Vi arbejdede med relationer mellem vores entities og lærte, hvordan forskellige tabeller kan forbindes ved hjælp af JPA.

Det var vigtigt for vores projekt, fordi en køreskole har flere forskellige oplysninger, der hænger sammen.

Eksempelvis skal en køretime kunne forbindes til en kørelærer, og en booking skal kunne forbindes til en elev.

### Det har vi implementeret

- Arbejdet med JPA-relationer
- Udvidet vores entities
- Arbejdet med Student, Instructor, Lesson og Booking
- Implementeret relationer mellem vores entities
- Brugt @OneToMany og @ManyToOne
- Arbejdet med foreign keys
- Udvidet vores DAO-klasser
- Implementeret JPQL-queries
- Arbejdet med databaseforespørgsler
- Oprettet automatiserede tests med JUnit
- Testet CRUD-operationer og relationer

### Resultat

Vi fik udvidet vores databasestruktur, så de forskellige dele af køreskolen kunne forbindes.

Vi lærte samtidig at bruge JPQL til at hente bestemte oplysninger fra databasen.

Ved hjælp af automatiserede tests kunne vi kontrollere, at vores DAO metoder fungerede som forventet.

---

# Week 3 – Data Integration & Gemini AI

I uge 3 arbejdede vi med data integration og kommunikation med eksterne API'er.

Vi valgte at integrere Google Gemini i DriveApp for at tilføje en AI-assistent til vores køreskolesystem.

Formålet var at give elever mulighed for at stille spørgsmål om køreteori, trafikregler og trafiksikkerhed.

Vi arbejdede samtidig med JSON og DTO'er for at kunne sende og modtage data mellem vores Java-applikation og Gemini.

### Det har vi implementeret

- Integreret Gemini API i DriveApp
- Oprettet DrivingAiService
- Arbejdet med Java HttpClient
- Sendt HTTP-requests til Gemini
- Arbejdet med JSON
- Brugt Jackson og ObjectMapper
- Arbejdet med serialization og deserialization
- Oprettet DTO-klasser til Gemini-responses
- Arbejdet med Candidate, Content, Part og GeminiResponse
- Modtaget og behandlet svar fra Gemini
- Oprettet DrivingAiServiceTest
- Testet kommunikationen med det eksterne API

### Resultat

Vi fik implementeret en AI-service, som kunne kommunikere med Gemini API.

DriveApp kunne nu sende spørgsmål til Gemini og behandle de svar, der kom tilbage.

Vi fik dermed erfaring med at integrere eksterne services i vores egen backend.

Senere i projektet har vi arbejdet videre med AI-funktionen og tilføjet tests af adgangen gennem vores REST API.

---

# Week 4 – Concurrency & Booking System

I uge 4 arbejdede vi med concurrency og multithreading i Java.

Vi lærte, hvordan flere threads kan udføre opgaver samtidigt, og hvilke problemer der kan opstå, når flere brugere forsøger at ændre de samme data.

Det var særligt relevant for vores bookingsystem.

Hvis to elever forsøger at booke den samme køretime på samme tidspunkt, skal systemet kunne håndtere situationen korrekt.

### Det har vi implementeret

- Arbejdet med threads i Java
- Lært om Runnable og multithreading
- Arbejdet med ExecutorService
- Undersøgt race conditions
- Arbejdet med synchronized
- Udviklet vores BookingService
- Arbejdet med bookLesson-metoden
- Implementeret kontrol af eksisterende bookinger
- Arbejdet med samtidige bookingforsøg
- Testet situationer, hvor flere elever forsøger at booke samme køretime

### Resultat

Vi arbejdede med at beskytte vores bookingsystem mod problemer med samtidige requests.

Ved hjælp af synchronized kunne vi sikre, at flere threads ikke udførte den beskyttede bookingmetode samtidigt på samme serviceinstans.

Vi lærte samtidig, hvorfor det er vigtigt at kontrollere, om en køretime allerede er booket, før en ny booking bliver oprettet.

Arbejdet gav os en bedre forståelse for concurrency og de udfordringer, der kan opstå i backend-systemer med flere brugere.

---

# Week 5 – REST API, Javalin & Documentation

I uge 5 begyndte vi at gøre vores backend tilgængelig gennem et REST API.

Indtil dette tidspunkt havde vi primært arbejdet med vores database, entities og DAO-klasser.

Nu skulle funktionerne kunne tilgås gennem HTTP-requests.

Vi valgte at bruge Javalin til at udvikle vores REST API.

### Det har vi implementeret

- Tilføjet Javalin til projektet
- Oprettet routes og controllers
- Arbejdet med REST-principper
- Implementeret GET, POST, PUT og DELETE
- Oprettet endpoints til elever
- Oprettet endpoints til kørelærere
- Oprettet endpoints til køretimer
- Oprettet endpoints til bookinger
- Forbundet controllers med vores backend
- Arbejdet med request- og response-DTO'er
- Implementeret validering af requests
- Arbejdet med HTTP-statuskoder
- Implementeret fejlhåndtering
- Dokumenteret vores endpoints i README

### Resultat

Vi fik udviklet et REST API, som gjorde det muligt at kommunikere med vores backend gennem HTTP.

Vi kunne nu arbejde med elever, kørelærere, køretimer og bookinger gennem vores endpoints.

Vi lærte samtidig, hvorfor det er vigtigt at opdele applikationen i forskellige lag.

Controllers håndterer HTTP-requests, mens vores øvrige backend-klasser håndterer forretningslogik og databaseoperationer.

Vi dokumenterede vores API i README, så andre lettere kunne forstå og bruge vores endpoints.

---

# Week 6 – REST Testing & Integration Tests

I uge 6 fokuserede vi på automatiserede tests.

Vi havde allerede arbejdet med tests af vores DAO-lag, men nu skulle vi også teste vores REST API.

Vi brugte REST Assured til at sende HTTP-requests til vores endpoints og kontrollere, at de returnerede de forventede resultater.

### Det har vi implementeret

- Arbejdet med REST Assured
- Brugt JUnit til automatiserede tests
- Arbejdet med Hamcrest
- Testet GET-requests
- Testet POST-requests
- Testet PUT-requests
- Testet DELETE-requests
- Kontrolleret HTTP-statuskoder
- Kontrolleret JSON-responses
- Testet gyldige og ugyldige requests
- Arbejdet med DAO-tests
- Arbejdet med integrationstests
- Brugt Testcontainers til database-tests
- Testet forskellige fejlscenarier
- Arbejdet med tests af vores AI-integration

### Resultat

Vi fik udvidet vores testopsætning, så vi kunne kontrollere flere dele af DriveApp automatisk.

Med REST Assured kunne vi teste vores endpoints uden at skulle sende alle requests manuelt.

Vi arbejdede både med succesfulde requests og fejlscenarier.

Det gjorde det nemmere at opdage problemer og kontrollere, at vores backend fortsat fungerede efter ændringer i koden.

---

# Week 7 – Security, BCrypt & JWT

I uge 7 arbejdede vi med sikkerhed i vores REST API.

Vi fokuserede på authentication og authorization, så vi kunne kontrollere, hvem der bruger systemet, og hvilke funktioner de har adgang til.

Det var vigtigt for DriveApp, fordi elever og kørelærere ikke nødvendigvis skal have adgang til de samme funktioner.

Vi arbejdede også med sikker opbevaring af passwords.

### Det har vi implementeret

- Arbejdet med authentication
- Arbejdet med authorization
- Implementeret BCrypt password hashing
- Arbejdet med sikker håndtering af passwords
- Implementeret login-funktionalitet
- Arbejdet med JSON Web Tokens
- Oprettet JWTToken
- Arbejdet med JWT payload og claims
- Implementeret brugerroller
- Arbejdet med STUDENT og INSTRUCTOR
- Beskyttet endpoints med adgangskontrol
- Arbejdet med security filters
- Testet JWT-funktionalitet
- Arbejdet med BcryptTest
- Arbejdet med JWTTokenTest

### Resultat

Vi fik implementeret et security-lag i DriveApp.

Passwords kunne nu håndteres med BCrypt, så de ikke skulle gemmes direkte som almindelig tekst.

Vi arbejdede samtidig med JWT, som gør det muligt at identificere brugere ved efterfølgende requests.

Ved hjælp af authorization kunne vi begrænse adgangen til bestemte endpoints baseret på brugerens rolle.

Det betyder eksempelvis, at en elev og en kørelærer kan have forskellige rettigheder i systemet.

Vi fik dermed praktisk erfaring med at beskytte et REST API og håndtere brugeradgang.

---

# Week 8 – Deployment & DevOps

I uge 8 arbejdede vi med deployment og DevOps.

Formålet var at gøre DriveApp tilgængelig uden for vores lokale udviklingsmiljø.

Vi arbejdede med Docker og GitHub Actions for at forstå, hvordan en Java-applikation kan bygges, pakkes og køres på en server.

Vi arbejdede også med CI/CD for at automatisere dele af udviklings og deploymentprocessen.

### Det har vi implementeret

- Arbejdet med Docker
- Oprettet Dockerfile
- Arbejdet med Docker Compose
- Arbejdet med Docker images og containers
- Brugt Maven til at bygge applikationen
- Arbejdet med JAR-filer
- Oprettet GitHub Actions workflow
- Arbejdet med CI/CD
- Automatiseret build og tests
- Arbejdet med Docker Hub
- Arbejdet med DigitalOcean
- Konfigureret PostgreSQL til deployment
- Arbejdet med environment variables
- Arbejdet med domæne og HTTPS
- Testet vores deployede REST API

### Deployment

Vores DriveApp API er tilgængeligt på:

[DriveApp – Deployed API](https://driveapp.website)

### Resultat

Vi fik arbejdet med hele processen fra en lokal Java-applikation til en backend, der kan køre på en ekstern server.

Docker gjorde det muligt at pakke vores applikation og dens nødvendige konfiguration i et mere ensartet miljø.

Med GitHub Actions arbejdede vi med at automatisere build, tests og deploymentprocessen.

Det gav os en bedre forståelse for, hvordan backend-applikationer kan sættes i drift og vedligeholdes.

---

# DriveApp – System Features

Ud over de enkelte ugers læringsmål har vi løbende arbejdet på at gøre DriveApp til et mere komplet køreskolesystem.

## Student Management

Systemet indeholder funktioner til administration af elever.

Vi har arbejdet med at oprette, hente, opdatere og slette elevoplysninger gennem vores backend og REST API.

## Instructor Management

Vi har implementeret funktioner til håndtering af kørelærere.

Kørelærere indgår i systemets databasestruktur og kan forbindes til køretimer.

## Lesson & Booking Management

Vi har udviklet funktioner til administration af køretimer og bookinger.

En vigtig del af arbejdet har været at håndtere situationer, hvor flere elever forsøger at booke den samme køretime.

## AI Assistant

Vi har integreret Google Gemini i vores backend gennem DrivingAiService.

AI-assistenten er udviklet med fokus på spørgsmål om køreteori, trafikregler og trafiksikkerhed.

## Authentication & Authorization

Vi har arbejdet med BCrypt, JWT og brugerroller.

Formålet er at beskytte vores API og sikre, at brugere kun får adgang til de funktioner, de har tilladelse til.

## Automated Testing

Vi har arbejdet med automatiserede tests af vores DAO-lag, REST API og forskellige services.

Testene hjælper os med at kontrollere funktionaliteten og opdage fejl under udviklingen.

---

# Project Architecture

DriveApp er udviklet som en Java-backend med en lagdelt struktur.

Vi har opdelt projektet i forskellige klasser og komponenter, som hver har deres eget ansvar.

### Controllers

Controllers modtager HTTP-requests og returnerer responses til klienten.

### Services

Serviceklasserne håndterer projektets forretningslogik.

Eksempelvis arbejder BookingService med bookingfunktionaliteten, mens DrivingAiService håndterer kommunikationen med Gemini.

### DAO

DAO-laget håndterer kommunikationen med databasen gennem JPA og Hibernate.

### Entities

Entities repræsenterer de data, vi gemmer i PostgreSQL.

### DTO

DTO'er bruges til at overføre data mellem forskellige dele af applikationen og til at styre, hvilke oplysninger vores API modtager og returnerer.

Denne opdeling gør projektet mere overskueligt og lettere at vedligeholde.

---

# Samlet resultat

Gennem 3. semester har vi udviklet DriveApp fra et mindre Java-projekt til et backend-system med flere forskellige funktioner.

Vi startede med JPA, Hibernate og PostgreSQL og udvidede derefter projektet med relationer, databasequeries og automatiserede tests.

Senere implementerede vi et REST API med Javalin, så systemets funktioner kunne tilgås gennem HTTP-requests.

Vi integrerede også Google Gemini, arbejdede med concurrency i vores bookingsystem og implementerede sikkerhed med BCrypt og JWT.

Til sidst arbejdede vi med Docker, GitHub Actions og deployment for at gøre vores backend tilgængelig online.

Projektet har givet os erfaring med hele udviklingsprocessen fra database og backend-logik til testing, security og deployment.

DriveApp samler dermed mange af de teknologier og emner, vi har arbejdet med gennem semesteret, i et samlet projekt.