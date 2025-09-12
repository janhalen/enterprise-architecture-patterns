---
layout: default
title: 🔄 OpenData.dk integration med Fælleskommunal adgangsstyring
summary: "Brug af OS²Adgang som identitetsbro for den CKAN baserede dataportal OpenData.dk"
parent: Proposals
---

{% include header_metadata.html %}

Udkast
{: .label .label-yellow }



## Baggrund
_Givet opgaven at integrere OpenData platformen med Fælleskommunal Adgangsstyring (FKA) anbefales følgende:_

Det anbefales at genbruge **OS2 Adgang**, baseret på upstream-projektet [*Authentik*](https://goauthentik.io/), som identitetsbro.
Det anbefales at undgå direkte integration med en hård SAML binding i CKAN.

## Anbefaling
_Investér i en moderne og modulær løsning hvor OS2Adgang håndterer adgangsstyring og eksponerer en OIDC-grænseflade til CKAN. Dette bygger videre på eksisterende arbejde og standarder._

### De tre vigtigeste gevinster:

### 1. Fremtidssikret og standardiseret løsning
Ved at vælge OpenID Connect (OIDC) får men en moderne, sikker og bredt understøttet standard, som allerede anvendes af førende cloud- og SaaS-platforme. Implementeret i en seperat komponent reducerer et sådant arkitekturvalg risici for teknisk gæld, leverer et separat lag uden for applikationen der beskytter mod sårbarheder og gør det nemt at tilføje nye identitetsudbydere (IdP’er) fremadrettet.

### 2. Modulær arkitektur med klar ansvarsfordeling
Det anbefales at adgangsstyringen isoleres i en dedikeret komponent, hvilket giver en tydelig adskillelse mellem applikation og identitetshåndtering. Det øger sikkerheden og muliggører genanvendelse på tværs af systemer- En løskoblet løsning bliver lettere at vedligeholde og understøtter domænespecifikke funktioner som f.eks compliance og audit ad adgange og brugerhændelser.

### 3. Skalerbarhed og fleksibilitet til fremtidige behov
Løsningen er designet til at vokse med organisationens behov. Den understøtter integrationer på tværs af platforme, sikrer en ensartet brugeroplevelse og genbruger eksisterende komponenter – fx OS2’s SAML bidrag til Authentik – på tværs af projekter.

<br>

## Forudsætninger

- **Teknisk opsætning og test**: Afsæt ressourcer til tilpasning af eksisterende CKAN OIDC plugin og korrekt implementering + test af konfigurationer, herunder claims mapping og redirect-URI’er.
- **Dokumentation**: Klar dokumentation og overblik over autentificeringsflowet og de krævede arbejdsgange i KOMBIT systemerne er afgørende for en genbrugelig løsning og er en vigtig brik i en exit-strategi og leverer muligheden for et flerleverandør setup.
- **Overvågning og vedligehold**: Authentik bliver en central komponent og bør overvåges og vedligeholdes på lige fod som resten af infrastrukturen den betjener.

<br>

## Løsnings overblik

```mermaid
---
config:
  theme: default
---
flowchart TB
 subgraph subGraph0[" "]
        CKAN[("📊 <b>OpenData Platform</b><br><small>Bruger login via OS2 Adgang</small>")]
        Authentik["🔐 <b>OS2 Adgang</b><br><small>Sikrer adgang mellem <br> moderne og ældre loginsystemer</small>"]
        Legacy_IdP["🏛️ <b>Fælleskommunal<br> Adgang</b><br><small>Bruger SAML og OIO</small>"]
  end
    CKAN -- OIDC login --> Authentik
    Authentik -- SAML bro --> Legacy_IdP
    CKAN@{ shape: rounded}
    Authentik@{ shape: h-cyl}
    Legacy_IdP@{ shape: subproc}
     CKAN:::Aqua
     Authentik:::Sky
     Legacy_IdP:::Ash
    classDef Aqua stroke-width:1px, stroke-dasharray:none, stroke:#46EDC8, fill:#DEFFF8, color:#378E7A
    classDef Sky stroke-width:1px, stroke-dasharray:none, stroke:#374D7C, fill:#E2EBFF, color:#374D7C
    classDef Ash stroke-width:1px, stroke-dasharray:none, stroke:#999999, fill:#EEEEEE, color:#000000
    style Legacy_IdP color:#616161
    style subGraph0 fill:#e2f2e6, stroke:none
```