---
layout: default
title: Åben leverancemodel
parent: Guides

---

Draft
{: .label .label-yellow }

# Åben leverancemodel

_Sådan får I styr på leverancerne!_

<p style="text-align:right"><small><a href="mailto:jan.maack@os2.eu">Jan Maack Kjerbye - Enterprise Arkitekt @ os2.eu ✉️</a></small></p>

<br>

> _Som projektleder i det offentlige kan du stå i en situation hvor du indkøber softwareudvikling uden at kunne se, hvad leverandøren faktisk laver. Men det behøver ikke være sådan!_
>
> _En åben leverancemodel gør alt arbejde synligt og sporbart - fra den første idé til den endelige leverance. Modellen bygger oven på jeres kontrakt - I får nu dokumentation for hvad der er lavet, hvad der mangler, og hvem der har gjort hvad._



## Fordelene

| **Enighed om leverancer** |
| Skab fælles forståelse mellem myndighed og leverandør ved at definere alt arbejde som synlige, prioriterede opgaver. Når prioriteringer laves åbent, kan begge parter se og acceptere hvad der leveres hvornår.|

| **Handlefrihed til myndigheden** |
| Behold kontrollen over jeres projekt uanset hvilken leverandør I vælger at bruge, nu eller i fremtiden. Når al kode og dokumentation er tilgængeligt, kan I til enhver tid skifte leverandør uden at miste viden eller investeret arbejde.|

| **Digital suverænitet** |
|   _Digital suverænitet_ er et mål for mange myndigheder, men vejen derhen kan føles uklar. Denne model giver et konkret svar: Når I ejer kildekoden, har uafhængig teknisk kompetence og arbejder transparent, har I allerede taget de vigtigste skridt. EU's og statens ambitioner om [digital suverænitet](#læs-mere) starter med at have kontrol over jeres egne digitale løsninger.  |

| **Direkte genbrugelighed** |
| Når I betaler for en løsning der er udviklet i det åbne med denne metode, kan andre offentlige myndigheder genbruge den med blot ganske få lokale tilpasninger. Dette maksimerer værdien af skatteborgernes penge og styrker det fællesoffentlige digitale økosystem. |

---

## Tre enkle trin til implementering
---
### 1. Organisering
#### Etabler klare roller og prioritering
---
* Følg OS2's styringsmodel og etabler en styregruppe og en koordinationsgruppe til at varetage projektets ledelse og produktansvar. Skriv til os2@os2.eu for at komme i gang med det organisatoriske.
* Definér en [`maintainer`](#begreber)-rolle der har det tekniske overblik. Styregruppen, koordinationsgruppen og maintaineren har forskellige fokusområder men et fælles mål: at levere kvalitetssoftware til tiden.
* [`Maintainer`](#begreber)-rollen sikrer at arbejdet lever op til aftalte standarder og kan automatisere arbejdsgangene via [`CI/CD`](#begreber) automatiseringsværktøjer indbygget i projektets versionsstyrings [`repository`](#begreber). Rollen er koordinationsgruppens forlængede tekniske arm og kræver open source-kompetencer, dyb erfaring med versionsstyringsværktøjet [`git`](#begreber) og et neutralt, leverandøruafhængigt overblik - det kan være en dybt teknisk kollega, eller en teknisk open source specialist I hyrer ind separat, uafhængigt af udviklings- eller hostingleverandøren.

---
### 2. Teknisk implementering
#### Skab et standardiseret fundament
---

* Alt starter i jeres projekts OS2-ejede [`repository`](#begreber). Skriv til os2@os2.eu for oprettelse samt onboarding af maintainer og projektleder.
* Jeres leverancestyring konfigureres og styres fra dette [`repo`](#begreber) - I har som medlemmer direkte adgang og indflydelse. Kildekode, dokumentation og leverancehistorik m.m. placeres her, uden for udviklings- eller hostingleverandørernes interne systemer.
* Maintainer opsætter [`branch protection`](#begreber)-regler der sikrer at kun gennemgået, godkendt kode kan [`merges`](#begreber) ind i projektet.
* Maintainer opsætter også [`pull request`](#begreber)-skabeloner der sikrer at alle ændringsanmodninger ([`pull requests`](#begreber)) indeholder nødvendig kontekst.
* Moderne [`git`](#begreber) platforme har indbygget [`CI/CD`](#begreber)-funktionalitet - klar til brug med det samme. Maintaineren vælger fra et stort bibliotek af automatiseringsbyggeblokke og tilpasser dem til projektet.
* Adgangsrettigheder konfigureres og vedligeholdes for at sikre at kun maintainer og projektleder (på vegne af styregruppen) har skriveadgang til [`main branch`](#begreber).

---
### 3. Proces-etablering
#### Arbejd transparent fra dag ét
---
* Definer en [`backlog`](#begreber) i jeres [`issue-tracker`](#begreber) med alle ønsker og krav, og bind dem sammen med en [`branch`](#begreber) inden arbejdet godkendes til at blive sat i gang. Prioriter synligt, så leverandøren ved præcis hvad der skal laves. Dette binder den leverede kode og dokumentation sammen med den definerede opgave.
* Alt arbejde udspringer af en aftalt opgave ([`issue`](#begreber)). Når leverandøren har udført arbejdet, kan I se det via en anmodning om godkendelse ([`pull request`](#begreber)). Her kan I stille spørgsmål, bede om rettelser eller demoer. Først når I har godkendt det, bliver det en del af løsningen.
* Leverandøren kan på denne måde starte med at levere dokumentation og kode med det samme, men kan ikke ændre den endelige løsning uden jeres godkendelse. Ligesom alt andet arbejde er også godkendelsen synlig i ændringshistorikken.
* Resultatet af arbejdet leveres som en [`pull request`](#begreber). Før kode [`merges`](#begreber), gennemgås den af en anden end forfatteren selv.
* Som behovet stiger tilføjes automatiske tests via den indbyggede [`CI/CD`](#begreber) inden kode [`merges`](#begreber).

## Fremadrettet

Når I arbejder åbent og transparent, kan I opbygge et fællesskab omkring jeres løsning. Andre myndigheder kan følge med i udviklingen og bidrage med forbedringer. Denne model er et simpelt leverancekrav - ikke anderledes end at stille krav til dokumentation eller kvalitetssikring.

---

## Forstå begreberne {#begreber}
#### Klik på begrebet for en længere ekstern forklaring (på engelsk)

| Term | Beskrivelse |
|:----|:------------|
|[`issue`](https://docs.github.com/en/issues/tracking-your-work-with-issues/learning-about-issues/about-issues) ↗ | <small>En opgave, fejl eller idé der registreres i projektets [`issue-tracker`](#begreber)</small> 
|[`issue-tracker`](https://docs.github.com/en/issues) ↗ | <small>Repositoriets indbyggede opgavestyringssystem</small>
|[`branch`](https://docs.github.com/en/pull-requests/collaborating-with-pull-requests/proposing-changes-to-your-work-with-pull-requests/about-branches) ↗ | <small>En isoleret arbejdskopi der knyttes til et issue</small>
|[`backlog`](https://docs.github.com/en/issues/planning-and-tracking-with-projects/learning-about-projects/about-projects) ↗ | <small>Alle opgaver der venter på at blive prioriteret</small>
|[`maintainer`](https://docs.github.com/en/repositories/managing-your-repositorys-settings/about-repositories) ↗ | <small>Teknisk ansvarlig der sikrer processerne overholdes og kan automatisere dem</small>
|[`branch protection`](https://docs.github.com/en/repositories/configuring-branches-and-merges-in-your-repository/managing-protected-branches/about-protected-branches) ↗ | <small>Regler der forhindrer kodeændringer uden godkendelse</small>
|[`pull request`](https://docs.github.com/en/pull-requests/collaborating-with-pull-requests/proposing-changes-to-your-work-with-pull-requests/about-pull-requests) ↗ | <small>Anmodning om at få kodeændringer gennemgået og godkendt før de optages i projektet</small>
|[`repository`](https://docs.github.com/en/get-started/learning-about-github/about-github#repositories) ↗ | <small>Projektmappe med kode, dokumentation og releaseprocesser</small>
|[`merge`](https://docs.github.com/en/get-started/using-git/about-git#merge) ↗ | <small>Godkendelse og publicéring af kode, dokumentation eller konfiguration</small>
|[`main branch`](https://docs.github.com/en/get-started/learning-about-github/about-github#about-branches) ↗ | <small>Den godkendte, endelige version af koden (klar til udgivelse)</small>
|[`repo`](https://docs.github.com/en/get-started/learning-about-github/about-github#repositories) ↗ | <small>Almindeligt brugt forkortelse for repository – projektmappe med kode og dokumentation</small>
|[`git`](https://docs.github.com/en/get-started/using-git/about-git) ↗ | <small>Versionsstyringssystem der holder styr på ændringer i projektet</small>
|[`CI/CD`](https://docs.github.com/en/actions/automating-builds-and-tests/about-continuous-integration) ↗ | <small>Værktøjer til automatisering af test og udgivelse af kode</small> |

---


## Læs mere

* [OS2.eu - **Det gør OS2**](/det-goer-OS2)
* [OS2.eu - **Governance og styringsmodel**](/governance)
* [OS2.eu - **Arbejdsgrupper**](/arbejdsgrupper)
* [digst.dk - **Digital suverænitet** (oversigt)](https://digst.dk/digital-transformation/digital-suveraenitet/)
* [digst.dk - **Analyse af digital suverænitet** (PDF, Januar 2026)](https://digst.dk/media/z15pdfmq/digital-suveraenitet_sammenfattende-erfaringsopsamling-paa-myndigheders-initiativer-for-at-migrere-til-alternative-teknologier-28012026.pdf)
* [kl.dk - **Kommunernes Digitaliseringsstrategi 2026-2030** (PDF)](https://www.kl.dk/media/z52mk0xb/kommunernes-digitaliseringsstrategi-2026-2030.pdf)
* [EU - **Digital Decade Country Report - Denmark**](https://digital-strategy.ec.europa.eu/en/factpages/denmark-2025-digital-decade-country-report)
* [GitHub.com - **About issues**](https://docs.github.com/en/issues)
* [GitHub.com - **About pull requests**](https://docs.github.com/en/pull-requests/collaborating-with-pull-requests/proposing-changes-to-your-work-with-pull-requests/about-pull-requests)
* [GitHub.com - **About protected branches**](https://docs.github.com/en/repositories/configuring-branches-and-merges-in-your-repository/managing-protected-branches/about-protected-branches)
* [GitHub.com - **About branch protection rules**](https://docs.github.com/en/repositories/configuring-branches-and-merges-in-your-repository/managing-protected-branches/managing-branch-protection-rules)
* [os2.eu - **Hvad er Open Source?**](/hvad-er-open-source-1)
