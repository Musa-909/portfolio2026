



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

Formålet med projektet er at gøre det nemmere at administrere elever, kørelærere, køretimer og bookinger gennem et samlet system.

Vi har udviklet projektet i Java med Javalin som REST API-framework, Hibernate/JPA til databasehåndtering og PostgreSQL som database.

Systemet indeholder funktioner til håndtering af elever, kørelærere, køretimer og bookinger. Vi har også integreret Google Gemini som en AI-assistent, der kan hjælpe med spørgsmål om køreteori og trafikregler.

Derudover har vi arbejdet med sikkerhed gennem JWT og BCrypt, automatiserede tests med JUnit, REST Assured og Testcontainers samt deployment med Docker og GitHub Actions.

Denne side dokumenterer udviklingen af DriveApp gennem semesterets otte emner og viser, hvordan vi har anvendt undervisningens teknologier i vores eget projekt.

⸻

Project Links

GitHub Repository:

DriveApp – GitHub

Deployed API:

DriveApp – Deployed API

⸻

Projektudvikling

Kursusemne	Hvordan vi har anvendt det i DriveApp	Undervisningsmateriale
01 JPA Basics	Hibernate/JPA, EntityManager, DAO-klasser og CRUD-operationer med PostgreSQL.	JPA Basics
02 JPA Relations	Relationer mellem Student, Instructor, Lesson og Booking samt JPQL.	JPA Relations
03 Data Integration	JSON, DTO’er, Java HttpClient, Jackson og integration med Google Gemini.	Data Integration
04 Concurrency	CompletableFuture til asynkron AI-kommunikation og arbejde med samtidighed i bookingsystemer.	Concurrency
05 REST API Intro	REST API med Javalin, routes, controllers og HTTP-metoder.	REST API Intro
06 REST & Test	JUnit, REST Assured, Hamcrest og PostgreSQL-integrationstests med Testcontainers.	REST & Test
07 Security	JWT-authentication, BCrypt password hashing og rollebaseret adgangskontrol.	Security
08 Deployment & DevOps	Docker, Docker Hub, GitHub Actions, CI/CD og DigitalOcean.	Deployment & DevOps

⸻

Week 1 – Project Setup, JPA & CRUD

I den første uge begyndte vi udviklingen af DriveApp.

Vi planlagde projektets grundlæggende struktur og oprettede forbindelsen mellem vores Java-applikation og PostgreSQL.

Vi brugte JPA og Hibernate til at håndtere kommunikationen med databasen, så vi kunne arbejde med Java-objekter i stedet for at skrive SQL til alle databaseoperationer.

Det har vi implementeret

* Oprettet Java-projektet med Maven.
* Konfigureret JPA og Hibernate.
* Oprettet forbindelse til PostgreSQL.
* Oprettet vores første entities: Student og Instructor.
* Oprettet DAO-klasser til databaseoperationer.
* Implementeret CRUD-operationer.
* Arbejdet med EntityManager og EntityManagerFactory.
* Konfigureret HibernateConfig.
* Testet databaseforbindelsen.

Resultat

Vi fik etableret projektets grundlæggende backend og databaseforbindelse.

Gennem DAO-laget kunne vi oprette, hente, opdatere og slette oplysninger i databasen.

Senere har vi videreudviklet DAO-klasserne med constructor injection, så de kan modtage en EntityManagerFactory og dermed bruge forskellige databaseforbindelser i udvikling og tests.

⸻

Week 2 – JPA Relations, JPQL & Testing

I uge 2 fortsatte vi med at udvikle databasestrukturen i DriveApp.

Vi arbejdede med relationer mellem vores entities og lærte, hvordan forskellige tabeller kan forbindes gennem JPA.

Det var vigtigt for projektet, fordi elever, kørelærere, køretimer og bookinger hænger sammen.

Eksempelvis skal en køretime kunne forbindes til en kørelærer, og en booking skal kunne forbindes til en elev og en køretime.

Det har vi implementeret

* Arbejdet med JPA-relationer.
* Udvidet vores entities.
* Arbejdet med Student, Instructor, Lesson og Booking.
* Brugt JPA-annoteringer til relationer.
* Arbejdet med foreign keys.
* Udvidet DAO-klasserne.
* Implementeret JPQL-queries.
* Arbejdet med databaseforespørgsler.
* Oprettet automatiserede DAO-tests med JUnit.
* Testet CRUD-operationer og relationer.

Resultat

Vi fik udvidet databasestrukturen, så de forskellige dele af køreskolen kunne forbindes.

Vi lærte samtidig at bruge JPQL til at hente bestemte oplysninger fra databasen.

Senere har vi forbedret vores DAO-tests ved at bruge Testcontainers, så de nu arbejder mod en isoleret PostgreSQL-database.

⸻

Week 3 – Data Integration & Gemini AI

I uge 3 arbejdede vi med dataintegration og kommunikation med eksterne API’er.

Vi valgte at integrere Google Gemini i DriveApp for at tilføje en AI-assistent til køreskolesystemet.

Formålet var at give elever mulighed for at stille spørgsmål om køreteori, trafikregler og trafiksikkerhed.

Vi arbejdede samtidig med JSON og DTO’er for at kunne sende og modtage data mellem vores Java-applikation og Gemini.

Det har vi implementeret

* Integreret Google Gemini API.
* Oprettet DrivingAiService.
* Arbejdet med Java HttpClient.
* Sendt HTTP-requests til Gemini.
* Arbejdet med JSON.
* Brugt Jackson og ObjectMapper.
* Arbejdet med serialization og deserialization.
* Oprettet DTO-klasser til Gemini-responses.
* Arbejdet med Candidate, Content, Part og GeminiResponse.
* Modtaget og behandlet svar fra Gemini.
* Oprettet DrivingAiServiceTest.
* Testet kommunikationen med det eksterne API.

Resultat

Vi fik implementeret en AI-service, som kan kommunikere med Gemini API.

DriveApp kan sende spørgsmål til Gemini og behandle de svar, der kommer tilbage.

Vi har efterfølgende udvidet løsningen, så Application kan modtage en AI-funktion gennem dependency injection.

Det gør det muligt at teste AI-endpointet med et simuleret svar uden at kontakte Gemini.

Vi har derfor to typer AI-tests:

* DrivingAiServiceTest: Tester kommunikationen med den rigtige Gemini API.
* AiApiTest: Tester AI-endpointets adgangskontrol og svarstruktur med en fake AI-service.

⸻

Week 4 – Concurrency & Booking System

I uge 4 arbejdede vi med concurrency og multithreading i Java.

Vi lærte, hvordan flere threads kan udføre opgaver samtidigt, og hvilke problemer der kan opstå, når flere brugere forsøger at ændre de samme data.

Det var særligt relevant for vores bookingsystem.

Hvis to elever forsøger at booke den samme køretime på samme tidspunkt, kan der opstå en race condition.

Det har vi arbejdet med

* Threads og multithreading i Java.
* Runnable og ExecutorService.
* Race conditions.
* Synchronized.
* Bookingfunktionalitet.
* Kontrol af eksisterende bookinger.
* Udfordringer ved samtidige bookingforsøg.
* CompletableFuture til asynkron AI-kommunikation.

Resultat

Vi arbejdede med at forstå og håndtere de problemer, der kan opstå ved samtidige requests.

En vigtig del af bookingfunktionaliteten er at kontrollere, om en køretime allerede er booket, før en ny booking oprettes.

Vi arbejdede også med synchronized og lærte, hvordan det kan forhindre flere threads i at udføre en beskyttet metode samtidigt på samme objekt.

Vi lærte samtidig, at synchronized ikke alene garanterer beskyttelse mod dobbeltbookinger, hvis applikationen kører på flere serverinstanser.

Arbejdet gav os en bedre forståelse for concurrency og betydningen af dataintegritet i backend-systemer.

⸻

Week 5 – REST API, Javalin & Documentation

I uge 5 begyndte vi at gøre vores backend tilgængelig gennem et REST API.

Indtil dette tidspunkt havde vi primært arbejdet med vores database, entities og DAO-klasser.

Nu skulle funktionerne kunne tilgås gennem HTTP-requests.

Vi valgte at bruge Javalin til at udvikle REST API’et.

Det har vi implementeret

* Tilføjet Javalin.
* Oprettet routes og controllers.
* Arbejdet med REST-principper.
* Implementeret GET, POST, PUT og DELETE.
* Oprettet endpoints til elever.
* Oprettet endpoints til kørelærere.
* Oprettet endpoints til køretimer.
* Oprettet endpoints til bookinger.
* Forbundet controllers med DAO-laget.
* Arbejdet med request- og response-DTO’er.
* Implementeret validering af requests.
* Arbejdet med HTTP-statuskoder.
* Implementeret fejlhåndtering.
* Dokumenteret API-endpoints i README.

Resultat

Vi fik udviklet et REST API, som gør det muligt at kommunikere med vores backend gennem HTTP.

Vi opdelte applikationen i forskellige lag:

HTTP Request → Route → Controller → DAO → Hibernate/JPA → PostgreSQL → JSON Response

Routes definerer vores endpoints, controllers håndterer requests, og DAO-laget kommunikerer med databasen.

Vi har senere forbedret Application, så den kan modtage en EntityManagerFactory gennem dependency injection.

Det gør applikationen lettere at teste, fordi vi kan starte den med en separat testdatabase.

⸻

Week 6 – REST Testing & Integration Tests

I uge 6 fokuserede vi på automatiserede tests.

Vi havde allerede arbejdet med tests af DAO-laget, men nu skulle vi også teste REST API’et.

Vi brugte REST Assured til at sende HTTP-requests til vores endpoints og kontrollere, at de returnerede de forventede resultater.

Det har vi implementeret

* Arbejdet med JUnit.
* Brugt REST Assured og Hamcrest.
* Testet GET, POST, PUT og DELETE.
* Kontrolleret HTTP-statuskoder.
* Kontrolleret JSON-responses.
* Testet gyldige og ugyldige requests.
* Testet JWT-beskyttede endpoints.
* Udviklet DAO-tests og API-tests.
* Implementeret PostgreSQL med Testcontainers.
* Oprettet HibernateTestConfig.
* Oprettet DatabaseTest.
* Oprettet ApiTest.
* Implementeret constructor injection i DAO-klasserne.
* Testet AI-endpointet med en fake AI-service.

Fra manuel testopsætning til Testcontainers

Tidligere krævede vores API-tests, at vi manuelt startede Javalin på localhost:7070.

Testene var også afhængige af en eksisterende PostgreSQL-database og testbrugere med bestemte loginoplysninger.

Det gjorde testene mere besværlige at starte og vedligeholde.

Vi forbedrede derfor testopsætningen ved at implementere Testcontainers.

Testcontainers starter automatisk en midlertidig PostgreSQL-database gennem Docker.

Vi oprettede to fælles testklasser:

DatabaseTest

* Starter PostgreSQL med Testcontainers.
* Opretter en EntityManagerFactory til testdatabasen.
* Gør databaseforbindelsen tilgængelig for testklasserne.
* Lukker forbindelsen og stopper containeren efter testene.

ApiTest

* Arver fra DatabaseTest.
* Starter Javalin automatisk.
* Bruger en dynamisk port i stedet for den faste port 7070.
* Konfigurerer REST Assured.
* Stopper serveren efter testene.

Vores API-tests opretter desuden selv de nødvendige testbrugere.

Environment Variables til tests

Efter ændringen kræver vores samlede testpakke kun:

JWT_SECRET=<test-secret>
GEMINI_API_KEY=<gemini-api-key>

JWT_SECRET bruges til tests af authentication og authorization.

GEMINI_API_KEY bruges til DrivingAiServiceTest, som kommunikerer med den rigtige Gemini API.

DAO-tests bruger ingen af disse variabler, mens AiApiTest bruger fake Gemini og derfor ikke kræver en Gemini API-nøgle.

Vi behøver ikke længere de gamle TEST_INSTRUCTOR_EMAIL, TEST_INSTRUCTOR_PASSWORD, TEST_STUDENT_EMAIL og TEST_STUDENT_PASSWORD.

Vi behøver heller ikke databaseoplysninger til Testcontainers-testene.

Resultat

Vi har fået en automatiseret testopsætning, hvor PostgreSQL og Javalin startes direkte fra testklasserne.

Testene er dermed uafhængige af vores eksisterende lokale database og produktionsdatabase.

Vi har kørt DAO-tests, API-tests, JWT-tests, BCrypt-tests og Gemini-servicetests.

Vi har også kørt hele testpakken samlet med succes.

Det har gjort vores testopsætning mere automatiseret og lettere at vedligeholde.

⸻

Week 7 – Security, BCrypt & JWT

I uge 7 arbejdede vi med sikkerhed i vores REST API.

Vi fokuserede på authentication og authorization, så vi kunne kontrollere, hvem der bruger systemet, og hvilke funktioner de har adgang til.

Det var vigtigt for DriveApp, fordi elever og kørelærere ikke nødvendigvis skal have adgang til de samme funktioner.

Vi arbejdede også med sikker opbevaring af passwords.

Det har vi implementeret

* Authentication og authorization.
* BCrypt password hashing.
* Login-funktionalitet.
* JSON Web Tokens.
* JWTToken.
* JWT payload og claims.
* Brugerrollerne STUDENT og INSTRUCTOR.
* Adgangskontrol til beskyttede endpoints.
* Security filters.
* Tests af JWT-funktionalitet.
* BcryptTest og JWTTokenTest.
* API-tests af requests uden JWT og med ugyldige tokens.

Resultat

Vi fik implementeret et security-lag i DriveApp.

Passwords håndteres med BCrypt, så de ikke gemmes direkte som almindelig tekst.

Ved login kan en bruger modtage et JWT-token, som bruges til authentication ved efterfølgende requests.

Med authorization kan vi begrænse adgangen til bestemte funktioner baseret på brugerens rolle.

Vi har også testet, at requests uden gyldigt JWT-token bliver afvist.

Det gav os praktisk erfaring med sikkerhed i REST API’er og forskellen mellem authentication og authorization.

⸻

Week 8 – Deployment & DevOps

I uge 8 arbejdede vi med deployment og DevOps.

Formålet var at gøre DriveApp tilgængelig uden for vores lokale udviklingsmiljø.

Vi arbejdede med Docker og GitHub Actions for at forstå, hvordan en Java-applikation kan bygges, pakkes og køres på en server.

Vi arbejdede også med CI/CD for at automatisere dele af udviklings- og deploymentprocessen.

Det har vi implementeret

* Arbejdet med Docker.
* Oprettet Dockerfile.
* Arbejdet med Docker Compose.
* Arbejdet med Docker images og containers.
* Brugt Maven til at bygge applikationen.
* Arbejdet med JAR-filer.
* Oprettet GitHub Actions-workflow.
* Automatiseret build og tests.
* Integreret Testcontainers i GitHub Actions.
* Arbejdet med Docker Hub.
* Arbejdet med DigitalOcean.
* Konfigureret PostgreSQL til deployment.
* Arbejdet med environment variables.
* Arbejdet med domæne og HTTPS.
* Testet vores deployede REST API.

GitHub Actions

Vi har opdateret vores GitHub Actions-workflow, så det passer til den nye Testcontainers-opsætning.

Tidligere startede workflowet en PostgreSQL-service og Javalin manuelt. Det oprettede også testbrugere direkte i databasen.

Efter ændringen håndterer testklasserne selv opstarten af PostgreSQL og Javalin.

Workflowet udfører nu følgende proces:

1. Henter projektets kode fra GitHub.
2. Opsætter Java og Maven.
3. Kører automatiserede tests med Testcontainers.
4. Bygger applikationens JAR-fil.
5. Bygger et Docker-image.
6. Uploader Docker-imaget til Docker Hub.

Vi bruger GitHub Secrets til at håndtere følsomme oplysninger som JWT_SECRET, GEMINI_API_KEY og Docker Hub-login.

Databaseopsætning

Vi har adskilt vores databaseopsætning mellem udvikling, test og produktion.

Miljø	Databaseforbindelse
Lokal udvikling	config.properties
Automatiske DAO- og API-tests	PostgreSQL med Testcontainers
Produktion	Environment variables

Det betyder, at vores automatiske tests ikke længere behøver at bruge en eksisterende lokal testdatabase.

Deployment

Vores DriveApp API er tilgængeligt på:

DriveApp – Deployed API

Resultat

Vi har arbejdet med processen fra en lokal Java-applikation til en backend, der kan køre på en ekstern server.

Docker gør det muligt at pakke applikationen i et ensartet miljø.

GitHub Actions automatiserer tests, build og upload af Docker-imaget.

Vi har desuden opdateret vores CI/CD-workflow, så testene bruger den samme Testcontainers-opsætning som under lokal udvikling.

Det har givet os en bedre forståelse for automatisering, deployment og vedligeholdelse af backend-applikationer.

⸻

DriveApp – System Features

Ud over de enkelte ugers læringsmål har vi løbende arbejdet på at gøre DriveApp til et mere komplet køreskolesystem.

Student Management

Systemet indeholder funktioner til administration af elever.

Vi kan oprette, hente, opdatere og slette elevoplysninger gennem vores REST API.

Elever kan registrere sig og logge ind.

Instructor Management

Vi har implementeret funktioner til håndtering af kørelærere.

Kørelærere kan forbindes til køretimer gennem vores databasestruktur.

Systemet indeholder desuden adgangskontrol til beskyttede funktioner.

Lesson & Booking Management

Vi har udviklet funktioner til administration af køretimer og bookinger.

Elever kan finde tilgængelige køretimer og oprette bookinger.

Vi har arbejdet med kontrol af eksisterende bookinger for at undgå, at samme køretime bookes flere gange.

AI Assistant

Vi har integreret Google Gemini gennem DrivingAiService.

AI-assistenten er udviklet med fokus på spørgsmål om køreteori, trafikregler og trafiksikkerhed.

Vi tester både den rigtige Gemini-service og AI-endpointet med en fake AI-service.

Authentication & Authorization

Vi bruger BCrypt til password hashing og JWT til authentication.

Systemet arbejder med brugerrollerne STUDENT og INSTRUCTOR.

Adgangskontrol bruges til at beskytte relevante API-endpoints.

Automated Testing

Vi har implementeret automatiserede tests med JUnit, REST Assured og Testcontainers.

DAO- og API-tests bruger en midlertidig PostgreSQL-database.

API-testene starter Javalin automatisk, og testbrugere oprettes direkte i testmiljøet.

Det gør det muligt at teste systemet uden at påvirke produktionsdatabasen.

⸻

Project Architecture

DriveApp er udviklet som en Java-backend med en lagdelt arkitektur.

Vi har opdelt projektet i forskellige klasser og komponenter med hver deres ansvar.

Routes

Routes definerer vores REST API-endpoints og forbinder HTTP-requests med de relevante controllers.

Controllers

Controllers håndterer requests, behandler input og returnerer HTTP-responses.

Services

Serviceklasser bruges til funktionalitet, der har sit eget ansvar.

Eksempelvis håndterer DrivingAiService kommunikationen med Google Gemini.

DAO

DAO-laget håndterer databaseoperationer gennem JPA og Hibernate.

Vi bruger constructor injection med EntityManagerFactory, så vores DAO-klasser kan arbejde med forskellige databaseforbindelser.

Entities

Entities repræsenterer de data, vi gemmer i PostgreSQL.

De vigtigste entities er:

* Student
* Instructor
* Lesson
* Booking

DTO

DTO’er bruges til at overføre data mellem forskellige dele af applikationen og til at styre, hvilke oplysninger vores API modtager og returnerer.

Dependency Injection

Vi har implementeret dependency injection i vores DAO-klasser og Application.

Det betyder, at databaseforbindelsen kan sendes ind i klasserne udefra.

Vi kan derfor bruge den normale Hibernate-konfiguration i applikationen og Testcontainers i vores tests.

Vi har også gjort det muligt at injicere en fake AI-funktion til AI API-tests.

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

Denne opdeling gør projektet mere overskueligt, lettere at teste og lettere at vedligeholde.

⸻

Samlet resultat

Gennem 3. semester har vi udviklet DriveApp fra et mindre Java-projekt til et backend-system med flere forskellige funktioner.

Vi startede med JPA, Hibernate og PostgreSQL og udvidede derefter projektet med relationer, databasequeries og automatiserede tests.

Senere implementerede vi et REST API med Javalin, så systemets funktioner kunne tilgås gennem HTTP-requests.

Vi integrerede også Google Gemini, arbejdede med concurrency i vores bookingsystem og implementerede sikkerhed med BCrypt og JWT.

Til sidst arbejdede vi med Docker, GitHub Actions og deployment for at gøre vores backend tilgængelig online.

En vigtig forbedring af projektet har været implementeringen af Testcontainers.

Vi gik fra en manuel testopsætning med en eksisterende PostgreSQL-database og Javalin på localhost til automatiserede integrationstests, som selv starter deres database og API-server.

Vi har også arbejdet med dependency injection, så vores kode lettere kan testes med forskellige databaseforbindelser og en simuleret AI-service.

Projektet har dermed givet os erfaring med hele udviklingsprocessen fra database og backend-logik til REST API, testing, security og deployment.

DriveApp samler semesterets centrale backend-teknologier i ét projekt og viser, hvordan vi har udviklet og forbedret systemet gennem undervisningsforløbet.