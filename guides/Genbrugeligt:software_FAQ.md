---
layout: default
title: ♻️ Hvordan sikrer man at et stykke egenudviklet software kan genbruges?
parent: Guides
---

# ♻️ Genbrugs-kriterier for Open Source  
✅ _Hvordan du gør dit projekt nemt at finde, forstå og genbruge –  3 hurtige trin_

<br>

## 1️⃣ Strategi og rammer
- [ ] Afklar behov og mål ([DIGST Vejledning om open source](https://arkitektur.digst.dk/sites/default/fileuploads/Tjekliste_til_brug_af_open_source_i_den_offentlige_sektor.pdf))
- [ ] Vælg åben licens og delingsstrategi ([DIGST Tjekliste til Standard for Offentlig Kode (PDF)](https://arkitektur.digst.dk/sites/default/fileuploads/Tjekliste_til_Standard_for_Offentlig_Kode_version_0.7.1.pdf))
- [ ] Lav markedsafdækning og TCO‑vurdering ([DIGST Strategier for genbrug og fællesudvikling](https://arkitektur.digst.dk/metoder/arkitekturmetoder/introduktion-til-vejledning-om-brug-af-open-source-i-den-offentlige-sektor))

## 2️⃣ Design og governance
- [ ] Etabler governance og roller ([OS2 Governance-model](https://www.os2.eu/governance))
- [ ] Planlæg brugerinddragelse og tilgængelighed ([FAIR-USE4OS Guidelines](https://journals.plos.org/ploscompbiol/article?id=10.1371/journal.pcbi.1012045))
- [ ] Garanter bæredygtighed og finansiering over tid ([OS2 Governance-rapport skabelon](https://github.com/OS2offdig))

## 3️⃣ Leverance og genbrug
- [ ] Byg åbent med åbne standarder ([Standard for Public Code](https://standard.publiccode.net/criteria/))
- [ ] Dokumentér kode, test og review ([GitHub Open Source Guide](https://opensource.guide/how-to-contribute/))
- [ ] Gør løsningen findbar og inviter bidrag ([opensource.guide – Building welcoming communities](https://opensource.guide/building-community/))
- [ ] Vedligehold roadmap og community ([OS2 GitHub](https://github.com/OS2offdig))


<br>


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

<br>

---

### Baggrundsmateriale

| 🏛 DIGST | 🤝 OS2 | 🫶 FAIR-USE4OS | 📖 Foundation for Public Code | 🌍 Open Source Guide |
|----------|-------------------|------------------------|---------------|-----------------------|
| 📖 [_DIGST Vejledning om open source_](https://arkitektur.digst.dk/metoder/arkitekturmetoder/introduktion-til-vejledning-om-brug-af-open-source-i-den-offentlige-sektor) | [ 📋 _OS2-Governancemodel_ ](https://www.os2.eu/governance) | [ 💓 _FAIR-USE4OS Guidelines_](https://journals.plos.org/ploscompbiol/article?id=10.1371/journal.pcbi.1012045) | [🥇 _Standard for Public Code_](https://standard.publiccode.net/)  | [ 🧑‍🤝‍🧑 _Community-drevet guide til open source_](https://opensource.guide/)|





