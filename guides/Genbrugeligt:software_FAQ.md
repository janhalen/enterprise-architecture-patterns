---
layout: faq
title: Hvordan sikrer man at et stykke egenudviklet software kan genbruges?
parent: Guides
---

# Q&A

### 🧹  Hvad skal man tjekke for, når man offentliggør koden og hvilke data skal man fjerne?
**Hold koden ren for adgangsoplysninger og miljøspecifikke filer**
_Inden I offentliggør koden, skal I sikre, at der **ikke** ligger nogen form for data i repoet, som kan være følsomme, miljøspecifikke eller irrelevante for andre brugere. Et open source-repo skal være generisk og uafhængigt af jeres interne miljø – så andre kan bruge det uden at kende jeres infrastruktur._

Undgå:
- **Følsomme oplysninger og credentials**: API-nøgler, tokens, brugernavne, adgangskoder
- **Miljøspecifikke filer**: Produktionskonfigurationer, interne URL’er, IP-adresser, databasenavne
- **Data og logfiler**: Produktionsdata, testdata med rigtige oplysninger, logfiler fra drift eller udvikling
- **Intern kontekst**: Referencer til interne systemer, brugere eller dokumentation med personhenførbare oplysninger
- **Midlertidige filer**: Lokale udviklingsfiler, cache, build-artifacts


Men inkluder gerne:
- **Syntetiske eller anonymiserede data** til eksempler og tests
- **Eksempelfiler** til konfiguration, f.eks. `config.example.env`
- Dokumentation, der forklarer hvordan man selv tilføjer konfiguration af adgange, logs o.s.v.

Best practice:
- Brug **miljøvariabler** til konfiguration – ingen adgangsoplysninger i koden
- Tilføj en **eksempelfil** som `config.example.env` og dokumenter hvordan den anvendes.
- Brug `.gitignore` til at udelukke `.env`, `config.*`, `*.log`, `.pem` osv.
- Dokumentér i `README.md`, hvordan man opsætter miljøet lokalt og hvilke miljøvarible der er nødvendige.

### ⚗️ Hvilke tests skal man lave?

A: Automatiske tests og dokumenteret testmiljø øger kvaliteten og genbrugeligheden af softwaren. For at sikre at softwaren fungerer som forventet – både nu og i fremtiden – bør der være automatiske tests og en klar beskrivelse af, hvordan man opsætter et testmiljø. Det gør det lettere for andre at bidrage og genbruge projektet.

#### Best practice:
- **Automatiske tests**: Brug CI-værktøjer som GitHub Actions, GitLab CI eller lignende til at køre tests automatisk i kode repositoriet når ny kode kommer ind.

- **Linting og formattering:** Brug linterværktøjer i dit ide og/eller i de automatiske tests for at sikre ensartet kodekvalitet.

- **Enhedstests og integrationstests:**
 Test de vigtigste funktioner og hvordan de spiller sammen. Involver gerne daglige brugere i testprocessen for at fange realistiske anvendelsesmønstre.

- **Dokumenter testen:** Dokumentér teststrategi og testdata direkte i projektet – f.eks. i tests/-mappen eller som en del af README.md

- **Inkluder eksempelfiler til testmiljøopsætning:** Tilføj en README.md-sektion eller separat fil, der forklarer hvordan andre kan opsætte et testmiljø lokalt.


#### Undgå:
Tests der afhænger af interne systemer: Sørg for at tests kan køre uden adgang til jeres interne netværk eller services.

#### Men inkluder gerne:
- **CI-konfiguration:** En .github/workflows/test.yml eller tilsvarende, der viser hvordan tests kører automatisk.
- **Eksempler på testkommandoer:** I README.md eller CONTRIBUTING.md, så nye udviklere hurtigt kan komme i gang.

- **Syntetiske testdata:**
Inkluder gerne dummy-data (eller links til retvisende dummy data) til at simulere realistiske scenarier uden at bruge rigtige oplysninger.


### 📚 Hvilken dokumentation skal man tilknytte?

**God dokumentation gør projektet lettere at forstå, bruge og genbruge**
_Dokumentation er en nøglekomponent i open source-projekter – både for at sænke barren for nye brugere og for at sikre projektets genbrugelighed._

#### Best practice:
- **Inkluder altid en README.md:** Giv en klar introduktion til projektet, hvordan det bruges, og hvordan man kommer i gang.
- **Eksempler på brug:** Vis konkrete eksempler på, hvordan softwaren anvendes.
- **Miljøopsætning:** Beskriv hvordan man opsætter et lokalt udviklings- eller testmiljø, herunder nødvendige miljøvariabler og afhængigheder.

- **Eksempelfiler til udrulning** Tilføj eksempler på templates til flere forskellige åbne udrulningsværktøjer, så andre nemt kan deploye softwaren i deres egne miljøer. Brug standarder og værktøjer, der er frit tilgængelig, open source, veldokumenterede og understøttede på tværs af platforme – det fremmer genbrug og reducerer risikoen for leverandørlåse.

#### Undgå:
- **Ufuldstændig eller forældet dokumentation:** Hold dokumentationen opdateret sammen med koden for at undgå forvirring og hæmme genbrugs potentialet.

- **Antagelser om intern viden:** Forklar alt, som en ekstern udvikler ikke kan gætte sig til.

- **Dokumentation i separate, lukkede systemer:** Hold det hele i eller tæt på repoet – ikke i interne dokumentations-systemer eller lignende.

- **Dokumentation i proprietære formater:** Undgå formater som Word-filer (.docx), statiske PDF’er eller andre binære dokumenter, der ikke nemt kan versionsstyres eller læses direkte i et kode-repo. Brug i stedet tekstbaserede og åbne formater som Markdown, AsciiDoc eller reStructuredText, som kan redigeres, diffes og reviewes på lige fod med kode.


#### Men inkluder gerne:

- **Diagrammer og arkitekturtegninger:** For at give overblik over systemet og dets komponenter. Brug åbne standardformater, der kan versionsstyres og placeres direkte i dokumentationen som f.eks. Mermaid.

- **Link til relevante issues eller diskussioner:** Hvis der er kendte begrænsninger eller planlagte ændringer.

- **Bidragsvejledning:** En `CONTRIBUTING.md`, der forklarer hvordan man kan bidrage med kode, tests eller dokumentation.


### Q: _Hvor skal man offentliggøre det?_

A: Brug åbne og tilgængelige platforme, der understøtter samarbejde og genbrug  
_For at sikre at din kode og dokumentation er nem at finde, bruge og bidrage til, bør du offentliggøre den på en platform, der er bredt anvendt i open source-fællesskabet og understøtter versionsstyring, issues og samarbejde._

#### Best practice:
- **Brug en open source-venlig platform:** GitHub, GitLab (self-hosted eller .com), Codeberg eller SourceHut er gode valg. De understøtter versionsstyring, pull requests/merge requests, issues og CI/CD.
- **Gør projektet offentligt:** Sørg for at repoet er sat til "public", så alle kan tilgå det uden login.
- **Tilføj en open source-licens:** Uden en licens er koden *ikke* juridisk open source. Brug f.eks. MIT, Apache 2.0 eller GPL afhængigt af dine behov.
- **Brug din README.md som "landing page":** Forklar hvad projektet gør, hvordan man bruger det, og hvordan man bidrager.

#### Undgå:
- **Lukkede platforme eller interne systemer:** Hvis andre ikke kan tilgå det uden VPN eller login, er det ikke reelt open source.
- **At offentliggøre uden kontekst:** Et repo uden README, licens eller dokumentation er svært at bruge og forstå.
- **At bruge platforme uden versionsstyring:** Filer på f.eks. Google Drive eller Dropbox er ikke egnet til open source-arbejde.

#### Men inkluder gerne:
- **Et link til repoet i anden kommunikation:** Hvis projektet nævnes i artikler, præsentationer eller dokumenter, så link direkte til repoet.
- **Beskrivelser i `CONTRIBUTING.md` og `CODE_OF_CONDUCT.md`:** For at gøre det nemt og trygt for andre at bidrage.




