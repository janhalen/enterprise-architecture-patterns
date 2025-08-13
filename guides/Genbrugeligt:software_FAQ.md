---
layout: default
title: ♻️ Hvordan sikrer man at et stykke egenudviklet software kan genbruges?
parent: Guides
---

# ♻️ Genbrugs-kriterier for Open Source  
*Hvordan du gør dit projekt nemt at finde, forstå og genbruge – uden at miste pusten.*

---

## 🔍 Eksponering (Findable)  
*Gør det nemt for andre at finde og forstå dit projekt.*

- Projektet kan findes via almindelig internetsøgning.
- En kort og klar **README.md** forklarer formål og gevinster.
- Dokumentationen er tilgængelig i et **søgbart webformat** (f.eks. auto - statisk site generator webside). skalbelon
- Brug af **emneord/tags** for bedre indeksering.
- Metadata udstilles via f.eks. **publiccode.yml**.
- Projektets ejere deltager aktivt i at udbrede kendskabet.

---

## 🌐 Tilgængelighed (Accessible)  
*Alle skal kunne tilgå og forstå projektet – uden at spørge først.*

- Kildekode og dokumentation er offentligt tilgængeligt (GitHub, GitLab, Codeberg).
- Udviklingsmetoder er beskrevet i en **CONTRIBUTING.md**.
- Udviklingen er **transparent** med historik (SemVer, Conventional Commits, CHANGELOG.md).
- Der findes en **kontaktkanal** (issues, discussions, chat) til spørgsmål og feedback.

---

## 🔄 Interoperabilitet (Interoperable)  
*Projektet skal kunne spille sammen med andre systemer og teknologier.*

- Brug af **standardiserede dataformater** (JSON, YAML).
- Kompatibilitet med andre **åbne systemer**.
- Der er tænkt på **videreudvikling og integration** med andre systemer.
- Projektet er pakket i et **standard eksekverbart format** (f.eks. oci-container), uafhængigt af lokale systemer.

---

## 🔁 Genbrugelighed (Reusable)  
*Andre skal kunne bruge, fejlfinde og bidrage til projektet.*

- Projektet er **observable** – udstiller logs og data til fejlfinding.
- Koden er **aktivt vedligeholdt** og sikker (opdaterede afhængigheder, automatisering).
- Der er afsat **ressourcer til governance** (maintainere, code stewards).
- Koden **testes og gennemses** før den merges (CI/CD, automatiske tests).
- Et **aktivt, sund community** understøtter udvikling og vedligehold (Pony- og Elephant-faktorer). 
- Code of Conduct: En CODE_OF_CONDUCT.md skaber tryghed og sætter rammer for samarbejde.
- Der medfølger **implementeringsskabeloner** til flere platforme.
- Security policy: En SECURITY.md med vejledning til, hvordan man rapporterer sårbarheder.
- **Kvalitetssikring og sikkerhed** er dokumenteret og gerne automatiseret:
  - Scanning af afhængigheder (f.eks Dependabot, Renovate eller Snyk.)
  - Tests før hvert build som accept kriterier i PRs

---

## 📚 Inspiration og baggrund

### FAIR-principperne og FAIR-USE4OS 

- [FAIR for Beginners – DeiC](https://www.deic.dk/en/data-management/instructions-and-guides/FAIR-for-Beginners)

- [Guidelines for creating impactful open-source software](https://journals.plos.org/ploscompbiol/article?id=10.1371/journal.pcbi.1012045)

- [The FAIR Principles for Data andSoftware](https://researchcodingclub.github.io/slides/2023-08-23-fair-data-and-software.pdf)

- [Translating the FAIR principles to code](https://sites.google.com/sheffield.ac.uk/fair-guidance/your-data-typecode/code-software)

---

# Spørgsmål og svar

<br>

<details>
  <summary>❓ Hvad skal man tjekke for, når man offentliggør koden?</summary>
  <br>
  <strong>✅ Hold koden ren for adgangsoplysninger og miljøspecifikke filer</strong><br>
  Inden I offentliggør koden, skal I sikre, at der ikke ligger nogen form for data i repoet, som kan være følsomme, miljøspecifikke eller irrelevante for andre brugere.
  <pre><code>
📌 Best practice:
  - Brug miljøvariabler til konfiguration – ingen adgangsoplysninger i koden
  - Tilføj en eksempelfil som `config.example.env` og dokumenter hvordan den anvendes
  - Brug `.gitignore` til at udelukke `.env`, `config.*`, `*.log`, `.pem` osv.
  - Dokumentér i `README.md`, hvordan man opsætter miljøet lokalt

🚫 Undgå:
  - Følsomme oplysninger og credentials: API-nøgler, tokens, brugernavne, adgangskoder
  - Miljøspecifikke filer: Produktionskonfigurationer, interne URL’er, IP-adresser
  - Data og logfiler: Produktionsdata, testdata med rigtige oplysninger
  - Intern kontekst: Referencer til interne systemer eller dokumentation
  - Midlertidige filer: Lokale udviklingsfiler, cache, build-artifacts

✅ Men inkluder gerne:
  - Syntetiske eller anonymiserede data til eksempler og tests
  - Eksempelfiler til konfiguration, f.eks. `config.example.env`
  - Dokumentation for hvordan man selv tilføjer konfiguration
  </code></pre>
</details>

---

<details>
  <summary>❓ Hvilke tests skal man lave?</summary>
  <br>
  <strong>✅ Automatiske tests og dokumenteret testmiljø øger kvaliteten</strong><br>
  For at sikre at softwaren fungerer som forventet – både nu og i fremtiden – bør der være automatiske tests og en klar beskrivelse af testmiljøet.
  <pre><code>
📌 Best practice:
  - Automatiske tests med CI-værktøjer som GitHub Actions eller GitLab CI
  - Linting og formattering med IDE eller CI
  - Enhedstests og integrationstests – gerne med input fra brugere
  - Dokumentér teststrategi og testdata i `tests/` eller `README.md`
  - Inkluder eksempelfiler til testmiljøopsætning

🚫 Undgå:
  - Tests der afhænger af interne systemer eller netværk

✅ Men inkluder gerne:
  - CI-konfiguration: f.eks. `.github/workflows/test.yml`
  - Eksempler på testkommandoer i `README.md` eller `CONTRIBUTING.md`
  - Syntetiske testdata til realistiske scenarier
  </code></pre>
</details>

---

<details>
  <summary>❓ Hvilken dokumentation skal man tilknytte?</summary>
  <br>
  <strong>✅ God dokumentation gør projektet lettere at forstå og genbruge</strong><br>
  Dokumentation er en nøglekomponent i open source-projekter – både for nye brugere og for genbrug.
  <pre><code>
📌 Best practice:
  - Inkluder altid en README.md med introduktion og brug
  - Vis konkrete eksempler på anvendelse
  - Beskriv miljøopsætning og nødvendige variabler
  - Tilføj templates til udrulning med åbne værktøjer

🚫 Undgå:
  - Ufuldstændig eller forældet dokumentation
  - Antagelser om intern viden
  - Dokumentation i lukkede systemer eller proprietære formater

✅ Men inkluder gerne:
  - Diagrammer og arkitekturtegninger (f.eks. Mermaid)
  - Links til relevante issues eller diskussioner
  - En `CONTRIBUTING.md` med bidragsvejledning
  </code></pre>
</details>

---

<details>
  <summary>❓ Hvor skal man offentliggøre det?</summary>
  <br>
  <strong>✅ Brug åbne og tilgængelige platforme</strong><br>
  For at sikre at din kode er nem at finde og bidrage til, bør du bruge en platform med versionsstyring og samarbejdsværktøjer.
  <pre><code>

📌 Best practice:
  - Brug GitHub, GitLab, Codeberg eller SourceHut
  - Gør projektet offentligt
  - Tilføj en open source-licens (MIT, Apache 2.0, GPL)
  - Brug README.md som landing page

🚫 Undgå:
  - Lukkede platforme eller interne systemer
  - At offentliggøre uden README, licens eller dokumentation
  - Platforme uden versionsstyring (f.eks. Google Drive)

✅ Men inkluder gerne:
  - Link til repoet i artikler, præsentationer eller dokumenter
  - `CONTRIBUTING.md` og `CODE_OF_CONDUCT.md` for bidrag
  </code></pre>
</details>

---