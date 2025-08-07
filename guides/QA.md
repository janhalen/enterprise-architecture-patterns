---
layout: default
title: Hvordan udgiver man sit software som open source?
parent: Guides
---

# ❓ Spørgsmål og svar

Denne side samler typiske spørgsmål og anbefalinger ved offentliggørelse af kode. Brug den som tjekliste og reference, når du deler projekter offentligt.

---

{: .question }

**❓ Hvad skal man tjekke for, når man offentliggør koden?**
<br>


{: .answer }
**🖐️ Undgå at inkludere data:**<br>
<small>
Det er god praksis at sikre, at **koden aldrig indeholder** adgangsoplysninger, miljøspecifikke konfigurationer eller andre følsomme data. Undgå derfor altid at inkludere:
</small>

- API-nøgler, tokens, brugernavne, adgangskoder  
- Produktionskonfigurationer, interne URL’er, IP-adresser, databasenavne  
- Produktionsdata, testdata med rigtige oplysninger, logfiler fra drift eller udvikling  
- Referencer til interne systemer, brugere eller dokumentation med personhenførbare oplysninger  
- Lokale udviklingsfiler, cache, build-artifacts  

{: .bestpractice }
**🤖 Anvend miljøvariable og syntetiske testdata**<br>
<small>
For at kunne udvikle og teste **uden at inkludere følsomme data i koden** anbefales det at følge en række best practices:
</small>

- Gør brug af syntetiske eller anonymiserede data til eksempler og tests  
- Dokumenter hvordan man selv tilføjer konfiguration af adgange, logs o.s.v.  
- Brug miljøvariabler til konfiguration af f.eks adgangskoder og tokens
- Tilføj en eksempelfil som `config.example.env` og dokumenter hvordan den anvendes  
- Brug `.gitignore` til at udelukke `.env`, `config.*`, `*.log`, `.pem` osv.  
- Dokumentér i `README.md`, hvordan man opsætter miljøet lokalt og hvilke miljøvariabler der er nødvendige  

---

{: .question }
**❓ Hvordan sikrer man, at der ikke ligger følsomme eller miljøspecifikke data i koden?**

{: .answer }
**🔍 Gå koden igennem:**<br>
<small>Selvom følsomme oplysninger og miljøspecifikke data **ikke bør være en del af kildekoden**, kan de utilsigtet ende der, især i interne projekter, der senere skal gøres offentlige. Derfor er det vigtigt at gennemgå koden grundigt inden offentliggørelse.
</small>

- Gennemgå data manuelt eller med scripts for at sikre, at intet følsomt slipper ud
- Lav en tjekliste for sikkerhed og databeskyttelse
- Få en kollega til at gennemgå koden med friske øjne


{: .bestpractice } 
**⚙️ Automatiske tjek i CI-pipeline**<br>
<small>
For at undgå utilsigtet offentliggørelse af følsomme oplysninger anbefales det at integrere automatiske tjek i projektets CI-pipeline. Det hjælper med at fange fejl tidligt og sikrer, at open source-projekter er sikre og ansvarligt udgivet.
</small>
- inkluder tjek med...


{: .highlight }
**⚠️ Hvis følsomme data allerede er committet:**<br>
<small>
Opdages det, at følsomme oplysninger ved en fejl er blevet inkluderet i kildekoden, bør de **fjernes så hurtigt som muligt**. Det gælder både i den aktuelle version og – hvis nødvendigt – i hele Git-historikken. Adgangsoplysninger der ved en fejl er blevt offentligtgjorte **skal skiftes med det samme** og det anbefales at gennemgå om der er behov for yderligere sikkerhedsforanstaltninger.
</small>

- Brug git filter-repo eller BFG Repo-Cleaner til at fjerne dem fra historikken
- Opret en ny commit med en ren version og force-push om nødvendigt (med forsigtighed)

---

{: .question }
**❓ Hvilke tests skal man lave?**

----

{: .question }
**❓ Hvilken dokumentation skal man tilknytte?**

---

{: .question }
**❓ Hvor skal koden offentliggøres?**

---



<details>
<summary>❓ Hvordan sikrer man, at der ikke ligger følsomme eller miljøspecifikke data i koden?</summary>

{: .answer }
**🔍 Gå koden igennem**

Selvom følsomme oplysninger og miljøspecifikke data **ikke bør være en del af kildekoden**, kan de utilsigtet ende der, især i interne projekter, der senere skal gøres offentlige. Derfor er det vigtigt at gennemgå koden grundigt inden offentliggørelse.

- Gennemgå data manuelt eller med scripts for at sikre, at intet følsomt slipper ud  
- Brug automatiske værktøjer som GitLeaks, TruffleHog eller detect-secrets

{: .bestpractice }
**⚙️ Automatiske tjek i CI-pipeline**

For at undgå utilsigtet offentliggørelse af følsomme oplysninger anbefales det at integrere automatiske tjek i projektets CI-pipeline. Det hjælper med at fange fejl tidligt og sikrer, at open source-projekter er sikre og ansvarligt udgivet.

Eksempler på værktøjer:

- **GitLeaks**: Scanner for hardcodede secrets som API-nøgler og tokens  
- **TruffleHog**: Finder credentials i hele Git-historikken  
- **pre-commit hooks**: Kører tjek lokalt før kode pushes til repoet  

</details>
