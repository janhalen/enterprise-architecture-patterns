---
layout: default
title: "Public Generative AI platform proposal"
summary: "Arkitekturforslag til en minimal platform"
author: "Jan Maack Kjerbye" 
date: "10-11-2025" 
tags: [IoT, FIWARE, NGSI-LD, Genbrug, Standardisering]
status: "Udkast" 
parent: "Proposals"
published: false
---

{% include header_metadata.html %}

Udkast
{: .label .label-yellow }

# Arkitektur anbefaling

---

> ### Det anbefales at undgå risici for opbygning af **unødvendige vedligeholdelsesomkostninger**, **leverandørafhængigheder** og betydelig **teknisk gæld** -- ved at starte med en minimal "Core stack" og genbruge eksisterende standardisereder Open Source komponenter.
>

---
## Komponenter
---

```mermaid
flowchart LR
 subgraph AIPlatform["AI Platform core"]
        OpenWebUI_F["OpenWebUI FRONTEND Svelte"]
        OpenWebUI_B["OpenWebUI BACKEND FastAPI"]
        Postgres["Postgres<br>Application Data"]
        VLLM_Mistral["vLLM<br>Inference Engine"]
  end
 subgraph s1["Platform"]
        n1["Large Language<br>Model"]
        SSO_OIDC["OS2Adgang<br>OIDC Provider"]
  end
 subgraph s2["AddOn features"]
        n2["Improved<br>document extraction"]
  end
    OpenWebUI_F <--> OpenWebUI_B
    OpenWebUI_B --> Postgres & VLLM_Mistral
    SSO_OIDC --> OpenWebUI_F
    VLLM_Mistral --> n1
    AIPlatform --- s2
    Postgres@{ shape: cyl}
    VLLM_Mistral@{ shape: diam}
    n1@{ shape: event}
    SSO_OIDC@{ shape: decision}
     OpenWebUI_F:::Rose
     OpenWebUI_B:::Rose
     Postgres:::Ash
     VLLM_Mistral:::Ash
     n1:::Peach
     SSO_OIDC:::Aqua
    classDef SGRON fill:#e6ffe6, stroke:#006600, stroke-width:2px 
    classDef RED fill:#ffe6e6, stroke:#cc0000, stroke-width:2px
    classDef ORANGE fill:#fff2e6, stroke:#ff9900, stroke-width:2px
    classDef YRAG fill:#fffacd, stroke:#cc9900, stroke-width:2px 
    classDef GRAY fill:#e0e0e0, stroke:#666666, stroke-width:2px 
    classDef LVL fill:#f5e6ff, stroke:#9933cc, stroke-width:2px
    classDef Aqua stroke-width:1px, stroke-dasharray:none, stroke:#46EDC8, fill:#DEFFF8, color:#378E7A
    classDef Peach stroke-width:1px, stroke-dasharray:none, stroke:#FBB35A, fill:#FFEFDB, color:#8F632D
    classDef Ash stroke-width:1px, stroke-dasharray:none, stroke:#999999, fill:#EEEEEE, color:#000000
    classDef Rose stroke-width:1px, stroke-dasharray:none, stroke:#FF5978, fill:#FFDFE5, color:#8E2236
    style AIPlatform fill:LightBlue,stroke:none
    style s1 fill:#C8E6C9,stroke:none
    linkStyle 5 stroke:none,fill:none
```



#### **[OpenWebUI](https://) (TBD)**

> Den UI

#### **[OS2Adgang](https://fi) (Based on KeyCloak provider)**
> Implementerer 

#### **[vLLM](https://q) (Inference Engine)**
> en **Time Series Database** Modulet er kritisk for at sikre **historisk lagring** uden at belaste Context Brokeren.

Opsummering:

# Forventede gevinster
---


### 🚀 ---
> Gevinst


