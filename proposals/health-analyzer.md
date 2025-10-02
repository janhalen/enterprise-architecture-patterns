---
layout: default
title: "PoC: Helbredsanalyse via Serverless Dataops" # [🔖 Titel på indsats eller forslag]
author: "Jan Maack Kjerbye" # [Navn på forfatter]
date: "2025-10-02" # [Dato for oprettelse]
tags: [DataOps, Serverless BI, Open Source, Meltano, Evidence] # [Liste over relevante tags]
status: "Udkast" # [Status: Udkast, Godkendt, etc.]
parent: "Proposals"
published: false # [Skal siden vises på sitet? false = nej]
---

{% include header_metadata.html %}

Udkast  
{: .label .label-yellow }

## Baggrund

Dette dokument adresserer behovet for at evaluere **helbred, bæredygtighed og genanvendelighed** af open source-projekter via **data-drevet indsigt**. De nuværende udfordringer er primært knyttet til fraværet af **gennemsigtig, automatiseret** dataindsamling og rapportering uden at pådrage sig driftsbyrden fra leverandør og infrastruktur bundne datawarehouses og BI-værktøjer.

# Arkitektur anbefaling
---

> ### Det anbefales at **etablere et Serverless BI/DataOps Proof-of-Concept (PoC)** på en **Serverless BI**-tilgang, hvor analyser er **versionsstyrede** (`BI as code`), og rapporter genereres **on-demand** uden dedikeret infrastruktur..

Dette PoC skal udnytte **Evidence** til statisk rapportering, Meltano til ELT-processen og GitHub Actions som den serverløse orkestrato

## Komponenter
_Arkitekturlandskab_

---

#### **[Meltano](https://www.meltano.com/) (ELT Engine)**

> Meltano fungerer som den **åbne kildekode ELT-motor** og bruger **Singer-protokollen** til at ekstrahere (via f.eks. `tap-github`) og indlæse data. Den er essentiel for at sikre **inkrementel replikering** af metrikker og for at indkapsle *hele* dataudtræksprocessen i én container. Meltano er konfigureret til at bruge den samme **SQLite-fil** som både tilstandslager (`.meltano/meltano.sqlite`) og datalager (`data/pipeline.sqlite`).

Opsummering: ELT-motor, der henter data fra GitHub API og indlæser det inkrementelt i **SQLite-filen** (`data/pipeline.sqlite`).

#### **[Evidence](https://www.evidence.dev/) (Reporting Framework)**

> Evidence er et **Data-as-Code** rapporteringsværktøj, der tager live-data og transformerer det til **statiske Markdown/HTML-rapporter**. Det benytter **DuckDB** til at query data direkte fra den opdaterede SQLite-fil, hvilket sikrer, at analyser er **versionerede, auditerbare** og **transparente**.

Opsummering: Konverterer SQLite-data til statiske, **versionerede rapporter** til **GitHub Pages**.

#### **GitHub Actions (Orkestrering)**

> Fungerer som den **serverless orkestrator** og tidsbaserede scheduler. GHA eksekverer Meltano-containeren, håndterer **State Persistence** ved at downloade/committe den opdaterede SQLite-fil (`.meltano/meltano.sqlite` og `data/pipeline.sqlite`) tilbage til Git, og afslutter med at bygge og deploye Evidence-sitet.

Opsummering: **Automatiserer hele end-to-end-pipelinen** uden at kræve dedikeret serverdrift (serverless).

# Forventede gevinster
---


### 💰 Reduktion af driftsbyrden
> Løsningen er **serverløs**, hvilket eliminerer behovet for at **drifte, opdatere og betale for en persistent database** og et traditionelt BI-værktøj. Omkostninger er primært knyttet til den minimale beregningstid i GitHub Actions.

### 🧠 BI as Code og Genanvendelighed
> **Hele analysen** (data, transformation, rapport) er versionsstyret i Git. Dette sikrer **fuld sporbarhed** (*traceability*) og gør det muligt at **genanvende** og klone løsningen med minimal indsats for nye projekter (princippet om **Infrastructure as Code** udvidet til data).

### ⚡ Hurtig og Transparent Levering
> Rapporter genereres **hurtigt** som statiske HTML-sider, der kan **deles uden login** (via GitHub Pages), hvilket sikrer **transparens** og nem adgang for både tekniske og forretningsmæssige interessenter.

# Anvendte arkitekturprincipper

* **Serverless First:** Prioriterer værktøjer og services, der skalerer til nul og minimerer driftsbyrden (GitHub Actions, Evidence's statiske output).
* **GitOps (Configuration as Code):** Al kildekode, konfiguration (Meltano), transformationer (SQL/dbt) og *selve dataens state* (SQLite-filen) er **versionsstyret i Git**.
* **Best-of-Breed Open Source:** Anvender specialiserede, modne open source-værktøjer (Meltano til ELT, Evidence til rapportering, DuckDB/SQLite til datahåndtering) for at undgå *vendor lock-in*.
* **Data Integrity & Traceability:** Ved at committe den opdaterede SQLite-fil sikres det, at de genererede rapporter altid er baseret på **den senest synkroniserede dataversion** i repositoryet.
