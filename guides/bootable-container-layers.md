# Bootable Container Image Layers

```mermaid
graph TD
    subgraph base["BaseOS Layer"]
        nornnet["nornnet"]
    end

    subgraph domain["Domain Layer"]
        sikkerselvbetjening["sikkerselvbetjening"]
        domain2["domain-2"]
        domain3["domain-3"]
    end

    subgraph location["Location Config Layer"]
        DOKK1["DOKK1"]
        Bautavej["Bautavej"]
    end

    nornnet ---|"bound to"| sikkerselvbetjening
    nornnet ---|"bound to"| domain2
    nornnet ---|"bound to"| domain3

    sikkerselvbetjening ---|"bound to"| DOKK1
    sikkerselvbetjening ---|"bound to"| Bautavej
    domain2 ---|"bound to"| DOKK1
    domain3 ---|"bound to"| Bautavej
```

## Layer Descriptions

- **BaseOS (nornnet)** — Foundational bootable container image providing the base operating system.
- **Domain** — Mid-tier images providing domain-specific functionality (e.g., `sikkerselvbetjening`, `domain-2`, `domain-3`). Each is logically bound to a BaseOS image.
- **Location Config** — Top-tier images applying site-specific configuration (e.g., `DOKK1`, `Bautavej`). Each is logically bound to one or more domain images.
