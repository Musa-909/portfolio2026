⸻

title: “Exam Portfolio”
date: 2026-10-29
draft: false
showDate: false
showReadingTime: false
showWordCount: false
showAuthor: false

Driving School Management System – DriveApp

DriveApp er vores semesterprojekt, hvor vi har udviklet et backend-system til administration af en køreskole.

Formålet er at gøre det nemmere at administrere elever, kørelærere, køretimer og bookinger gennem et samlet system.

Vi har udviklet projektet i Java med Javalin, Hibernate/JPA og PostgreSQL. Systemet indeholder desuden en AI-assistent baseret på Google Gemini.

Gennem semesteret har vi arbejdet med REST API, databasehåndtering, concurrency, sikkerhed, automatiserede tests og deployment.

Denne side dokumenterer udviklingen af DriveApp gennem semesterets otte emner.

⸻

Project Links

GitHub Repository:
DriveApp – GitHub

Deployed API:
DriveApp – Deployed API

⸻

Projektudvikling

Kursusemne	Hvordan vi har anvendt det	Undervisningsmateriale
01 JPA Basics	Hibernate/JPA, DAO og CRUD med PostgreSQL.	JPA Basics
02 JPA Relations	Relationer mellem Student, Instructor, Lesson og Booking samt JPQL.	JPA Relations
03 Data Integration	JSON, DTO’er, HttpClient og Google Gemini API.	Data Integration
04 Concurrency	CompletableFuture, multithreading og samtidige bookingforsøg.	Concurrency
05 REST API Intro	REST API med Javalin, routes og controllers.	REST API Intro
06 REST & Test	JUnit, REST Assured og Testcontainers.	REST & Test
07 Security	JWT, BCrypt og rollebaseret adgangskontrol.	Security
08 Deployment & DevOps	Docker, GitHub Actions, Docker Hub og DigitalOcean.	Deployment & DevOps

⸻

Week 1 – Project Setup, JPA & CRUD

I uge 1 begyndte vi udviklingen af DriveApp og oprettede projektets grundlæggende struktur.

Vi brugte Hibernate og JPA til at kommunikere med PostgreSQL gennem Java-objekter.

Det har vi implementeret

* Oprettet Java-projekt med Maven.
* Konfigureret PostgreSQL og Hibernate.
* Oprettet Student og Instructor entities.
* Implementeret DAO-klasser.
* Arbejdet med EntityManager og CRUD.
* Konfigureret HibernateConfig.

Resultat

Vi fik etableret projektets backend og databaseforbindelse.

Gennem DAO-laget kunne vi oprette, hente, opdatere og slette data.

Senere udvidede vi DAO-klasserne med constructor injection, så de også kunne bruges med Testcontainers.

⸻

Week 2 – JPA Relations, JPQL & Testing

I uge 2 arbejdede vi med relationer mellem vores entities.

Vi udvidede databasestrukturen, så elever, kørelærere, køretimer og bookinger kunne forbindes.

Det har vi implementeret

* Oprettet Student, Instructor, Lesson og Booking.
* Arbejdet med @ManyToOne og @OneToMany.
* Implementeret foreign keys.
* Arbejdet med JPQL-queries.
* Udvidet vores DAO-klasser.
* Oprettet DAO-tests med JUnit.

Resultat

Vi lærte, hvordan Hibernate håndterer relationer mellem Java-objekter og databasetabeller.

Vi kunne samtidig teste vores CRUD-operationer og databaseforespørgsler.

⸻

Week 3 – Data Integration & Gemini AI

I uge 3 arbejdede vi med kommunikation mellem vores backend og eksterne API’er.

Vi integrerede Google Gemini for at give elever mulighed for at stille spørgsmål om køreteori og trafikregler.

Det har vi implementeret

* Oprettet DrivingAiService.
* Integreret Google Gemini API.
* Arbejdet med Java HttpClient.
* Brugt JSON og Jackson ObjectMapper.
* Oprettet DTO’er til Gemini-responses.
* Arbejdet med serialization og deserialization.
* Oprettet DrivingAiServiceTest.

Resultat

Vi fik implementeret en AI-assistent, som kan sende spørgsmål til Gemini og behandle svarene.

Senere tilføjede vi dependency injection, så AI-endpointet også kan testes med et simuleret svar.

Vi tester derfor AI på to måder:

* DrivingAiServiceTest: Bruger den rigtige Gemini API.
* AiApiTest: Bruger fake Gemini uden eksterne API-kald.

⸻

Week 4 – Concurrency & Booking System

I uge 4 arbejdede vi med concurrency og multithreading.

Det var relevant for vores bookingsystem, fordi flere elever kan forsøge at booke den samme køretime.

Det har vi arbejdet med

* Threads og Runnable.
* ExecutorService.
* Race conditions.
* Synchronized.
* Bookingfunktionalitet.
* Kontrol af eksisterende bookinger.
* CompletableFuture til asynkron AI-kommunikation.

Resultat

Vi lærte om udfordringer ved samtidige requests og betydningen af at kontrollere eksisterende bookinger.

Vi arbejdede med synchronized og undersøgte, hvordan det kan beskytte en metode mod samtidig udførelse på samme objekt.

Vi lærte samtidig, at beskyttelse på tværs af flere serverinstanser kræver yderligere mekanismer.

⸻

Week 5 – REST API, Javalin & Documentation

I uge 5 udviklede vi vores REST API med Javalin.

Det gjorde det muligt at kommunikere med DriveApp gennem HTTP-requests.

Det har vi implementeret

* Oprettet routes og controllers.
* Implementeret GET, POST, PUT og DELETE.
* Oprettet endpoints til elever og kørelærere.
* Oprettet endpoints til køretimer og bookinger.
* Arbejdet med DTO’er og JSON.
* Implementeret validering og fejlhåndtering.
* Arbejdet med HTTP-statuskoder.
* Dokumenteret API’et i README.

Resultat

Vi fik opbygget en lagdelt backendarkitektur:

HTTP Request → Route → Controller → DAO → Hibernate/JPA → PostgreSQL

Denne struktur adskiller håndteringen af HTTP-requests fra databaseoperationerne.

Senere opdaterede vi Application, så den kan modtage en EntityManagerFactory gennem dependency injection.

⸻

Week 6 – REST Testing & Testcontainers

I uge 6 fokuserede vi på automatiserede tests med JUnit, REST Assured og Hamcrest.

Vi testede vores API-endpoints, HTTP-statuskoder og JSON-responses.

Det har vi implementeret

* DAO-tests med JUnit.
* API-tests med REST Assured.
* Tests af GET, POST, PUT og DELETE.
* Tests af gyldige og ugyldige requests.
* PostgreSQL-integrationstests med Testcontainers.
* Oprettet HibernateTestConfig.
* Oprettet DatabaseTest og ApiTest.
* Implementeret constructor injection i DAO-klasserne.
* Fake Gemini til AI API-tests.

Fra manuel testopsætning til Testcontainers

Tidligere skulle vi starte Javalin manuelt på localhost:7070 og bruge en eksisterende PostgreSQL-database med bestemte testbrugere.

Vi forbedrede derfor vores testopsætning med Testcontainers.

Nu starter vores tests automatisk en midlertidig PostgreSQL-database gennem Docker.

DatabaseTest håndterer databasen og EntityManagerFactory.

ApiTest starter Javalin automatisk på en ledig port og konfigurerer REST Assured.

Testene opretter også selv de nødvendige testbrugere.

Environment Variables

Til samlet testkørsel bruger vi:

JWT_SECRET=<test-secret>
GEMINI_API_KEY=<gemini-api-key>

JWT_SECRET bruges til authentication og authorization.

GEMINI_API_KEY bruges til de tests, der kontakter den rigtige Gemini API.

Vi behøver ikke længere de gamle TEST_INSTRUCTOR_EMAIL, TEST_INSTRUCTOR_PASSWORD, TEST_STUDENT_EMAIL og TEST_STUDENT_PASSWORD til vores automatiske tests.

Resultat

Vi har nu automatiserede DAO- og API-tests, som ikke er afhængige af vores eksisterende database.

Vi har kørt hele testpakken samlet med succes.

Det har gjort testene lettere at starte og mere isolerede.

⸻

Week 7 – Security, BCrypt & JWT

I uge 7 arbejdede vi med sikkerhed i vores REST API.

Vi implementerede authentication og authorization for at kontrollere brugeradgang.

Det har vi implementeret

* BCrypt password hashing.
* Login for elever og kørelærere.
* JWT authentication.
* JWT claims og brugerroller.
* STUDENT og INSTRUCTOR.
* Security filters.
* Beskyttelse af API-endpoints.
* BcryptTest og JWTTokenTest.
* API-tests af ugyldige og manglende tokens.

Resultat

Passwords håndteres med BCrypt, så de ikke gemmes som almindelig tekst.

Ved login modtager brugeren et JWT-token, som bruges ved efterfølgende requests.

Vi bruger samtidig roller til at begrænse adgangen til bestemte funktioner.

⸻

Week 8 – Deployment & DevOps

I uge 8 arbejdede vi med deployment og CI/CD.

Formålet var at gøre DriveApp tilgængelig uden for vores lokale udviklingsmiljø.

Det har vi implementeret

* Dockerfile og Docker Compose.
* Docker images og containers.
* Maven-build og JAR-filer.
* GitHub Actions.
* Automatiserede tests med Testcontainers.
* Docker Hub.
* DigitalOcean.
* Environment variables og GitHub Secrets.
* Domæne og HTTPS.

GitHub Actions

Vi opdaterede vores workflow, så det passer til Testcontainers.

Tidligere startede workflowet PostgreSQL og Javalin manuelt og oprettede testbrugere direkte i databasen.

Nu håndteres dette automatisk af testklasserne.

Workflowet:

1. Henter koden fra GitHub.
2. Opsætter Java og Maven.
3. Kører automatiserede tests.
4. Bygger applikationens JAR-fil.
5. Bygger et Docker-image.
6. Uploader imaget til Docker Hub.

Databaseopsætning

Miljø	Database
Lokal udvikling	config.properties
Automatiske tests	Testcontainers
Produktion	Environment variables

Deployment

Vores API er tilgængeligt på:

DriveApp – Deployed API

Resultat

Vi fik erfaring med Docker, automatiserede builds, tests og deployment.

Vi har samtidig forbedret vores CI/CD-proces ved at integrere Testcontainers i GitHub Actions.

⸻

DriveApp – System Features

Student Management

Vi har implementeret CRUD-operationer til administration af elever samt registrering og login.

Instructor Management

Systemet understøtter administration af kørelærere, som kan forbindes til køretimer.

Lesson & Booking Management

Vi har implementeret funktioner til administration af køretimer og bookinger.

Elever kan finde tilgængelige køretimer og oprette bookinger.

AI Assistant

Vi har integreret Google Gemini gennem DrivingAiService.

AI-assistenten fokuserer på køreteori, trafikregler og trafiksikkerhed.

Authentication & Authorization

Vi bruger BCrypt, JWT og rollerne STUDENT og INSTRUCTOR til at beskytte vores API.

Automated Testing

Vi tester vores DAO-lag, API-endpoints og services med JUnit, REST Assured og Testcontainers.

⸻

Project Architecture

DriveApp er udviklet som en Java-backend med en lagdelt arkitektur.

Routes

Definerer vores REST API-endpoints.

Controllers

Håndterer HTTP-requests og returnerer responses.

Services

Håndterer selvstændig funktionalitet som kommunikationen med Gemini.

DAO

Håndterer databaseoperationer gennem JPA og Hibernate.

Entities

Repræsenterer Student, Instructor, Lesson og Booking i databasen.

DTO

Bruges til at overføre data mellem applikationen og klienten.

Dependency Injection

Vi bruger constructor injection med EntityManagerFactory, så DAO-klasserne kan arbejde med forskellige databaseforbindelser.

Application understøtter desuden injection af en fake AI-funktion til tests.

Architecture Flow

HTTP Request
      ↓
Javalin Routes
      ↓
Controller
      ↓
DAO
      ↓
Hibernate / JPA
      ↓
PostgreSQL
      ↓
JSON Response

⸻

Samlet resultat

Gennem 3. semester har vi udviklet DriveApp fra et mindre Java-projekt til et backend-system med REST API, databasehåndtering, AI-integration og sikkerhed.

Vi har arbejdet med Hibernate, JPA, PostgreSQL, Javalin, Gemini, JWT og BCrypt.

En vigtig forbedring har været implementeringen af Testcontainers, hvor vi gik fra manuel testopsætning til automatiserede integrationstests.

Vi har også arbejdet med dependency injection og opdateret GitHub Actions, så vores tests automatisk køres inden Docker-build og upload.

DriveApp har dermed givet os praktisk erfaring med hele backendprocessen fra database og API til testing, security og deployment.