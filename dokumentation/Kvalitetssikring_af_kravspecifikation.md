## Kvalitetssikring af kravspecifikation

> Gennemgang og vurdering af kravspecifikation for migration af CPR-integration i OS2valghalla med henblik på udbud til leverandører

*Forfatter:* Jan Mack Kjerbye, Enterprise Arkitekt OS²

*Dato:* September 2026

---

## 1. Indledning

Da leverandører alene kan forventes at kende forhold der fremgår af fremsendt materiale, er denne vurdering udført alene på baggrund af det udleverede kravspecifikationsdokument (KS).

Uformel eller tavs viden, antagelser om kendskab til tidligere korrespondance eller aftaler nævnt andetsteds er dermed ikke en del af denne vurdering.

---

## 2. Strukturelle og formelle forhold

Flere af de berørte emner er generelle for softwareleverancer og kan med fordel henvises til eksterne bilag og principper fra autoritative kilder (DIGST, OS², KL m.fl.)

### 2.1 Ejerskab og ansvar

Manglende klarhed over roller, ansvar og ejerskab vil have afgørende betydning for en leverandørs endelige estimater.
Følgende forhold mangler specificering:

- **Beslutningsejerskab:** KS nævner analyse, arkitektur og implementering, men mangler formel afklaring af hvem der ejer de tekniske beslutninger og hvordan de dokumenteres. F.eks bør det afklares hvem der afgører om fallback er "teknisk muligt".

- **Ejerskab af leverancekæde:** KS nævner at kildekode skal leveres til OS2valghallas repository, men henviser ikke til governance-dokumentation (CONTRIBUTING.md, CODEOWNERS) der beskriver hvilken proces og kontrol kodebidrag, ændringsstyring og review-processer er underlagt.

- **Leverandøruafhængighed:** Kravspecifikationen nævner generelt at løsningen skal kunne videreudvikles af andre leverandører, men der mangler konkrete krav til at udarbejdelse af dokumentation for arkitekturvalg og tydelig afkobling af leverandørspecifikke komponenter skal foreligge som en del af et tilbud.

### 2.2 Konsolidering af parallelle krav

Konsolidering forbedrer læsevenlighed og kan minimere modstridende fortolkninger:

Konkrete muligheder for konsolidering:

- **Genbrug** (F3, O2) – samles ét sted med henvisning til DIGSTs principper og OS²s styringsmodel, så kravet ikke gentages unødigt
- **Fejlhåndtering**(F7, NF2) – samles i én sektion der beskriver den samlede fejlhåndteringsstrategi
- **Test** (F8, F9) – integreres til én teststrategi der dækker funktionel test, integrationstest og end-to-end-test
- **Dokumentation** (F9, O5, NF5) – samles ét sted med klart afgrænset ansvar og format
- **Leverandøruafhængighed** (NF5, O6) – beskrives samlet for at sikre ensartet fortolkning
- **Release** (F5, Fase 7) – samles til én samlet release-proces med tydelige milepæle

### 2.3 Præcisering af begreber

KS anvender flere steder begreber som *"tilfredsstillende resultat"* og *"stabil"*, der ikke er konkrete eller målbare. 

- **Uklarheder**:
  
  - Hvornår test betragtes som bestået
  
  - Hvornår "aftalt stabiliseringsperiode" betragtes som afsluttet
  
  - Hvad der definerer "tilfredsstillende" i forhold til test og performance

- **Præciseringer:**
  
  - *****"med rimelighed"* i fast pris bør defineres
  
  - *"unødige leverandørspecifikke afhængigheder"* bør konkretiseres
  
  - *"væsentlige oplysninger"* bør præciseres med en checkliste
  
  - *"gældende aftaler om support"* bør uddybes
  
  - Udsagn om *"relevante forhold"* mangler konkrete referencer
  
  - **"Hvis relevant"* bør erstattes med konkret afgrænsninger for relevans.



---

## 3. Teknisk gennemgang

### 3.1 Løsningsarkitektur

KS mangler henvisninger den autoritative beskrivelse af OS²valghallas løsningsarkitektur. For at levere et fast tilbud vil en leverandør bl.a. have brug for detaljeret viden om:

- Begrundet valg af programmeringssprog, frameworks.
- Databasevalg og dataformater
- Eksisterende integrationsarkitekturer, komponenter, libs, protokoller etc.
- Softwarens build-pipeline og deploymentsstruktur og hvilken ci/cd der forventes anvendt.

### 3.2 Services og datamodeller

Dokumentet nævner "Datafordeleren (DAF)" generelt, men specificerer ikke hvilke konkrete services eller datamodeller der forventes anvendt. Det bør afklares:

- **Services:** Hvilke konkrete services (f.eks. CPR Hent Person, CPR Søg Person), API-version og endpoint-struktur
- **Datamodeller:** Datamodeller for CPR-opslag (nuværende og kommende), for den eksisterende KOMBIT-integration og forventede datafelter/svarformater fra DAF

### 3.3 Eksisterende integrationer

Dokumentet nævner kort `PersonBaseDataExtendedService v.5 (SF1520 – CPR replika opslag)`, men linker ikke til dokumentation for:

- Hvilke felter og data OS2valghalla faktisk bruger fra denne service
- Hvor ofte opslag foretages (volumen)
- Om der er tale om abonnementer, hændelser eller batchkørsler
- Fejlhåndtering og timeout i den eksisterende integration

### 3.4 Testmiljøer

Dokumentet nævner "adgang til test- og produktionsmiljøer", men specificerer ikke:

- Hvis ansvar det er at etablere og drive testmiljøer, og om et fælles test snitflade stilles til rådighed fra KOMBIT med anvendelig test-data.
- Hvordan sådan evt. testdata tilgås og kvalitetssikres
- Om det kan blive nødvendigt med Mock-services for at kunne automatisere tests og nå deadline?

### 3.5 Parallel afvikling

Dokumentet nævner parallel afvikling som ønskværdigt, men mangler beskrivelser af:

- Hvordan dette teknisk skal implementeres (feature flags, routing-logik, etc.)
- Hvornår parallel afvikling er relevant (og hvornår den ikke er)
- Hvordan sammenligning af svar skal gennemføres i praksis
- Hvordan driftansvar placeres hvis der skal drives to parallelle instanser.
- Hvornår og efter hvilke kriterier parallel drift kan ophøre?

### 3.6 Sikkerhedskrav

Dokumentet nævner sikkerhedskrav generelt, men ikke:

- Typen af certifikater der skal anvendes (TLS, klientcertifikater, OAuth osv.)
- Hvem udsteder certifikaterne, hvordan integreres de?
- Om der er specifikke krav til secret / certifikat management
- Krav om databeskyttelse og lovformelighed:
  - Om leverandørerne har behov for adgange til eller behandling af persondata med deraffølgende krav om databehandleraftaler
  - Datamapping for CPR-data med angivelse af hvilke felter der behandles for at sikre dataminimering.
  - Hvilke krypteringskrav for CPR-data (in transit / at rest)
  - Hvilke adgangskontroller og audit trails på transport af persondata
  - Begrundede beslutninger om dataopbevaringstider og slettepolitikker for CPR-data



## 4. Konklusion

KS indeholder en grundlæggende god faglig forståelse af domænet og
de tekniske udfordringer. Punkterne herover kan medvirke til at styrke specifikationen inden udbud, så både projektet og kommende leverandør har et klart og fælles grundlag. Disse afklaringer om roller, ejerskab og tekniske forudsætninger, kan påvirke både tidsplan, omfang og pris og bør foretages inden der indgås aftaler med en udviklingsleverandør.



---
