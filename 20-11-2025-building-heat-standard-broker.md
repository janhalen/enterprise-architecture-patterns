---
layout: default
title: "" # [🔖 Titel på indsats eller forslag]
author: "" # [Navn på forfatter]
date: "" # [Dato for oprettelse]
tags: [] # [Liste over relevante tags]
status: "" # [Status: Udkast, Godkendt, etc.]
parent: "Proposals"
published: false
---

{% include header_metadata.html %}

Udkast  
{: .label .label-yellow }

## Baggrund

<!-- [Beskriv den kontekst eller problemstilling, som dokumentet adresserer.] -->
<!-- [Hvad er de nuværende udfordringer, og hvorfor er der behov for denne indsats?] -->

# Arkitektur anbefaling

---

> ### Det anbefales at sammensætte en robust, genbrugelig løsning der er kosteffektiv at vedligeholde ved at anvende eksisterende løsninger og datastandarder

## Komponenter
_Arkitekturlandskab_

---

Højniveau arkitekturlandskab i mermaid
```mermaid
flowchart LR
    S1>"Indendørs sensorer"] --> A1("IoT Agent<br>-Producer-")
    S2["Vejrdata API<br>(DMI)"] --> n1["Context Provider<br>-Producer-"]
    A1 -- "Inde temperatur<br>- NGSI-LD -" --> C("Orion-LD<br>Context Broker")
    C -- Notify --> AI["Predictive Heating Service<br>-Consumer-"] & QL["QuantumLeap<br>-Consumer-"] & n3["IoT Agent<br>- Modbus bridge -"]
    QL --> TS["Historisk Data<br>- TimeSeries -<br>State-store"]
    QL --- n2["Grafisk<br>Overbliks flade"]
    QL -. Subscribe .-> C
    n1 -- "Ude temperatur<br>- NGSI-LD -" --> C
    AI -. Subscribe .-> C
    n3 -- Modbus --> HVAC["Varmekontrolsystem<br>(API modtager)"]
    n3 -. Subscribe .-> C
    S2@{ shape: das}
    n1@{ shape: rounded}
    QL@{ shape: rounded}
    n3@{ shape: rounded}
    TS@{ shape: cyl}
    n2@{ shape: display}
     S1:::Ash
     A1:::Sky
     S2:::Ash
     n1:::Peach
     C:::Sky
     AI:::Peach
     QL:::Sky
     n3:::Peach
     TS:::Sky
     n2:::Peach
     HVAC:::Ash
    classDef Aqua fill:#e0f7fa,stroke:#006064,stroke-width:2px
    classDef Ash stroke-width:1px, stroke-dasharray:none, stroke:#999999, fill:#EEEEEE, color:#000000
    classDef Sky stroke-width:1px, stroke-dasharray:none, stroke:#374D7C, fill:#E2EBFF, color:#374D7C
    classDef Peach stroke-width:1px, stroke-dasharray:none, stroke:#FBB35A, fill:#FFEFDB, color:#8F632D

```
#### **[NGSI-LD](https://fiware-datamodels.readthedocs.io/en/stable/ngsi-ld_howto/) (Next Generation Service Interface - Linked Data)**

> Den åbne datastandard (specificeret af ETSI), der definerer, hvordan 

#### **[Komponent A](https://link/) (Beskrivende linktekst)**

> Komponent A beskrivelse

OSS Datamodel imod Danfoss ECL: https://github.com/smart-data-models/dataModel.Device/blob/master/Modbus/README.md

Tutorial example: https://ngsi-ld-tutorials.readthedocs.io/en/latest/time-series-data.html

Opsummering: <!-- komponent opsummering med links -->

# Forventede gevinster
---


### <!-- f.eks 💰 Reduktion af driftsbyrden -->
> Brødtekst med **effekten** i bold


# Anvendte arkitekturprincipper
