---
layout: default
title: "🔖 Test" 
author: "Jan Maack Kjerbye" 
date: "25-09-2025" 
tags: [IoT, FIWARE, NGSI-LD, Genbrug, Standardisering]
status: "Godkendelse af princip" 
parent: "Proposals"
published: true
---

{% include header_metadata.html %}

# Status: Godkendelse af Princip 🚀
{: .text-green-000 }

**Mål:** Eliminér teknisk gæld og vendor lock-in ved at standardisere flådedata med FIWARE/NGSI-LD.

---

## Baggrund: Den Nuværende Udfordring

Den nuværende situation omfatter et behov for at integrere data fra en række **GPS-enheder** i et centralt flådestyringssystem.

> **💡 Problemet:** Leverandøren har foreslået en custom-udviklet backend og en agentlignende komponent.
>
> **⚠️ Risikoen:** Dette skaber **unødvendige vedligeholdelsesomkostninger**, øger **leverandørafhængigheder** og akkumulerer betydelig **teknisk gæld**.
{: .note .note-danger}

Dette forslag afbøder aktivt denne risiko ved at gøre brug af internationalt anerkendte arkitekturprincipper og metoder.

---

## Formål og Væsentlige Effekter ✨

| Effekt | Beskrivelse | Nøglekomponent |
| :--- | :--- | :--- |
| **Standardisering** | Data struktureres efter **ETSI's NGSI-LD-standard**, hvilket gør data **let at dele, genbruge og integrere** med andre offentlige myndigheder. | `NGSI-LD` |
| **Interoperabilitet** | Hurtigere og mere omkostningseffektivt at tilføje nye enhedstyper eller sammenkoble andre standard analyse- eller servicesystemer. | `FIWARE Komponenter` |
| **Reduktion af Driftsbyrden** | FIWARE Foundation og Open Source fællesskaberne vedligeholder kernekomponenterne (Orion-LD, IoT-Agents). **Aflaster driftsbudgettet**. | `Orion-LD` |
| **Styrket Handlefrihed** | Standardiserede protokoller sikrer **kontinuitet** ved leverandørskifte. Sikker exit-strategi. | `NGSI-LD` |
| **Fokus på Forretningsværdi** | IoT Agent-rammeværket tillader udviklerne **udelukkende at fokusere på den unikke GPS-protokol**. | `IoT-Agent Framework` |
| **Skalerbarhed/Robusthed** | **Orion-LD** er designet til storskala datastrømme, hvilket sikrer, at systemet er **driftssikkert** fra dag ét. | `Orion-LD` |
{: .table .table-striped }

---

## Anvendte Arkitektoniske Principper

Disse principper forankrer løsningen i anerkendte standarder og akademiske koncepter, hvilket sikrer et robust design.

### 1. Genbrug (Software Reuse & COTS)
> Reducerer omkostninger og risiko ved at maksimere genbrug af eksisterende COTS/FOSS komponenter over nyudvikling.
{: .label .label-blue }
🔗 [TOGAF - Common Use Applications](https://pubs.opengroup.org/architecture/togaf9-doc/arch/chap20.html)

### 2. Standardisering (Interoperability & Open Standards)
> Sikrer informationsudveksling og interoperabilitet, og afbøder risici for leverandørlåse.
{: .label .label-green }
🔗 [ETSI - NGSI-LD (åben datastandard)](https://www.etsi.org/technologies/smart-cities/ngsi-ld)

### 3. Modularitet og Løskobling (Separation of Concerns & Loose Coupling)
> Sikrer skalerbarhed og effektivt vedligehold ved at adskille bekymringer (concerns) i løst koblede moduler.
{: .label .label-yellow }
🔗 [Parnas, D. L.: On the Criteria To Be Used in Decomposing Systems into Modules (1972)](https://web.eecs.umich.edu/~stearn/pubs/criteria-72.pdf)

---

## Risikovurdering og Afbødning 🛡️

Vi anerkender potentielle risici og foreslår konkrete afbødningsstrategier.

| Kategori | Risici (Custom-løsning) | Afbødning (FIWARE-løsning) |
| :--- | :--- | :--- |
| **Teknisk Gæld** | Vedligeholdelse, sikkerhed og skaleringsoptimering vil være en **vedvarende byrde** for myndigheden. | **✅ Vælg FIWARE/Orion-LD:** Løbende vedligeholdelse og fejlrettelse leveres af et stort Open Source-fællesskab, hvilket **minimerer teknisk gæld**. |
| **Leverandørafhængighed** | Proprietær backend/agent øger risikoen for **vendor lock-in**, hvilket komplicerer fremtidige udbud/overdragelser. | **✅ Vælg NGSI-LD:** Data semantikken er standardiseret. Enhver kompetent partner kan overtage driften af Context Brokeren. |
| **Læringskurve** | Initial læringskurve for interne medarbejdere og leverandøren i forhold til FIWAREs koncepter (NGSI-LD, Entity Modelling). | **✅ Udnyt FIWARE Academy:** FIWARE er veldokumenteret og har en stor mængde tutorials og eksisterende implementeringer til hurtig kompetenceopbygning. |
{: .table .table-bordered }

[Implementér FIWARE-Løsningen Nu](https://fiware-ops.github.io/docs/){: .btn .btn-blue .btn-block }