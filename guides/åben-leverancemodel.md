---
layout: default
title: 📦 Åben leverancemodel
parent: Guides

---

# 📦 Åben leverancemodel
### _Sådan får I styr på leverancerne!_

<p style="text-align:right"><small>👤 Jan Maack Kjerbye - Enterprise Arkitekt @ os2.eu</small></p>

<br>

> _Som projektleder i det offentlige kan du stå i en situation hvor du indkøber softwareudvikling uden at kunne se hvad leverandøren faktisk laver. Det behøver ikke være sådan._
>
> _En åben leverancemodel gør alt arbejde synligt og sporbart - fra den første idé til den endelige leverance. Modellen bygger ovenpå jeres kontrakt - I får nu dokumentation for hvad der er lavet, hvad der mangler, og hvem der har gjort hvad._



## Fordelene

- **Enighed om leverancer**:

    Skab fælles forståelse mellem myndighed og leverandør ved at definere alt arbejde som synlige, prioriterede opgaver. Når prioriteringer laves åbent, kan begge parter se og acceptere hvad der leveres hvornår.

- **Handlefrihed til myndigheden**:

    Behold kontrollen over jeres projekt uanset hvilken leverandør I vælger at bruge, nu eller i fremtiden. Når al kode og dokumentation er tilgængeligt, kan I til enhver tid skifte leverandør uden at miste viden eller investeret arbejde.

- **Digital suverænitet**:

    _Digital suverænitet_ er et mål for mange myndigheder, men vejen derhen kan føles uklar. Denne model giver et konkret svar: Når I ejer kildekoden, har uafhængig teknisk kompetence og arbejder transparent, har I allerede taget de vigtigste skridt. EU's og statens ambitioner om [digital autonomi](#læs-mere) starter med at have kontrol over jeres egne digitale løsninger. 

- **Direkte genbrugelighed**:

    Når I betaler for en løsning der er udviklet i det åbne med denne metode, kan andre offentlige myndigheder genbruge den med blot ganske få lokale tilpasninger. Dette maksimerer værdien af skatteborgernes penge og styrker det fællesoffentlige digitale økosystem.

---
### Forstå begreberne {#begreber}
##### Denne guide anvender en række tekniske begreber fra versionsstyring og softwareudvikling. Nedenfor er de forklaret med kendte begreber fra projektstyring

`issue`  
: <small>Opgavebeskrivelser, user-stories, løsningsdialog, fejlbeskrivelser, ideer m.m. samles i `issue-trackeren` som issues.

`branch`  
: <small>Isoleret arbejdsmappe, bindes sammen med et issue for at forstå formålet og gøre indholdet transparent.

`backlog`  
: <small>Prioriteret liste af opgaver

`maintainer`  
: <small>Teknisk rolle der sikrer processerne overholdes og automatiserer processerne løbende.

`branch protection`  
: <small>**Kildekodebeskyttelse** Et standard regelsæt der opsættes på `repo`  og forhindrer merge uden review.

`pull request`  
: <small>Anmodning om godkendelse og publicering. Forkortes PR og omtales i nogle systemer også som MR - merge request

`repository`  
: <small>**Projektmappe** - Projektområde til kode, dokumentation, releaseprocesser, kvalitetssikring og `issue-tracker` 

`merge`  
: <small>Godkendelse og publicéring til `main-branch` - Indfletning af godkendt kode, klar til produktion.

`main branch`  
: <small>**Seneste udgivelsesklare version** - Hovedsporet for kildekoden - den godkendte, endelige version klar til release

`repo`  
: <small>**Projektmappe** - Kort for `repository` - projektområde til kode, dokumentation, releaseprocesser, kvalitetssikring og `issue-tracker` 

`git`  
: <small>**Versionsstying** - Versionskontrolssystem der kan styre ændringer i projektet

`CI/CD`  
: <small>Continuous Integration / Continuous Deployment - indbyggede automatiseringsværktøjer i enhver moderne git platform. Maintaineren vælger fra et stort bibliotek af færdige byggeblokke ≈ Automatiseret kvalitetssikring

---

## Tre Enkle Trin til Implementering

### 1. ORGANISERING
**Etabler klare roller og prioritering**

* Følg OS2's styringsmodel og etabler en styregruppe og en koordinationsgruppe til at varetage projektets ledelse og produktansvar. Skriv til os2@os2.eu for at komme i gang med det organisatoriske.
* Definér en rolle der har det tekniske overblik ([`maintainer`](#begreber)). De tre roller har forskellige fokusområder men et fælles mål: at levere kvalitetssoftware til tiden.
* Maintaineren sikrer at arbejdet lever op til aftalte standarder og anvender indbyggede automatiseringsværktøjer (CI/CD). Rollen kræver teknisk kompetence og et leverandøruafhængigt overblik - det kan være en teknisk kollega, eller en specialist I hyrer ind separat. 


### 2. TEKNISK IMPLEMENTERING
**Få styr på værktøjerne fra start**

* Alt starter i jeres projekts OS2-ejede [`repo`](#begreber) skriv til os2@os2.eu for oprettelse samt onboarding af maintainer og projektleder.
* Jeres leverancestyring konfigureres i dette [`repo`](#begreber) - I har som medlemmer direkte adgang og indflydelse. Kildekode, dokumentation og leverancehistorik m.m. placeres her, uden for leverandørens interne systemer.
* Maintainer opsætter [`branch protection`](#begreber) regler der sikrer at kun gennemgået kode kan [`merges`](#begreber).
* Maintainer opsætter også [`pull request`](#begreber)-skabeloner der sikrer at alle [`pull requests`](#begreber) indeholder nødvendig kontekst.
* Moderne git platforme har indbygget [`CI/CD`](#begreber)-funktionalitet - klar til brug med det samme. Maintaineren vælger fra et stort bibliotek af automatiserings byggeblokke og tilpasser dem til projektet.
* Adgangsrettigheder konfigureres og sikrer at kun maintainer og projektleder (på vegne af produktejer) har skriveadgang til [`main branch`](#begreber).

### 3. PROCESS ETABLERING
**Arbejd transparent fra dag ét**

* Definer en [`backlog`](#begreber) i jeres `issue-tracker` med alle ønsker og krav og bind dem sammen med koden via en `branch` når arbejdet er godkendt til at sætte i gang. Prioriter synligt, så leverandøren ved præcis hvad der skal laves.
* Alt arbejde udspringer af en aftalt opgave ([`issue`](#begreber)). Når leverandøren har udført arbejdet, kan I se det via en anmodning om godkendelse ([`pull request`](#begreber)). Her kan I stille spørgsmål, bede om rettelser eller demoer. Først når I har godkendt det, bliver det en del af løsningen.
* Hver ændring arbejdes i en isoleret arbejdskopi kaldet en [`branch`](#begreber) der knyttes til det relevante [`issue`](#begreber).
* Leverandøren kan nu levere kode, men kan ikke ændre den endelige løsning uden jeres godkendelse - og ligesom alt andet arbejde er også godkendelsen synlig i ændringshistorikken.
* Resultatet af arbejdet leveres som en `pull request`](#begreber). Før kode [`merges`](#begreber), gennemgås den af en andre end forfatteren selv.
* Som behovet stiger tilføjes automatiske tests via den indbyggede CI/CD inden kode man [`merges`](#begreber).

## Fremadrettet

Når I arbejder åbent og transparent, kan I opbygge et fællesskab omkring jeres løsning. Andre myndigheder kan følge med i udviklingen og bidrage med forbedringer. Denne model er et simpelt leverancekrav - ikke anderledes end at stille krav til dokumentation eller kvalitetssikring.

---

###### Læs mere:

###### [OS2.eu - **Det gør OS2**](/det-goer-OS2)

###### [OS2.eu - **Governance og styringsmodel**](/governance)

###### [OS2.eu - **Arbejdsgrupper**](/arbejdsgrupper)

###### [digst.dk - **Digital suverænitet** (oversigt)](https://digst.dk/digital-transformation/digital-suveraenitet/)

###### [digst.dk - **Analyse af digital suverænitet** (PDF, Januar 2026)](https://digst.dk/media/z15pdfmq/digital-suveraenitet_sammenfattende-erfaringsopsamling-paa-myndigheders-initiativer-for-at-migrere-til-alternative-teknologier-28012026.pdf)

###### [kl.dk - **Kommunernes Digitaliseringsstrategi 2026-2030** (PDF)](https://www.kl.dk/media/z52mk0xb/kommunernes-digitaliseringsstrategi-2026-2030.pdf)

###### [EU - **Digital Decade Country Report - Denmark**](https://digital-strategy.ec.europa.eu/en/factpages/denmark-2025-digital-decade-country-report)

###### [GitHub.com - **About issues**](https://docs.github.com/en/issues)

###### [GitHub.com - **About pull requests**](https://docs.github.com/en/pull-requests/collaborating-with-pull-requests/proposing-changes-to-your-work-with-pull-requests/about-pull-requests)

###### [GitHub.com - **About protected branches**](https://docs.github.com/en/repositories/configuring-branches-and-merges-in-your-repository/managing-protected-branches/about-protected-branches)

###### [GitHub.com - **About branch protection rules**](https://docs.github.com/en/repositories/configuring-branches-and-merges-in-your-repository/managing-protected-branches/managing-branch-protection-rules)

###### [os2.eu - **Hvad er Open Source?**](/hvad-er-open-source-1)
