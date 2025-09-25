---
layout: default
title: "🔖 Udviddelse af Os2FleetOptimiser med direkte device understøttelse"
summary: "Arkitekturforslag til integration af GPS data direkte fra enheder via genbrug af internationalt anerkendte Open Source komponenter og datastandarder."
author: "Jan Maack Kjerbye" 
date: "25-09-2025" 
tags: [IoT, FIWARE, NGSI-LD, Genbrug, Standardisering]
status: "Udkast" 
parent: "Proposals"
published: true
---

{% include header_metadata.html %}

Udkast
{: .label .label-yellow }

# Arkitektur anbefaling

---


{: .default }
> _Det anbefales at undgå risici for opbygning af **unødvendige vedligeholdelsesomkostninger**, **leverandørafhængigheder** og betydelig **teknisk gæld** ved at genbruge eksisterende standardisereder datamodeller og Open Source komponenter som [NGSI-LD](https://fiware-datamodels.readthedocs.io/en/stable/ngsi-ld_howto/) og [Orion-LD](https://fiware-orion.readthedocs.io/en/master/)_


#### **[NGSI-LD](https://fiware-datamodels.readthedocs.io/en/stable/ngsi-ld_howto/) (Next Generation Service Interface - Linked Data)**

> Den åbne datastandard (specificeret af ETSI), der definerer, hvordan positionsdata i GeoJSON og kontekstdata (f.eks. position, hastighed, status) fra IoT-enheder som GPS devices kan modelleres og udveksles. I praksis betyder det, at flådedata standardiseres, hvilket sikrer interoperabilitet, genbrug og en stærk exit-strategi uafhængig af leverandørforhold.

#### **[Orion-LD](https://fiware-orion.readthedocs.io/en/master/) (Context Broker-software fra FIWARE)**
> Implementerer NGSI-LD standarden. Den fungerer som systemets centrale nerve: den samler data fra alle GPS-enheder og præsenterer dem som en samlet, realtids kontekst til andre service. Ved at bruge Orion-LD sikrer man et skalerbart, driftssikkert kernesystem, hvis vedligeholdelse og udvikling varetages af et internationalt Open Source-fællesskab.

Opsummering: [NGSI-LD](https://fiware-datamodels.readthedocs.io/en/stable/ngsi-ld_howto/) giver standarden, [Orion-LD](https://fiware-orion.readthedocs.io/en/master/) giver implementeringen, og sammen leverer de et fundament, der eliminerer teknisk gæld og vendor lock-in!

# Forventede gevinster
---


### 🚀 Øget effektivitet
> Udviklerne undgår at bruge tid på at kode standard API-kommunikation, provisionering og vedligeholdelse af kerneinfrastruktur. Dette gør det muligt udelukkende at fokusere på den unikke GPS-enheds protokol og virkemåde, hvilket **maksimerer den tid, der bruges på at levere direkte forretningsværdi.**

### 💰 Reduktion af driftsbyrden
> FIWARE Foundation og open source fællesskaberne omkring IoT-Agents og Orion-LD leverer sikkerhedsrettelser og vedligeholdelse af kernekomponenterne. Dette **aflaster driftsbudgettet** for de tunge opgaver med at vedligeholde en egenudviklet infrastruktur-backend.

### 📈 Skalerbarhed og robusthed
> **Orion-LD** er designet til storskala datastrømme, hvilket sikrer, at systemet er **driftssikkert** og kan skaleres **uden dyr omskrivning** senere.

### 🔃 Øget interoperabilitet
> Ved at genbruge bredt anvendte internationale komponenter, bliver det **hurtigere og mere omkostningseffektivt** at tilføje nye enhedstyper eller sammenkoble andre standard analyse-, visualiserings- eller servicesystemer til platformen.

### 🤝 Styrket handlefrihed og exit-strategi
> Valg af veldokumenterede standardløsninger betyder at i tilfælde af hændelser, der fører til leverandørskifte, sikres **kontinuitet**, idet der eksisterer et stort antal leverandører der vil kunne overtage drift og videreudvikling. 

### 🇪🇺 Strategiske alliancer og mulighed for fælles EU finansiering
> Data struktureres efter **ETSI's NGSI-LD-standard**, hvilket sikrer, at flådedata er øjeblikkeligt **let at dele, genbruge og integrere** med andre offentlige myndigheder på tværs af EU. Dette **muliggør deltagelse i tvær-europæiske samarbejder** og skaber potentielle veje til **afledt EU-finansiering** via standardiserede initiativer.

# Anvendte arkitekturprincipper
---
Forslaget er i tråd med de [fællessoffentlige arkitektur principper](https://arkitektur.digst.dk/principper-og-regler) ved at anvende følgende anerkendte internationale principper for software og enterprise arkitektur:

[♻️ Software Reuse & FOSS](https://glossary.cncf.io/portability/){: .btn .btn-green }
[👁️ Open Standards](https://www.etsi.org/technologies/smart-cities/ngsi-ld){: .btn .btn-green }
[🧩 Loose Coupling & Modularity](https://glossary.cncf.io/loosely-coupled-architecture/){: .btn .btn-green }