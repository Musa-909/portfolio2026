---
title: "Driving School Management System - Week 1"
weight: 1
date: 2026-08-30
draft: false
---

# Driving School Management System

Et portfolio-projekt hvor vi gennem semesteret udvikler et backend-system til administration af en køreskole.

## Development Log

### Week 1 – Project Setup, JPA & CRUD

I uge 1 startede vi udviklingen af vores **Driving School Management System**.

Formålet med projektet er at udvikle et system, der kan hjælpe en køreskole med at administrere blandt andet elever, kørelærere, køretimer og andre relevante oplysninger.

Fokus i denne uge var at få projektets grundlæggende backend- og databasestruktur på plads ved hjælp af **Java, JPA, Hibernate og PostgreSQL**.

## Det har vi arbejdet med

- Oprettet projektets grundlæggende Maven-struktur
- Tilføjet de nødvendige dependencies til projektet
- Konfigureret **JPA og Hibernate**
- Forbundet projektet til en **PostgreSQL-database**
- Oprettet vores første JPA entity: `Study`
- Registreret vores entities gennem `EntityRegistry`
- Arbejdet med `EntityManager` og `EntityManagerFactory`
- Oprettet databasekonfiguration gennem:
  - `HibernateConfig`
  - `HibernateBaseProperties`
- Arbejdet med JPA annotations som:
  - `@Entity`
  - `@Table`
  - `@Id`
  - `@GeneratedValue`
  - `@Column`
- Arbejdet med CRUD-operationer:
  - Create
  - Read
  - Update
  - Delete

## Resultat

Ved slutningen af uge 1 har vi fået den grundlæggende backend- og databasestruktur på plads.

Projektet er blevet koblet til PostgreSQL gennem Hibernate og JPA, og vores første entity er blevet oprettet og registreret korrekt.

Vi har samtidig fået forståelse for, hvordan `EntityManager` bruges til at arbejde med data i databasen, og hvordan CRUD-operationer kan bruges til at oprette, hente, opdatere og slette data.

Resultatet er, at vi nu har et fungerende fundament for vores **Driving School Management System**, som vi kan bygge videre på i de kommende uger med flere entities, relationer og nye funktioner.