---
title: "Exam Portfolio"
date: 2026-10-27
draft: false
showDate: false
showReadingTime: false
showWordCount: false
showAuthor: false
---

# DriveApp – Driving School Management System

DriveApp er vores backendprojekt fra 3. semester, som jeg har udviklet sammen med Amaan.

Vi ville bygge et system til en køreskole, hvor man kan administrere elever, kørelærere, køretimer og bookinger samlet. Projektet er udviklet i Java med Javalin, Hibernate/JPA og PostgreSQL.

Vi har arbejdet videre på DriveApp gennem hele semesteret. Hver gang vi lærte et nyt emne i undervisningen, forsøgte vi at bruge det til at udbygge eller forbedre vores backend.

Vi begyndte med databasen og JPA, hvorefter vi udviklede REST API-endpoints. Senere integrerede vi Google Gemini som AI-assistent, implementerede sikkerhed med JWT og BCrypt og tilføjede automatiserede tests.

Til sidst arbejdede vi med Docker, GitHub Actions og deployment på DigitalOcean, så vores API kunne tilgås online.

På denne side gennemgår jeg projektets udvikling uge for uge. Jeg beskriver både, hvordan vi brugte teknologierne i DriveApp, og hvad jeg selv fik ud af arbejdet.

## Projektlinks

**GitHub Repository**

[DriveApp – kildekode](https://github.com/Musa-909/DriveApp)

**Deployed Application**

[DriveApp API](https://driveapp.website)

**API Health Check**

[Kontroller om DriveApp kører](https://driveapp.website/api/health)

---

## Projektudvikling

Vi udviklede DriveApp gradvist i takt med undervisningen. Vi startede med at få styr på databasen og vores Java-klasser og byggede derefter videre med API, testing, sikkerhed og deployment.

Tabellen giver et overblik over de otte emner, og hvordan vi anvendte dem i vores fælles projekt.

| Uge | Emne | Hvordan vi brugte det i DriveApp |
|---|---|---|
| **Uge 1** | [JPA Basics](https://3sem.kursusmaterialer.dk/backend/jpa-basics/) | Vi satte databasen op med Hibernate, JPA og PostgreSQL og oprettede de første entities og DAO-klasser. |
| **Uge 2** | [JPA Relations](https://3sem.kursusmaterialer.dk/backend/jpa-relations/) | Vi oprettede relationer mellem Student, Instructor, Lesson og Booking og arbejdede med JPQL. |
| **Uge 3** | [Data Integration](https://3sem.kursusmaterialer.dk/backend/data-integration/) | Vi integrerede Google Gemini med Java HttpClient, JSON og DTO'er for at udvikle en AI-assistent. |
| **Uge 4** | [Concurrency](https://3sem.kursusmaterialer.dk/backend/concurrency/) | Vi lærte om threads, race conditions og synchronized og brugte CompletableFuture til asynkrone requests til Gemini. |
| **Uge 5** | [REST API](https://3sem.kursusmaterialer.dk/backend/rest-intro/) | Vi byggede routes, controllers og endpoints i Javalin til elever, kørelærere, køretimer og bookinger. |
| **Uge 6** | [REST Testing](https://3sem.kursusmaterialer.dk/backend/rest-test/) | Vi brugte JUnit, REST Assured og Testcontainers til at teste vores API og databaseoperationer. |
| **Uge 7** | [Security](https://3sem.kursusmaterialer.dk/backend/security/) | Vi implementerede BCrypt, JWT-login og rollebaseret adgangskontrol. |
| **Uge 8** | [Deployment & DevOps](https://3sem.kursusmaterialer.dk/backend/deployment/) | Vi anvendte Docker, GitHub Actions og DigitalOcean og brugte DanDomain til at forbinde vores domæne. |

I de følgende afsnit beskriver jeg hver uge mere detaljeret og forklarer, hvad vi lavede, hvad jeg lærte, og hvordan projektet udviklede sig.

---

## Udvalgte blogindlæg

Jeg har også skrevet blogindlæg gennem semesteret, hvor jeg dokumenterer undervisningens emner og mine erfaringer. Blogindlæggene viser min løbende læring, mens denne side fokuserer på, hvordan vi konkret anvendte emnerne i DriveApp.

**Ugentlige blogindlæg**

- [Week 1 – JPA Basics](/posts/)
- [Week 2 – JPA Relations](/posts/)
- [Week 3 – Data Integration](/posts/)
- [Week 4 – Concurrency](/posts/)
- [Week 5 – REST API](/posts/)
- [Week 6 – REST Testing](/posts/)
- [Week 7 – Security](/posts/)
- [Week 8 – Deployment](/posts/)

---

# Week 1 – JPA Basics

I den første uge begyndte vi på DriveApp med fokus på projektets backend og database. Vi satte et Java-projekt op med Maven og arbejdede med Hibernate/JPA og PostgreSQL. Samtidig oprettede vi vores første entities og DAO-klasser, så vi kunne begynde at håndtere data.

### Det arbejdede vi med

- Oprettede Java-projektet med Maven
- Forbandt applikationen med PostgreSQL
- Konfigurerede Hibernate og JPA
- Oprettede entities for Student og Instructor
- Arbejdede med DAO-klasser og CRUD-operationer
- Brugte EntityManager til databasekommunikation

### Hvad jeg lærte

Jeg fik en bedre forståelse for, hvordan Hibernate og JPA bruges sammen med PostgreSQL. Det blev mere konkret for mig, hvordan en Java-entity kan repræsentere en tabel i databasen, og hvordan vi kan gemme og hente objekter uden at skrive SQL til hver enkelt operation.

Jeg lærte også, hvorfor DAO-klasser er nyttige. Når databaseoperationerne ligger i deres eget lag, bliver det lettere at holde styr på ansvarsfordelingen i projektet og arbejde videre på koden senere.

### Resultat

Ved ugens afslutning havde vi den grundlæggende databaseopsætning klar. Vi kunne udføre operationer gennem DAO-klasserne og havde dermed et fundament, som resten af DriveApp kunne bygges ovenpå.

---

# Week 2 – JPA Relations

I uge 2 fortsatte vi med databasen og fokuserede på relationerne mellem vores entities. Vi arbejdede med Student, Instructor, Lesson og Booking og forbandt dem ved hjælp af JPA.

Det var vigtigt i et køreskolesystem, fordi en elev skal kunne knyttes til sine bookinger, og en køretime skal kunne forbindes med en kørelærer.

### Det arbejdede vi med

- Oprettede relationer mellem vores entities
- Arbejdede med `@OneToMany` og `@ManyToOne`
- Forbandt elever, kørelærere, køretimer og bookinger
- Brugte foreign keys mellem databasetabeller
- Arbejdede med JPQL-forespørgsler
- Opdaterede vores DAO-klasser
- Skrev JUnit-tests til CRUD og relationer

### Hvad jeg lærte

Jeg lærte, hvordan JPA-relationer fungerer, og hvorfor det er vigtigt at modellere forbindelserne mellem data korrekt. Det gjorde det nemmere at forstå, hvordan de forskellige dele af DriveApp hænger sammen.

Jeg fik også erfaring med JPQL, som gør det muligt at hente bestemte oplysninger gennem vores Java-entities. Derudover gav arbejdet med JUnit mig en bedre forståelse for, hvordan vi kan kontrollere, at databaseoperationer og relationer fungerer som forventet.

### Resultat

Vi fik etableret forbindelserne mellem de centrale entities. Elever kunne knyttes til bookinger, og kørelærere kunne knyttes til køretimer. Det gjorde datamodellen mere anvendelig og gav os et bedre udgangspunkt for det bookingsystem, vi senere arbejdede videre med.

---

# Week 3 – Data Integration & Gemini AI

I uge 3 arbejdede vi med integration af eksterne services. Vi valgte at bruge Google Gemini i DriveApp, fordi vi gerne ville tilføje en AI-assistent, som elever kunne stille spørgsmål til om køreteori, trafikregler og trafiksikkerhed.

Vi brugte Java HttpClient til at kommunikere med Gemini API og JSON til at sende og modtage data.

### Det arbejdede vi med

- Integrerede Google Gemini i DriveApp
- Oprettede klassen `DrivingAiService`
- Brugte Java HttpClient til HTTP-requests
- Arbejdede med JSON og Jackson ObjectMapper
- Oprettede DTO-klasser til svarene fra Gemini
- Arbejdede med serialization og deserialization
- Lavede tests af vores AI-service

### Hvad jeg lærte

Jeg lærte, hvordan vores egen Java-applikation kan kommunikere med et eksternt API. Det gav mig en bedre forståelse for, hvordan en HTTP-request bygges op, og hvordan svaret kan behandles i vores backend.

Jeg fik også mere erfaring med JSON og Jackson. Det var især nyttigt at se, hvordan vi kunne konvertere JSON-data til Java-objekter og bruge DTO'er til at strukturere oplysningerne fra Gemini.

### Resultat

Vi fik en fungerende integration med Google Gemini. DriveApp kunne sende et spørgsmål til Gemini og modtage et svar, som vores backend kunne behandle. AI-assistenten blev dermed en ekstra funktion i køreskolesystemet og gav os praktisk erfaring med data integration.

---

# Week 4 – Concurrency & Booking System

I uge 4 havde vi concurrency og multithreading. Vi lærte, hvordan flere threads kan arbejde samtidigt, og hvilke problemer der kan opstå, når flere brugere forsøger at ændre de samme oplysninger.

Det passede godt til DriveApp, fordi to elever i princippet kan forsøge at booke den samme køretime. Vi arbejdede også med `CompletableFuture` i vores Gemini-integration for at håndtere HTTP-requests asynkront.

### Det arbejdede vi med

- Arbejdede med threads og multithreading i Java
- Brugte Runnable og ExecutorService
- Undersøgte race conditions
- Arbejdede med `synchronized`
- Implementerede bookinglogik i `BookingController` og `BookingDAOImpl`
- Tilføjede kontrol af, om en køretime allerede var booket
- Brugte `CompletableFuture` i `DrivingAiService`
- Testede forskellige situationer med bookinger

### Hvad jeg lærte

Jeg fik en bedre forståelse for, hvorfor concurrency er relevant i en backend, hvor flere requests kan blive behandlet samtidigt. Race conditions viste mig, at det ikke altid er nok, at en metode virker korrekt, når kun én bruger anvender den.

Jeg lærte, hvordan `synchronized` kan bruges til at beskytte en kritisk sektion, så flere threads ikke udfører den samtidigt på samme objekt. Samtidig lærte jeg, hvordan `CompletableFuture` kan bruges til asynkrone operationer, eksempelvis når vores backend venter på et svar fra Google Gemini.

### Resultat

Vi forbedrede bookinglogikken, så systemet kontrollerer, om en køretime allerede er booket, før der oprettes en ny booking. Vi arbejdede samtidig med concurrency og fik større forståelse for, hvordan samtidige requests kan påvirke et backend-system.

---

# Week 5 – REST API & Javalin

I uge 5 begyndte vi at gøre DriveApp tilgængelig gennem et REST API. Indtil da havde vi især arbejdet med databasen, entities og DAO-klasser. Nu skulle man kunne kommunikere med systemet gennem HTTP-requests.

Vi valgte Javalin og byggede routes og controllers, som blev forbundet med vores DAO-lag.

### Det arbejdede vi med

- Tilføjede Javalin til projektet
- Oprettede routes og controllers
- Arbejdede med GET, POST, PUT og DELETE
- Lavede endpoints til elever, kørelærere, køretimer og bookinger
- Forbandt controllers med DAO-laget
- Brugte DTO'er til request- og response-data
- Tilføjede validering af indgående requests
- Arbejdede med HTTP-statuskoder
- Tilføjede fejlhåndtering og logging
- Dokumenterede API-endpoints i README

### Hvad jeg lærte

Jeg lærte, hvordan REST API'er fungerer, og hvordan HTTP-metoder bruges til at arbejde med ressourcer i en backend. Det blev tydeligere for mig, hvad forskellen er på routes, controllers og DAO-klasser.

Routes angiver, hvilke endpoints der findes, controllers håndterer requests, og DAO-klasserne står for databaseoperationerne. Jeg fik også en bedre forståelse for DTO'er og for, hvorfor vi skal styre, hvilke data vores API modtager og sender tilbage.

### Resultat

Vi havde nu et REST API bygget med Javalin. Gennem HTTP-requests kunne vi arbejde med elever, kørelærere, køretimer og bookinger. Det var et vigtigt skridt, fordi DriveApp nu kunne bruges gennem API-endpoints og ikke kun gennem kode, der talte direkte med databasen.

---

# Week 6 – REST Testing & Integration Tests

I uge 6 fokuserede vi på at teste DriveApp automatisk. Vi havde tidligere arbejdet med DAO-tests, men ville nu også sikre, at vores REST API reagerede korrekt på forskellige requests.

Vi brugte JUnit og REST Assured til at sende requests og kontrollere både statuskoder og JSON-responses. Et vigtigt fokus var desuden at holde testdata adskilt fra vores produktionsdatabase.

### Det arbejdede vi med

- Skrev automatiserede tests med JUnit
- Brugte REST Assured til vores API-endpoints
- Testede GET, POST, PUT og DELETE
- Kontrollerede HTTP-statuskoder og JSON-responses
- Testede både gyldige og ugyldige requests
- Lavede tests til elever, kørelærere, køretimer og bookinger
- Arbejdede med Testcontainers og PostgreSQL
- Brugte Testcontainers til midlertidige PostgreSQL 16-databaser
- Oprettede fælles `DatabaseTest`- og `ApiTest`-klasser
- Lod testopsætningen starte database og Javalin-server automatisk
- Sørgede for, at tests ikke ændrede produktionsdata
- Brugte testdata frem for at oprette testbrugere i produktion
- Testede DAO-klasser og databaseoperationer
- Lavede tests til Gemini-integrationen
- Arbejdede med fejlscenarier og fejlhåndtering

### Hvad jeg lærte

Jeg lærte, hvor stor en forskel automatiserede tests kan gøre, når et backendprojekt vokser. Med REST Assured kunne jeg teste endpoints systematisk i stedet for at skulle udføre hver request manuelt.

Testcontainers var et af de vigtigste emner for mig denne uge. I begyndelsen brugte vi en separat lokal PostgreSQL-testdatabase. Senere forbedrede vi opsætningen, så Testcontainers automatisk opretter en midlertidig PostgreSQL-database, når testene køres.

Vi arbejdede også med at lade vores API-tests starte Javalin automatisk på en ledig port og oprette de testbrugere, de har brug for. Det gjorde det tydeligt for mig, hvorfor et godt testmiljø skal kunne starte uden en masse manuel opsætning.

Det var samtidig vigtigt, at tests ikke påvirkede de rigtige elever og bookinger i produktionsdatabasen. Jeg fik derfor en bedre forståelse for forskellen på et testmiljø og et produktionsmiljø.

### Resultat

Vi fik en mere selvstændig testopsætning med Testcontainers og midlertidige PostgreSQL-databaser. Vores API-tests kan starte Javalin på en tilgængelig port og oprette egne testdata uden en manuelt konfigureret testdatabase.

Det gjorde testene lettere at køre lokalt og i GitHub Actions. Samtidig blev risikoen for at påvirke produktionsdata reduceret, og vi fik bedre mulighed for at opdage fejl efter ændringer i koden.

---

# Week 7 – Security, BCrypt & JWT

I uge 7 arbejdede vi med at sikre vores REST API. Vi ville gøre det muligt for både elever og kørelærere at logge ind og samtidig begrænse, hvilke oplysninger og funktioner den enkelte bruger kan tilgå.

Vi brugte BCrypt til passwords og JWT til authentication.

### Det arbejdede vi med

- Implementerede BCrypt til hashing af passwords
- Lavede login for elever og kørelærere
- Arbejdede med authentication og authorization
- Implementerede JWT-tokens til indloggede brugere
- Oprettede klassen `JWTToken`
- Tilføjede security filters til beskyttede endpoints
- Arbejdede med rollerne `STUDENT` og `INSTRUCTOR`
- Implementerede rollebaseret adgangskontrol
- Tilføjede kontrol af, at elever kun kan tilgå deres egne oplysninger
- Oprettede tests til BCrypt og JWT

### Hvad jeg lærte

Jeg lærte forskellen mellem authentication og authorization. Authentication handler om at kontrollere, hvem brugeren er, mens authorization handler om, hvilke handlinger brugeren har tilladelse til at udføre.

Jeg lærte også, hvorfor passwords ikke må gemmes som almindelig tekst. BCrypt gør det muligt at gemme en hash i databasen i stedet for selve passwordet.

Arbejdet med JWT gav mig en bedre forståelse for, hvordan en bruger kan logge ind, modtage et token og derefter bruge tokenet ved requests til beskyttede endpoints.

### Resultat

Vi fik implementeret sikkerhed med BCrypt, JWT og brugerroller. Elever og kørelærere kunne logge ind, og vores backend kunne kontrollere brugerens rettigheder, inden et beskyttet endpoint blev tilgået.

Det var nødvendigt for at beskytte brugeroplysninger og sikre, at forskellige brugere ikke automatisk har adgang til de samme funktioner.

---

# Week 8 – Deployment & DevOps

I uge 8 arbejdede vi med at få DriveApp online. Hidtil havde vi hovedsageligt kørt vores backend lokalt, men målet var at gøre REST API'et tilgængeligt via internettet.

Vi fulgte deploymentguiden fra undervisningsmaterialet og arbejdede med Docker, GitHub Actions, DigitalOcean og DanDomain.

### Det arbejdede vi med

- Oprettede en Dockerfile til Java-applikationen
- Arbejdede med Docker images og containers
- Brugte Docker Compose til applikation og database
- Oprettede et GitHub Actions-workflow
- Arbejdede med CI/CD til automatiseret build og testing
- Brugte Docker Hub til Docker images
- Fulgte kursets deploymentguide
- Deployede DriveApp på en DigitalOcean-server
- Konfigurerede PostgreSQL til den deployede applikation
- Arbejdede med environment variables
- Brugte DanDomain til domæne- og DNS-indstillinger
- Forbandt domænet med DigitalOcean-serveren
- Opsatte HTTPS til vores API
- Testede det deployede REST API

### Hvad jeg lærte

Jeg lærte, hvordan en backend kan flyttes fra min lokale computer til en server, hvor andre kan tilgå den. Docker gjorde det nemmere at forstå, hvordan applikationen kan pakkes i en container og køres i forskellige miljøer.

GitHub Actions gav mig erfaring med CI/CD og med at automatisere build og tests, når vi pusher ændringer til GitHub. Jeg fik også en bedre forståelse for, hvordan DigitalOcean og DanDomain bruges sammen, og hvordan DNS-indstillinger forbinder et domæne med en server.

Det var en stor forskel at se vores API fungere online frem for kun på localhost.

### Resultat

Vi fik deployet DriveApp på DigitalOcean, og vores REST API blev tilgængeligt via vores domæne:

[DriveApp API](https://driveapp.website)

Vi havde også et GitHub Actions-workflow til at understøtte automatiseret build og testing. Det betød, at vi havde været igennem hele processen fra lokal udvikling til en backend, der kan tilgås online.

---

# Projektarkitektur og tekniske valg

Vi har arbejdet med en lagdelt arkitektur i DriveApp, så koden bliver mere overskuelig og nemmere at vedligeholde. Projektet er opdelt i routes, controllers, DAO-klasser og services, der hver har deres ansvar.

## REST API og database

Vi brugte Javalin til at oprette vores REST API og håndtere HTTP-requests til elever, kørelærere, køretimer og bookinger.

Hibernate/JPA og PostgreSQL bruges til at gemme data. DAO-klasserne håndterer databaseoperationerne, mens DTO'er hjælper os med at styre, hvilke oplysninger der modtages og returneres gennem API'et.

Denne opdeling gjorde koden lettere at forstå og hjalp os med at undgå at sende følsomme oplysninger som passwords videre i API-responses.

## Services og bookinglogik

Bookinglogikken er implementeret i `BookingController` og `BookingDAOImpl`. Inden en booking oprettes, kontrollerer vi, at både eleven og køretimen findes, og at køretimen ikke allerede er booket.

Vi har også oprettet `DrivingAiService`, som kommunikerer med Google Gemini ved hjælp af Java HttpClient og `CompletableFuture`.

Opdelingen gør det nemmere at holde API-håndtering, databaseoperationer og kommunikation med eksterne services adskilt.

## Separate databaser til testing og produktion

Et vigtigt teknisk valg var at holde automatiserede tests adskilt fra produktionsdatabasen.

Den deployede applikation bruger PostgreSQL, mens testene anvender midlertidige PostgreSQL 16-databaser, der oprettes gennem Testcontainers.

Vi har desuden fælles `DatabaseTest`- og `ApiTest`-klasser, som hjælper med at starte og stoppe testdatabasen og Javalin-serveren automatisk.

Det betyder, at vi kan køre tests uden først at oprette en testdatabase manuelt eller starte applikationen selv. Det er vigtigt, fordi testbrugere og testbookinger ikke skal ende i produktionsdatabasen.

## Sikkerhed

Vi bruger BCrypt til at hashe passwords og JWT til at identificere brugere efter login.

Vi har også roller for elever og kørelærere, så vores API kan kontrollere, hvilke endpoints brugerne har adgang til. De løsninger er med til at beskytte oplysninger og gøre systemet mere sikkert.

## Deployment

Vi bruger Docker til at køre applikationen i containers og GitHub Actions til at automatisere build og tests.

Ved hjælp af undervisningens deploymentguide fik vi DriveApp online med DigitalOcean og DanDomain. På den måde fik vi også praktisk erfaring med serveropsætning, domæner og DNS.

## Hvad jeg lærte

Arbejdet med DriveApp har lært mig, at backendudvikling ikke kun handler om at få en funktion til at virke. Det er også vigtigt at tænke på projektets struktur, så det er muligt at teste, ændre og vedligeholde løsningen.

Jeg har især fået en bedre forståelse for, hvordan valg omkring sikkerhed, automatiserede tests og deployment har betydning for, hvor stabilt og overskueligt et system bliver.

---

# Afsluttende refleksion

Gennem semesteret har jeg lært meget om backendudvikling ved at arbejde på DriveApp sammen med Amaan.

Vi begyndte med JPA, Hibernate og PostgreSQL og udbyggede gradvist systemet med REST API, testing, sikkerhed og deployment. Det har hjulpet mig med at se, hvordan de forskellige dele af en backend hænger sammen, fra databasen og DAO-klasserne til controllers og API-endpoints.

En af de vigtigste erfaringer for mig har været, at det ikke er nok, at en funktion virker isoleret. Når flere dele af et system skal arbejde sammen, bliver struktur, fejlhåndtering og testing afgørende.

Vi mødte også udfordringer undervejs, særligt med vores testopsætning og forskellige databasekonfigurationer. I starten brugte vi en separat lokal PostgreSQL-testdatabase, men senere gik vi over til Testcontainers. Nu kan testene oprette midlertidige PostgreSQL-databaser og starte Javalin på en ledig port automatisk.

Det var en forbedring, fordi vi ikke længere skulle være afhængige af en manuelt opsat testdatabase. Samtidig kunne vi holde testdata adskilt fra de rigtige data i produktion.

Vi brugte også tid på at rette fejl i tests og GitHub Actions. Det lærte mig, hvor vigtigt det er at kunne fejlfinde systematisk og sørge for, at testmiljøet fungerer uafhængigt af produktionsmiljøet.

En anden udfordring opstod under deployment, hvor vi havde problemer med at få domænet fra DanDomain til at fungere korrekt. Det handlede især om DNS og nameservers, blandt andet NS1, NS2 og NS3.

Vi måtte kontakte DanDomain flere gange og følge op for at finde årsagen og få domænet forbundet med serveren. Det tog tid, men gav mig en mere praktisk forståelse for, hvordan domæner, nameservers og DNS fungerer i forbindelse med deployment.

De udfordringer har lært mig, at debugging er en stor del af udviklingsarbejdet. Man er nødt til at undersøge problemerne trin for trin og forstå, hvorfor noget ikke fungerer, frem for bare at ændre koden tilfældigt.

Jeg har desuden fået erfaring med at samarbejde om kode på GitHub og med at deploye en Java-backend ved hjælp af Docker og DigitalOcean.

Samlet set har DriveApp givet mig en langt bedre forståelse for backendudvikling. Jeg har prøvet at være med i hele processen, fra de første entities og databaseoperationer til et REST API med tests, sikkerhed og en fungerende deployment.

Det vigtigste, jeg tager med mig fra projektet, er forståelsen af, hvordan alle disse teknologier hænger sammen i en samlet løsning, og hvorfor god struktur og løbende testing gør det lettere at udvikle et system videre.
