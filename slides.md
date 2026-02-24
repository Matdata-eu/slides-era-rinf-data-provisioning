---
theme: default
title: "ERA RINF Data Provisioning Workshop"
info: |
  Hands-on workshop for Infrastructure Managers and National Registration Entities.
  25 February 2026 · European Union Agency for Railways
highlighter: shiki
lineNumbers: false
drawings:
  persist: false
transition: slide-left
class: text-center
mdc: true
background: /assets/background.png
---

<img src="/assets/European_Union_Agency_for_Railways_logo.svg" class="h-14 absolute top-6 left-6" />

# RINF Data Provisioning Workshop

### Training for Infrastructure Managers & NREs

<div class="text-gray-400 mt-4">
📅 25 February 2026 &nbsp;·&nbsp; 09:30 – 17:00
</div>

<!--
Welcome everyone! Good morning and thank you for joining us today.

This is a full-day hands-on workshop. We'll go from legal context and background to your hands on a keyboard uploading data to the ERA Dataset Manager.

The goal: by end of day everyone can independently provision RINF data as RDF and validate it.
-->

---
layout: default
---

# Today's Agenda 📋

<div class="grid grid-cols-2 gap-4 mt-2 text-sm">
<div>

| Time | Session |
|------|---------|
| 09:00 | ☕ Coffee & Networking |
| 09:30 | 👋 Welcome & Introductions |
| 10:00 | 🌐 The ERA Data Ecosystem |
| 10:30 | 🔍 ERA Data Portal Tour |
| 11:00 | ☕ Coffee Break |
| 11:15 | 🧩 RINF Ontology |
| 12:00 | 🗂️ Dataset Example |
| 12:30 | 🍽️ Lunch |

</div>
<div>

| Time | Session |
|------|---------|
| 13:30 | ⚙️ Data Provisioning Workflow |
| 14:45 | ☕ Coffee Break |
| 15:00 | ✅ SHACL Validation |
| 16:00 | 🔑 Access, Help & Issues |
| 16:30 | 💬 Q&A & Open Discussion |
| 16:50 | 🎯 Wrap-up & Next Steps |
| 17:00 | 🏁 End |

</div>
</div>

<!--
We have a packed day. Key principle: slides are the backdrop — we'll spend a lot of time in real code and repositories.

This deck is designed to be reference material too — every concept we cover is here so you can revisit it afterwards.
-->

---
layout: section
---

# 👋 Welcome & Introductions

### 09:30 – 10:00

<div class="absolute bottom-6 left-0 right-0 text-center text-xs text-gray-400">
  <span class="font-semibold text-white">① Welcome</span> · ② Ecosystem · ③ Portal · ④ Ontology · ⑤ Dataset · ⑥ Pipeline · ⑦ SHACL · ⑧ Access · ⑨ Q&A
</div>

<!--
30 minutes for welcome and round-table introductions.
-->

---
layout: default
---

# Workshop Objectives 🎯

By the end of today you will be able to:

<v-clicks>

- 🗺️ **Navigate** the ERA Data Interoperability Portal
- 📄 **Prepare** datasets according to RINF ontology v3.1
- ⚙️ **Use** the Dataset Manager pipeline for data provisioning
- ✅ **Perform** SHACL validation and interpret results
- 🔧 **Troubleshoot** common errors and validation issues
- 🆘 **Access** support resources and report issues effectively
- ✨ **Be amazed** by the possibilities of a railway topology

</v-clicks>

<!--
These are the 7 concrete objectives. At the end of the day we'll briefly revisit these to check off what we covered.

Key message: this is not a theoretical lecture. We will get our hands dirty.
-->


---
layout: section
---

# 🌐 Understanding the ERA Data Ecosystem

### 10:00 – 10:30

<div class="absolute bottom-6 left-0 right-0 text-center text-xs text-gray-400">
  ① Welcome · <span class="font-semibold text-white">② Ecosystem</span> · ③ Portal · ④ Ontology · ⑤ Dataset · ⑥ Pipeline · ⑦ SHACL · ⑧ Access · ⑨ Q&A
</div>

<!--
30 minutes covering legal context, why RDF, and terminology.
Split: ~10 min legal, ~15 min why RDF, ~5 min terminology/quiz.
-->

---
layout: two-cols
---

# ⚖️ Legal Framework

**Three directives drive RINF data provision:**

<v-clicks>

- 📜 **EU 2019/773** — RINF Regulation  
  _Infrastructure managers **must** submit data_

- 🔗 **EU 2016/797** — Interoperability Directive  
  _Data must follow TSI requirements_
  _Compliance can be machine-verified via SHACL_

- 📂 **EU 2019/1024** — Open Data Directive  
  _Infrastructure data must be open and reusable_

</v-clicks>

::right::

<div class="mt-12">
<v-click>

**ERA's mandate:**

- Maintain the ontology, SHACL shapes, SKOS vocabularies
- Validate and publish submitted data
- Provide tooling for submission and querying

</v-click>

<v-click>

> 🗓️ **Deadline: 31 March 2026**  
> All data providers must submit RINF data  
> in RDF format (ontology v3.1)

</v-click>
</div>

<!--
The legal context is important — this is not optional. Infrastructure managers are legally required to provide this data.

The Open Data directive means the data, once submitted, becomes public. This is a feature, not a bug: it enables route compatibility tools, journey planners, and infrastructure research.

ERA's role: they don't just collect data — they maintain the entire technical standard (ontology + SHACL + vocabularies).
-->

---
layout: default
---

# 📅 RINF RDF Transition Timeline

```mermaid
gantt
    dateFormat YYYY-MM-DD
    title RINF RDF Transition Timeline
    tickInterval 1year

    section Legal Basis
    RINF Regulation 2019/773             :done, rinf19, 2019-06-17, 2019-07-01
    Open Data Directive 2019/1024        :done, odd19, 2019-06-20, 2019-07-01

    section ERA Ontology Evolution
    Ontology v3.0 (RDF transition)       :done, v30, 2023-01-01, 2024-12-31
    Ontology v3.1 (current)              :active, v31, 2025-01-01, 2026-03-31
    Application guide published   :crit, milestone, 2025-03-31, 2025-03-31

    section ★ Deadline
    RDF v3.1 Submission Due (31 March)   :crit, milestone, 2026-03-31, 2026-04-01
    Digital Routebook based on RINF      :crit, milestone, 2027-03-31, 2027-04-01
    Digital Rulebook & Routebook         :crit, milestone, 2028-03-31, 2028-04-01
```
<v-click>

> 🗓️ **Deadline: 31 March 2026**  
> All data providers must submit RINF data  
> in RDF format (ontology v3.1)

</v-click>
<!--
Key takeaway from this timeline:
- The legal mandate has existed since 2019
- The technical specification (ontology) has been evolving
- We are NOW in the final stretch before the mandatory deadline
- Routebook and rulebook come next!

Where are we today? February 2026 — 5 weeks before the deadline.
-->

---
layout: default
---

# 🤔 Why RDF? Smart Standardisation

```mermaid
graph LR
    A["🔑 IRIs<br/>How to identify data"] --> B["🔗 RDF<br/>How to structure data"]
    B --> C["📚 Ontology<br/>How to give meaning"]
    C --> D["✅ SHACL<br/>How to define constraints"]

    style A fill:#1a3a5c,color:#fff,stroke:#4a90d9
    style B fill:#1a5c3a,color:#fff,stroke:#4ad990
    style C fill:#5c3a1a,color:#fff,stroke:#d9904a
    style D fill:#5c1a3a,color:#fff,stroke:#d94a90
```

<ul class="mt-4 text-sm text-left space-y-2">
<li v-click><div class="bg-blue-900 rounded p-2"><strong>🔑 IRIs</strong> — Dereferencable globally unique identifiers. No more local IDs that clash across systems.</div></li>
<li v-click><div class="bg-green-900 rounded p-2"><strong>🔗 RDF</strong> — Subject–predicate–object triples. Graph, not hierarchy.</div></li>
<li v-click><div class="bg-orange-900 rounded p-2"><strong>📚 OWL Ontology</strong> — Classes, properties, semantics. Machine-readable meaning.</div></li>
<li v-click><div class="bg-pink-900 rounded p-2"><strong>✅ SHACL</strong> — Validation constraints. Compliance is machine-verifiable. Also useful for building UIs and search engines.</div></li>
</ul>

<!--
This is the key insight: the EU (and ERA) chose RDF not just to be modern, but because each layer solves a real problem.

- IRIs: no more "our station ID is 42, theirs is 42 too but they're different stations"
- RDF: a graph model naturally fits railway networks — stations connect to tracks, tracks connect to signals
- OWL Ontology: the schema accompanies the data. New consumers can understand old data.
- SHACL: instead of writing custom validation code, you declare constraints and any validator can check them.

Real benefit: ERA can download a dataset from any IM and validate it with the same SHACL shapes. No custom parsing per IM.
-->

---
layout: default
---

# 📊 RDF vs XML

| Aspect | **XML** | **RDF** |
|--------|---------|---------|
| Data model | Hierarchical tree 🌲 | Graph — triples 🕸️ |
| Identity | Element nesting | Global URI for every resource |
| Validation | XSD | SHACL |
| Querying | XPath / XQuery | SPARQL |
| Linkability | Difficult (XLink) | Native: URIs link across datasets |
| Merging | Trees don't merge | Trivial: union of triple sets |


<!--
The biggest practical difference: XML IDs are local. When you want to reference data from another IM or another system, you need agreed mapping tables. With RDF, the URI IS the identifier — no mapping needed.

This is exactly what RINF needs: 30+ countries, ~600 infrastructure managers, one shared graph.
-->

---
layout: default
---

# 🔍 SPARQL vs REST JSON API

| Aspect | **REST JSON API** | **SPARQL over RDF** |
|--------|-------------------|---------------------|
| Querying | One endpoint per resource type | Any query over the full graph |
| Cross-dataset joins | Requires custom code | Native — federated queries across IMs |
| Identifiers | Opaque local IDs, mapping tables needed | Global URIs — universal, no mapping |
| Schema | Lives in documentation | Accompanies the data (ontology) |
| Extensibility | New fields require API versioning | Add triples without restructuring |
| Setup cost | Custom development per endpoint | No development — graph is the endpoint |

<!--
Key message: a REST API is a contract between two systems. SPARQL is a standard interface over any RDF graph — no bespoke development, no custom endpoint per question.

Real example: "give me all tunnels longer than 500m in the Benelux with their max speed" — one SPARQL query across datasets from BE, NL, LU. With REST APIs you'd need three different API calls, three different schemas, and custom code to merge them.
-->


---
layout: default
---

# 🚂 The Railway Data Problem

We have such a beautiful system…

<img src="./assets/railway-reality-dark.svg" class="max-h-80 w-full object-contain" />

---
layout: default
---

# 🚂 The Railway Data Problem

But we decided to break it into pieces we call "use cases"…

<img src="./assets/railway-reality-dark-silos.svg" class="max-h-80 w-full object-contain" />


---
layout: default
---

# 🤔 How do we glue the pieces back together?

<div class="grid grid-cols-2 gap-6 mt-4">
<div>

**The challenge:**
<v-clicks>

- 🗂️ Siloed data models, historically home grown
- 📍 Multiple coordinate systems
- 🔀 Hierarchical + network structure
- ⏰ Temporal validity
- 🌍 Cross-border IMs

</v-clicks>

</div>
<div v-click>

> _"If there is not enough autonomy, an organisation will be slow to adapt. But with too much autonomy and not enough cohesion, it will grow silos that pursue their own continuation at the expense of the whole._
>
> _Can you have freedom and keep everything working together at the same time?"_
>
> https://essentialbalances.com/

<div class="mt-4 p-3 bg-blue-900 rounded text-sm">

**Answer: Linked Data = standardisation**

- 🔑 Use **IRIs** as globally unique identifiers
- 🔗 Use **RDF** to structure data
- 📚 Reuse **ontologies** for shared meaning
- And... don't give up!

</div>

</div>
</div>

<!--
This is the core motivation for RDF in RINF.

Societies create traffic rules to allow individual freedom while maintaining safe, efficient cohesion. Track design follows standards to form a coherent network. Data needs the same.

Linked Data as the "traffic rules" of data: every organisation can build their own systems, but IRIs, RDF and shared ontologies create the cohesion that makes cross-border integration possible.

This is exactly why ERA chose RDF — not because it's fashionable, but because it's the standardisation layer that makes 600+ infrastructure managers' data work together.
-->

---
layout: default
---

# 🏗️ Where RDF Fits in Your Architecture

```mermaid
flowchart LR
    IS["🗄️ Internal Systems<br/>DB / GIS / Asset Management / Telematics"] --> ETL

    ETL["⚙️ RDF Generation<br/>SPARQL-Anything · R2RML · Python · OTTR"] --> POST

    POST["🔧 Post-Processing<br/>SPARQL UPDATE · Python · SHACL Rules"] --> GRAPH

    GRAPH["📄 ERA-compliant RDF<br/>.ttl / .nt"] --> VAL
    GRAPH --> DM
    GRAPH --> LDES

    VAL["✅ SHACL Validation<br/>Local · EU Test Bed"] -->|"fix issues"| GRAPH

    DM["📤 Dataset Manager<br/>Full or Partial Upload"] --> KG

    LDES["📡 LDES Publication<br/>Event-Driven Streaming"] --> KG

    KG["🌐 ERA Knowledge Graph<br/>Public SPARQL Endpoint"]

    style IS fill:#2d3748,color:#e2e8f0
    style KG fill:#1a365d,color:#e2e8f0
    style VAL fill:#276749,color:#e2e8f0
```

<!--
You don't need to abandon your existing systems. Your internal DB, GIS, and asset management systems stay as-is.

You add an RDF generation step — a transformation layer — that converts your data to ERA-compliant RDF.

The key insight: validate BEFORE you upload. Local SHACL validation gives you fast feedback. The Dataset Manager also validates, but it's slower to iterate.

The LDES option is for the future: rather than batch uploads, stream changes incrementally.
-->

---
layout: default
---

# 📖 Terminology Quick Reference

<div class="grid grid-cols-3 gap-3 text-sm">
<div>

**Organisations & Roles**
- **ERA** — EU Agency for Railways
- **IM** — Infrastructure Manager
- **NRE** — National Registration Entity
- **RCC** — Route Compatibility Check

**Registers**
- **RINF** — Register of Infrastructure
- **ERATV** — European Register of Authorised Types of Vehicles

</div>
<div>

**Data Standards**
- **RDF** — Resource Description Framework
- **TTL** — Turtle (RDF format)
- **SPARQL** — RDF query language
- **KG** — Knowledge Graph
- **URI** — Uniform Resource Identifier
- **IRI** — Internationalised Resource Identifier

**Validation**
- **SHACL** — Shapes Constraint Language
- **SKOS** — Simple Knowledge Org. System

</div>
<div>

**Infrastructure**
- **OP** — Operational Point (station, junction, ...)
- **SoL** — Section of Line
- **TSI** — Technical Specification for Interoperability
- **TEN-T** — Trans-European Transport Network
- **ETCS** — European Train Control System

**Topology**
- **NE** — LinearElement (NetElement)
- **NR** — NetRelation
- **LRS** — Linear Referencing System

</div>
</div>

<!--
This is a reference slide — don't read it out loud. Point people to it and let them take a photo.

You'll hear these abbreviations throughout the day. If something is unclear, ask!

Quick quiz idea: show the abbreviation, ask room to call out the full term.
-->

---
layout: section
---

# 🔍 ERA Data Portal Tour

### 10:30 – 11:00

**https://data-interop.era.europa.eu/**

<div class="absolute bottom-6 left-0 right-0 text-center text-xs text-gray-400">
  ① Welcome · ② Ecosystem · <span class="font-semibold text-white">③ Portal</span> · ④ Ontology · ⑤ Dataset · ⑥ Pipeline · ⑦ SHACL · ⑧ Access · ⑨ Q&A
</div>

<!--
30 minutes touring the ERA Data Interoperability Portal.
Switch to browser: open https://data-interop.era.europa.eu/
We will navigate through each application live.
-->

---
layout: two-cols
---

# 🖥️ Portal Applications

**Navigate to: https://data-interop.era.europa.eu/**

<v-clicks>

1. **🔎 Search Form**
   - Search OPs and sections of line
   - Advanced filters and export
   - 💡 *Get the SPARQL query behind results*

2. **🗺️ Map Explorer**
   - Interactive rail infrastructure map
   - Visualise track characteristics

3. **🚆 Route Compatibility Check**
   - Vehicle + route compatibility
   - Uses ERATV vehicle data
   - ⚠️ _Currently limited — workgroup active_

</v-clicks>

::right::

<v-clicks>

4. **📦 Dataset Explorer**
   - Browse published datasets
   - Metadata and provenance
  
</v-clicks>

<div class="mt-16 text-sm">

**💡 Hands-on tip:**

> In the Search Form, run a query and look for  
> the "Show SPARQL" option. This reveals the  
> exact SPARQL query behind the filter — great  
> for learning the data model.

</div>

<!--
Live demo in browser:
1. Show Search Form: search for "Hamburg" operational points, show SPARQL button
2. Show Map Explorer: zoom to a country, click a track to see its properties
3. Briefly show RCC — mention it's being reviewed by a working group
4. Show Dataset Explorer — show a recently uploaded dataset

Key message: these are the CONSUMER applications. As data providers, you feed this system.
-->

---
layout: two-cols
---

# 📚 Portal Resources

<v-clicks>

1. **📖 Data Stories**
   - Real use cases and best practices
   - Examples from other submissions

2. **🧬 Vocabulary / Ontology**
   - ERA RINF ontology structure
   - Key classes, properties, version

3. **⚡ SPARQL Endpoint**
   - Direct query access
   - 💡 Use [Yasgui](https://yasgui.matdata.eu/) for better UX
  
</v-clicks>

::right::


<v-clicks>

1. **📤 Data Provisioning**
   - Introduction to Dataset Manager
   - Links to user manual
  
</v-clicks>



<div class="mt-4 text-sm">

**Useful links:**

| Resource | URL |
|---|---|
| Portal | [data-interop.era.europa.eu](https://data-interop.era.europa.eu/) |
| Application Guide | [rinf-appGuide](https://data-interop.era.europa.eu/era-vocabulary/rinf-appGuide/) |
| ERA GitLab | [era-ontology](https://gitlab.com/era-europa-eu/public/interoperable-data-programme/era-ontology/era-ontology) |
| UAT Environment | [uat.ld4rail...](https://uat.ld4rail.fpfis.tech.ec.europa.eu/) |
| User Manual | [RINF User Manual](https://data-interop.era.europa.eu/RINF-User%20Manual%20v2.0.pdf) |

</div>

<!--
SPARQL tip: the ERA-provided SPARQL interface is functional but basic. The Yasgui instance at yasgui.matdata.eu offers autocomplete, result table downloads, and history — much better for day-to-day work.

GitLab is where all the source material lives: ontology OWL files, SHACL shapes, SKOS concept schemes, and the issue tracker for reporting problems.
-->

---
layout: center
class: text-center
---

# ☕ Coffee Break

### 11:00 – 11:15

<div class="text-6xl mt-4">☕</div>

_Back in 15 minutes for the ontology deep-dive_

---
layout: section
---

# 🧩 RINF Ontology

### 11:15 – 12:30

<div class="absolute bottom-6 left-0 right-0 text-center text-xs text-gray-400">
  ① Welcome · ② Ecosystem · ③ Portal · <span class="font-semibold text-white">④ Ontology</span> · ⑤ Dataset · ⑥ Pipeline · ⑦ SHACL · ⑧ Access · ⑨ Q&A
</div>

<!--
75 minutes. Most technical section of the morning.
-->


---
layout: default
---

# 🗺️ What We'll Cover

<div class="grid grid-cols-3 gap-4 mt-4 text-sm">

<div class="bg-gray-800 rounded p-3">

**🏢 Organisation**
- `era:Body` + `era:OrganisationRole` (v3.1)

**🛤️ Topology**
- `LinearElement` + geometry
- `NetRelation` + navigability
- Worked example

**📏 Positioning**
- `NetPointReference`
- `NetLinearReference`
- `NetAreaReference`
- GeoSPARQL geometry
- Linear Referencing (KPs)

</div>

<div class="bg-gray-800 rounded p-3">

**🏗️ Infrastructure Elements**
- Overview & base pattern
- `OperationalPoint`
- `SectionOfLine`
- `Track` & functional resources
- `Signal` / `Switch`
- `Tunnel` / `Bridge`
- `LevelCrossing` / `PlatformEdge` / `KilometricPost` / `PrimaryLocation`

</div>

<div class="bg-gray-800 rounded p-3">

**📐 Patterns & Best Practices**
- Open World Assumption
- Temporal validity (`era:validity`)
- Functional Resources: TDS, CLS, ETCS

**🔀 Special Cases**
- Border Points
- Documents
- `era:hasPart` (inferred)

</div>
</div>

<!--
Overview of the ontology chapter. Walk through this quickly — it sets expectations for the next 75 minutes.
-->


---
layout: default
---

# 🏢 Organisation (Infrastructure Manager)

<div class="text-sm mt-3">

The `era:infrastructureManager` property on all infrastructure elements (Tracks, OPs, Signals …) points to the **`era:OrganisationRole`** instance, not directly to the `era:Body`.

</div>


<div class="grid grid-cols-2 gap-3 text-sm">

<div>
```turtle
# ✅ v3.1 pattern
<era:organisations/0076> a era:Body ;
    era:organisationCode "0076" ;
    era:role <era:organisations/0076_IM> ;
    rdfs:label "Bane NOR"@no .

<era:organisations/0076_IM> a era:OrganisationRole ;
    era:hasOrganisationRole
      <era:concepts/organisation-roles/IM> ;
    era:roleOf <era:organisations/0076> .
```

</div>

<div class="p-2 bg-red-900 rounded text-sm mt-4">

❌ **Deprecated (v3.0):** `era:InfrastructureManager` + `era:imCode`  
✅ **Required (v3.1):** `era:Body` + `era:OrganisationRole`

</div>

</div>

<div class="mt-4">

```mermaid
graph LR
    body["era:Body<br/>'Bane NOR'<br/>organisationCode: 0076"]
    role["era:OrganisationRole<br/>0076_IM"]
    concept["SKOS Concept<br/>organisation-roles/IM"]
    body -->|"era:role"| role
    role -->|"era:hasOrganisationRole"| concept
    role -->|"era:roleOf"| body
```

</div>

<!--
The organisation pattern changed significantly in v3.1.

The key rule: infrastructureManager on tracks/OPs/etc points to the OrganisationRole, not the Body.
-->

---
layout: default
---

# �️ Topology: LinearElements

**LinearElements** are the atoms of the network topology — each represents a track segment between two connection points (switches, buffer stops, etc.). They have an origin and an end. They are directed.

```turtle
<_:NE001> a era:LinearElement ;
    era:length 500.0 .     # metres — optional but recommended
```

A geometry is attached with GeoSPARQL **`gsp:hasGeometry`**. Only 1 allowed in current SHACL...

```turtle
<_:NE001> a era:LinearElement ;
    era:length 500.0 ;
    gsp:hasGeometry [          # real-world WGS84 LINESTRING
        a gsp:Geometry ;
        rdfs:label "WGS84"@en ;
        gsp:asWKT "LINESTRING(7.4520 51.5100, 7.4620 51.5148)"
            ^^gsp:wktLiteral
    ] .
```

<!--
LinearElements are the atoms: each represents a track segment between two connection points (switches, buffer stops, etc).

gsp:hasGeometry can only appear ones and should be WGS84, longitude first.
-->

---
layout: default
---

# �️ Topology: LinearElements with multiple geometries

But what about schematic coordinates? A schematic visualisation? 

```turtle
<_:NE001> a era:LinearElement ;
    era:length 500.0 ;
    gsp:hasGeometry [          # real-world WGS84 LINESTRING
        a gsp:Geometry ;
        rdfs:label "WGS84"@en ;
        gsp:asWKT "LINESTRING(7.4520 51.5100, 7.4620 51.5148)"
            ^^gsp:wktLiteral
    ] ;
    gsp:hasGeometry [          # separate schematic-diagram geometry
        a gsp:Geometry ;
        rdfs:label "Schematic"@en ;
        gsp:asWKT "<https://data.example.eu/schematic/0/> LINESTRING(0 0, 500 0)"^^gsp:wktLiteral
    ] .
```

<!--
GeoSPARQL doesn't limit the number of gsp:hasGeometry on a gsp:Feature. 

gsp:hasGeometry can appear multiple times on the same element — e.g. one WGS84 LINESTRING for GIS tools and a separate schematic LINESTRING for diagram rendering.

Everything else — signals, tracks, operational points — positions itself ON the topology using netReference. And there could be an automatic calculation of their coordinates in the different coordinate systems.
-->

---
layout: default
---

# 🔗 Topology: NetRelations

**NetRelations** connect `LinearElements` at their endpoints, defining navigability.

```turtle
<_:NR001> a era:NetRelation ;
    era:elementA <_:NE001> ; era:isOnOriginOfElementA false ;   # end of NE001
    era:elementB <_:NE002> ; era:isOnOriginOfElementB true ;    # start of NE002
    era:navigability <era:concepts/navigabilities/Both> .
```

<div class="grid grid-cols-2 gap-4 mt-4 text-sm">
<div class="bg-gray-800 rounded p-3">

**`isOnOriginOfElement`**
- `true` = connects at the **start** of the element
- `false` = connects at the **end** of the element

</div>
<div class="bg-gray-800 rounded p-3">

**`navigability` values**
- `Both` — bidirectional
- `AB` — only A → B
- `BA` — only B → A
- `None` — physically connected, not traversable

</div>
</div>

<!--
NetRelations connect LinearElements at their endpoints. The isOnOriginOf flags determine which end connects where.

Navigability: Both = bidirectional, AB = only A→B, BA = only B→A, None = not navigable (physically connected but not traversable, e.g., bumper only).
-->

---
layout: two-cols
---

# 🗺️ Topology: LinearElements & NetRelations — Worked Example

```mermaid
graph LR
    NE001["🛤️ LinearElement<br/>NE001 · 500 m"] -->|"NR001 · Both"| NE002["🛤️ LinearElement<br/>NE002 · 300 m"]
    NE002 -->|"NR002 · Both"| NE003["🛤️ LinearElement<br/>NE003 · 400 m"]
    NE001 -->|"NR003 · Both"| NE003
```

<img src="./assets/netelements-relations-dark.svg" class="max-h-44 w-full object-contain mt-2" />

::right::

```turtle
<_:NE001> a era:LinearElement ; era:length 500.0 .
<_:NE002> a era:LinearElement ; era:length 300.0 .
<_:NE003> a era:LinearElement ; era:length 400.0 .

# NE001 end ──── NE002 start
<_:NR001> a era:NetRelation ;
    era:elementA <_:NE001> ;
    era:isOnOriginOfElementA false ;  # end of NE001
    era:elementB <_:NE002> ;
    era:isOnOriginOfElementB true ;   # start of NE002
    era:navigability
        <era:concepts/navigabilities/Both> .

# NE002 end ──── NE003 start
<_:NR002> a era:NetRelation ;
    era:elementA <_:NE002> ;
    era:isOnOriginOfElementA false ;
    era:elementB <_:NE003> ;
    era:isOnOriginOfElementB true ;
    era:navigability
        <era:concepts/navigabilities/Both> .

# NE001 end ──── NE003 start  (junction/branch)
<_:NR003> a era:NetRelation ;
    era:elementA <_:NE001> ;
    era:isOnOriginOfElementA false ;
    era:elementB <_:NE003> ;
    era:isOnOriginOfElementB true ;
    era:navigability
        <era:concepts/navigabilities/Both> .
```

<!--
This is the worked example for the previous two slides.
NE001 branches at its end (isOnOriginOfElementA=false) into both NE002 and NE003 — a classic junction/switch topology.

The SVG shows the same network: you can see the branching at the right end of NE001.
-->

---
layout: default
---

# 📏 Positioning: NetPointReference

Used by **point elements**: Signals, Switches, Level Crossings, Kilometric Posts, stopping-point Operational Points.

```mermaid
graph LR
    sig["🚦 era:Signal<br/>SIG001"]
    npr["era:NetPointReference"]
    tc["era:TopologicalCoordinate<br/>offsetFromOrigin: 250.0 m"]
    ne["🛤️ era:LinearElement<br/>NE001 · 500 m total"]
    sig -->|"era:netReference"| npr
    npr -->|"era:hasTopoCoordinate"| tc
    tc -->|"era:onLinearElement"| ne
```


```turtle
<_:SIG001> a era:Signal ;
    era:netReference <_:NPR_SIG001> .

<_:NPR_SIG001> a era:NetPointReference ;
    era:hasTopoCoordinate <_:TC_SIG001> .

<_:TC_SIG001> a era:TopologicalCoordinate ;
    era:onLinearElement <_:NE001> ;
    era:offsetFromOrigin 250.0 .   # metres from origin

# Optional: LRS (kilometric) coordinate
<_:NPR_SIG001> era:hasLrsCoordinate [
    a era:LinearPositioningSystemCoordinate ;
    era:kmPost <_:KP_LPS01_km125> ;
    era:offsetFromKilometricPost 37.5   # metres
] .
```

<div class="text-xs mt-2 text-gray-400">



</div>

<!--
The topology coordinate is the most important. It places the element precisely on the network graph.

NetPointReference = one LinearElement, one offset. The simplest case.


**Topological coordinate — mandatory**

**LRS coordinate — optional**

`offsetFromOrigin` is in **metres** from the origin end of the LinearElement.  
The LRS coordinate is independent — both can coexist on the same NetPointReference.
-->

---
layout: default
---

# 📏 Positioning: NetLinearReference

Used by **linear elements**: RunningTrack, Siding, PlatformEdge, single-track Tunnel/Bridge.

```mermaid
graph LR
    trk["🛤️ era:RunningTrack<br/>TRK001"]
    nlr["era:NetLinearReference"]
    ne1["🛤️ LinearElement NE001<br/>500 m"]
    ne2["🛤️ LinearElement NE002<br/>300 m"]
    ne3["🛤️ LinearElement NE003<br/>700 m"]
    spt["era:NetPointReference<br/>(startsAt)"]
    ept["era:NetPointReference<br/>(endsAt)"]
    tcs["era:TopologicalCoordinate<br/>offsetFromOrigin: 50.0 m"]
    tce["era:TopologicalCoordinate<br/>offsetFromOrigin: 400.0 m"]
    trk -->|"era:netReference"| nlr
    nlr -->|"era:hasSequence ①"| ne1
    nlr -->|"era:hasSequence ②"| ne2
    nlr -->|"era:hasSequence ③"| ne3
    nlr -->|"era:startsAt"| spt
    nlr -->|"era:endsAt"| ept
    spt -->|"era:hasTopoCoordinate"| tcs
    ept -->|"era:hasTopoCoordinate"| tce
    tcs -.->|"era:onLinearElement"| ne1
    tce -.->|"era:onLinearElement"| ne3
```

```turtle
<_:TRK001> a era:RunningTrack ;
    era:netReference <_:NLR_TRK001> .

<_:NLR_TRK001> a era:NetLinearReference ;
    # ordered sequence of LinearElements spanned
    era:hasSequence ( <_:NE001> <_:NE002> <_:NE003> ) ;
    era:startsAt :NPR_START ;
    era:endsAt :NPR_END .
```

<!--
The sequence is an ordered rdf:List of LinearElements the track spans.
startsAt and endsAt carry full NetPointReference/TopologicalCoordinate chains to express the precise offset within the first and last LinearElement.
-->

---
layout: default
---

# 📏 Positioning: NetAreaReference

Used by **aggregate elements**: OperationalPoints, Sections of Line, multi-track Tunnels/Bridges.

```mermaid
graph LR
    op["🚉 era:OperationalPoint<br/>OP001"]
    nar["era:NetAreaReference"]
    nlr1["era:NetLinearReference<br/>(TRK001)"]
    nlr2["era:NetLinearReference<br/>(TRK002)"]
    ne1["🛤️ LinearElement NE001"]
    ne2["🛤️ LinearElement NE002"]
    ne3["🛤️ LinearElement NE003"]
    op -->|"era:netReference"| nar
    nar -->|"era:includes ①"| nlr1
    nar -->|"era:includes ②"| nlr2
    nlr1 -.->|"era:hasSequence"| ne1
    nlr1 -.->|"era:hasSequence"| ne2
    nlr2 -.->|"era:hasSequence"| ne2
    nlr2 -.->|"era:hasSequence"| ne3
```


```turtle
<_:OP001> a era:OperationalPoint ;
    era:netReference <_:NAR_OP001> .

<_:NAR_OP001> a era:NetAreaReference ;
    # ordered list, one entry per track inside the OP
    era:includes ( <_:NLR_TRK001> <_:NLR_TRK002> ) .
```

<!--
The NetAreaReference aggregates the NetLinearReference of every track in the area. Tracks within the same OP can share underlying LinearElement nodes.
-->

---
layout: two-cols
---

# 🗺️ GeoSPARQL Geometry

Geometries are placed on the element (and/or its netReference). Can be **computed** from topology + LinearElement LINESTRING, or provided directly.

```turtle
<_:SIG001>
  era:netReference [
    a era:NetPointReference ;
    era:hasTopoCoordinate [
      a era:TopologicalCoordinate ;
      era:onLinearElement <_:NE001> ;
      era:offsetFromOrigin 250.0 ] ] ;
  gsp:hasGeometry [
    a gsp:Geometry ;
    gsp:asWKT "POINT(10.752 59.914)"^^gsp:wktLiteral ] .
  #                  ^^^lon ^^^lat  ← longitude FIRST!
```

::right::
<v-click>
<div class="mt-4 text-sm">

**⚠️ #1 geometry mistake in RINF submissions:**

`POINT(`**lat lon**`)` instead of `POINT(`**lon lat**`)`

**WKT coordinate order in Europe:**

| Position | Dimension | Range |
|----------|-----------|-------|
| **1st ← FIRST** | **Longitude** | 4° – 25° E |
| 2nd | Latitude | 35° – 70° N |

**Memory aid:** In Europe, longitude is the *smaller* number. Even though it is LONG

> `POINT(`**10.75** `59.91)` ← 10.75° E, 59.91° N ✅ (Oslo)
> `POINT(`**59.91** `10.75)` ← latitude first ❌

**⚠️ Your GIS tool likely shows `(lat, lon)` — WKT is the reverse!**

</div>
</v-click>
<!--
The GeoSPARQL geometry is what goes on the map.

The coordinate order issue is one of the most frequent mistakes because:
1. Most people naturally think "latitude, longitude" (GPS, Google Maps)
2. Most GIS tools display coordinates as (lat, lon)
3. WKT standard is (lon, lat) — x-axis first, then y-axis

In Europe: if the first POINT value is > 30, it's almost certainly latitude (which belongs second). Run the SPARQL detection query from the appendix to bulk-check your dataset.

Geometry can be computed automatically from topological coordinates by interpolating along LinearElement LINESTRING geometries using Shapely or equivalent. See the era-wkt-geometry-enrichment skill for this workflow.
-->

---
layout: default
---

# 📌 Linear Referencing (Kilometric Posts)

LRS coordinates add a **kilometric position** to any topology position. They are **optional** but widely used.

```turtle
<_:netPointRef_SIG001>
    era:hasLrsCoordinate [
        a era:LinearPositioningSystemCoordinate ;
        era:kmPost <_:kmPost_LPS01_km125> ;
        era:offsetFromKilometricPost 37.5   # metres forward
    ] .

<_:kmPost_LPS01_km125> a era:KilometricPost ;
    era:hasLRS <_:lps_01> ;          # the Linear Positioning System
    era:kilometer 125.0 ;             # km value (xsd:double)
    era:kmPostName "1bis" ;         # human-readable name (optional)
    era:measuredDistance 125000.0 ;  # cumulative distance in metres (optional)
    era:netReference <_:NPR_KM125> . # own topology placement
```

<div class="grid grid-cols-2 gap-4 mt-4 text-sm">
<div class="bg-gray-800 rounded p-3">

📖 **Reading:** _"Signal SIG001 is at km 125 + 37.5 m on LPS01"_

</div>
<div class="bg-gray-800 rounded p-3">

**`KilometricPost`** is also an `era:InfrastructureElement` — it carries its own `era:netReference` (`NetPointReference`) for precise placement on the topology network.

</div>
</div>

<!--
LRS coordinates are optional but common. They provide a human-friendly reference alongside the topological coordinate.

The KilometricPost itself needs a netReference — it also lives on the topology network.
-->

---
layout: default
---

# 🏗️ Infrastructure Element Overview

All classes share the same base pattern: `era:inCountry`, `era:infrastructureManager`, `era:netReference`.

<div class="grid grid-cols-2 gap-3 mt-3 text-sm">

<div class="bg-gray-800 rounded p-3">

**📍 Point elements**

- `era:OperationalPoint` (stopping-point type), `era:Signal`, `era:Switch`,`era:LevelCrossing`, `era:KilometricPost`

**↔️ Linear elements** 

- `era:RunningTrack`, `era:Siding`, `era:PlatformEdge`, `era:Tunnel`, `era:Bridge`

**🗺️ Area elements** 

- `era:OperationalPoint`, `era:SectionOfLine`

</div>

<div>

```turtle
# Every infrastructure element follows this pattern:
<_:ELEM001> a era:InfrastructureElement ;

    # Where in the world
    era:inCountry country:DEU ;

    # Who manages it (→ era:OrganisationRole)
    era:infrastructureManager
        <era:organisations/0080_IM> ;

    # Where on the network topology
    era:netReference <_:REF_001> .
```
</div>
</div>

<!--
All these classes share the same base pattern:
- era:inCountry (required)
- era:infrastructureManager (required)
- era:netReference (required for positioning)

The functional resources distinction is crucial: ContactLineSystem, ETCS, TrainDetectionSystem do NOT have netReference — they are linked FROM tracks.

This is one of the most common modelling mistakes: trying to put netReference on a ContactLineSystem.
-->

---
layout: two-cols
---

# 📍 Operational Point Patterns

```turtle
<_:OP001> a era:OperationalPoint ;
    era:opName "Hauptbahnhof"@de ;
    rdfs:label "Hauptbahnhof"@de ;
    era:opType
      <era:concepts/op-types/10> ;   # station
    era:uopid "DEHBF" ;
    era:inCountry country:DEU ;
    era:infrastructureManager
      <era:organisations/0080_IM> ;
    era:netReference <_:NAR_OP001> .
```

**Required:** `opType`, `uopid`, `inCountry`, `infrastructureManager`, `netReference`

::right::

<div class="mt-4 text-sm">

**OP Types (selection):**

| Code | Type |
|------|------|
| 10 | Station |
| 20 | Small Station |
| 30 | Passenger Terminal |
| 70 | Passenger Stop (halt) |
| 80 | Junction |
| 90 | **Border Point** (UOPID starts `EU`) |
| 120 | Switch |
| 130 | Private Siding |

</div>

<!--
Border points are special: UOPID starts with EU, not a country code. E.g., EUBP1 not DEBP1.

The ERA organisation pattern changed significantly in v3.1. The old era:InfrastructureManager class is deprecated. The new pattern is era:Body (the organsation) + era:OrganisationRole (n-ary relationship for the IM role).

The infrastructureManager property now points to an era:OrganisationRole instance, not directly to a Body.
-->

---
layout: default
---

# ↔️ Section of Line

A `SectionOfLine` connects two `OperationalPoint` instances and acts as a **container for the tracks** between them.

```turtle
<_:SOL001> a era:SectionOfLine ;
    rdfs:label "Hauptbahnhof–Westbahnhof" ;
    era:opStart <_:OP001> ;
    era:opEnd   <_:OP002> ;
    era:solNature <era:concepts/sol-natures/10> ;   # Regular SoL
    era:nationalLine <_:lps_LineA> ;
    era:inCountry country:DEU ;
    era:infrastructureManager <_:0080_IM> ;
    era:netReference <_:netAreaRef_SOL001> .        # ← NetAreaReference
```

**Required:** `opStart`, `opEnd`, `solNature`, `inCountry`, `infrastructureManager`, `netReference`

<!--
SoL is the second top-level container after OperationalPoint.
The nationalLine property links to the Linear Positioning System — the same LPS used for kilometric posts.
-->

---
layout: default
---

# 🛤️ Track & Functional Resources

Tracks are ... (nope.. not going to tumble in that rabbit hole...). The ERA ontology distinguishes between RunningTrack (main line tracks) and Siding (auxiliary tracks):

```turtle
<_:TRK001> a era:RunningTrack ;
    era:inCountry country:DEU ;
    era:infrastructureManager <_:0080_IM> ;
    era:netReference <_:NLR_TRK001> ;

    # Functional resources linked FROM the track:
    era:contactLineSystem <_:CLS001> ;
    era:trainDetectionSystem <_:TDS001> ;
    era:etcs <_:ETCS001> ;
    era:maximumPermittedSpeed 160 .
```

<!--
Functional resources are a different category from infrastructure elements.

Infrastructure elements (OP, Track, Signal, Tunnel ...) all inherit from era:InfrastructureElement and have netReference.

Functional resources (ContactLineSystem, TrainDetectionSystem, ETCS) do NOT inherit from era:InfrastructureElement and do NOT have netReference. They are attached to the track via properties like era:contactLineSystem.

This is one of the most common modelling mistakes: people try to add netReference to a ContactLineSystem. The SHACL shapes will catch this — but it's better to understand the architecture than to rely on error messages.
-->

---
layout: default
---
# Track category

<img src="./assets/Track_categories.png" />

---
layout: two-cols-header
---

# 🚦 Signal

> ⚠️ Signs (panels) are **not** era:Signals.

::left::

```turtle
<_:SIG001> a era:Signal ;
    rdfs:label "Signal A1" ;
    era:signalType <era:concepts/signal-types/01> ;
    era:inCountry country:DEU ;
    era:infrastructureManager <_:0080_IM> ;
    era:netReference <_:NPR_SIG001> .
```

::right::

| id | type |
|----|------|
| 01 | Home Signal |
| 02 | Intermediate Signal |
| 04 | Exit Signal |
| 06 | Block Signal |


<!--
Both Signal and Switch are point elements — they use NetPointReference.
-->

---
layout: two-cols-header
---

# 🚇 Tunnel

`era:Tunnel` → `NetLinearReference`
> `lineReferenceTunnelStart/End` are not meaningful when the tunnel spans multiple tracks.


::left::

**Required properties:**

<div class="text-sm">

| Property | Note |
|---|---|
| `era:tunnelIdentification` | string ID |
| `era:lineReferenceTunnelStart` | `NetPointReference` |
| `era:lineReferenceTunnelEnd` | `NetPointReference` |
| `era:inCountry` | |
| `era:infrastructureManager` | |
| `era:netReference` | `NetLinearReference` |


</div>

::right::

```turtle
<_:TUN001> a era:Tunnel ;
    rdfs:label "Bergtunnel" ;
    era:tunnelIdentification "TUN001" ;          # REQUIRED
    era:lineReferenceTunnelStart <_:NPR_start> ; # REQUIRED
    era:lineReferenceTunnelEnd   <_:NPR_end> ;   # REQUIRED
    era:inCountry country:DEU ;
    era:infrastructureManager <_:0080_IM> ;
    era:netReference <_:NLR_TUN001> ;
    # Optional properties:
    era:lengthOfTunnel 1250.0 ;       # metres — NOT era:length!
    era:crossSectionArea 50 ;         # m²
    era:maxTunnelSpeed 120 ;          # km/h
    era:complianceInfTsi true ;
    era:dieselThermalAllowed true ;
    era:hasEmergencyPlan true ;
    era:hasEvacuationAndRescuePoints true ;
    era:hasWalkway true ;
    era:nationalRollingStockFireCategory "A" ;
    era:rollingStockFireCategory
      <era:concepts/rolling-stock-fire/10> ;
    era:tunnelDocRef <_:doc_emergency_plan> .
```


<!--
Tunnels use NetLinearReference.
Three required properties specific to Tunnel beyond the base pattern.
lineReferenceTunnelStart/End point to NetPointReference resources marking the tunnel portals.
era:length does not exist — always use era:lengthOfTunnel.
When a tunnel spans multiple parallel tracks, start/end references are not meaningful — just use the NLR.
-->

---
layout: default
---

# 🌉 Bridge

`era:Bridge` → `NetLinearReference`

> Bridge has no extra required properties beyond the two booleans and the base pattern (`inCountry`, `infrastructureManager`, `netReference`).

<div class="grid grid-cols-2 gap-4 mt-2 text-sm">
<div>

**Required properties** (beyond base):

| Property | Type | Meaning |
|---|---|---|
| `era:existBridgeWindRestriction` | `boolean` | Wind speed limits? |
| `era:existOpeningHoursLimitation` | `boolean` | Opening hours? |

</div>
<div>

```turtle
<_:BRG001> a era:Bridge ;
    rdfs:label "Rheinbrücke" ;
    era:inCountry country:DEU ;
    era:infrastructureManager <_:0080_IM> ;
    era:netReference <_:NLR_BRG001> ;
    # REQUIRED — even when false:
    era:existBridgeWindRestriction false ;
    era:existOpeningHoursLimitation false .
```

</div>
</div>

<!--
Bridge is one of the simpler elements — the main trap is missing the two boolean properties.
In RDF Open World semantics, omitting existBridgeWindRestriction does not say "no restriction" — it says "we don't know".
SHACL will flag an absent boolean as a Violation.
-->


---
layout: default
---

# ⚠️ Level Crossing

`era:LevelCrossing` → `NetPointReference`

<div class="grid grid-cols-2 gap-4 mt-4 text-sm">
<div>

Level crossings use a **point** network reference — the crossing position on the track.

**Required properties:** only the base pattern:

- `era:inCountry`
- `era:infrastructureManager`
- `era:netReference` → `NetPointReference`

No additional SHACL-required properties beyond the base for `era:LevelCrossing`.

</div>
<div>

```turtle
<_:LC001> a era:LevelCrossing ;
    rdfs:label "Bahnübergang Feldweg" ;
    era:inCountry country:DEU ;
    era:infrastructureManager <_:0080_IM> ;
    era:netReference <_:NPR_LC001> .
```

> Optional properties include road and railway identifiers, protection equipment (`era:protectionLegacySystem`), and traffic control (`era:hasBarriersOrGates`).

</div>
</div>

<!--
Level crossing is the simplest element — just the base triple pattern.
The optional properties cover things like road category, protection systems, barrier types.
-->

---
layout: default
---

# 🚉 Platform Edge

`era:PlatformEdge` → `NetLinearReference`

<div class="grid grid-cols-2 gap-4 mt-2 text-sm">
<div>

**Key property: `era:platformHeight`**

| Concept | Height |
|---|---|
| `platform-heights/30` | 550 mm |
| `platform-heights/40` | 760 mm |
| `platform-heights/140` | 920 mm |

Also: `era:platformId` — string identifier matching the OP's platform label.

</div>
<div>

```turtle
<_:PE001> a era:PlatformEdge ;
    rdfs:label "Platform 1" ;
    era:inCountry country:DEU ;
    era:infrastructureManager <_:0080_IM> ;
    era:netReference <_:NLR_PE001> ;
    era:platformId "Platform 1/2" ;
    era:platformHeight
      <era:concepts/platform-heights/30> .
      # 550 mm
```

> The `era:netReference` spans the full length of the platform edge as a `NetLinearReference`.

</div>
</div>

<!--
Platform edge uses NetLinearReference — the extent from the start to the end of the platform face.
Platform height is a SKOS concept, not a literal number.
The platformId should match the identifier used in the operational point description.
-->

---
layout: default
---

# 📌 Kilometric Post

`era:KilometricPost` → `NetPointReference`

<div class="grid grid-cols-2 gap-4 mt-4 text-sm">
<div>

Kilometer posts mark physical distance markers placed alongside the track. They carry both a **topological coordinate** (position on the topology) and a **LRS coordinate** (the kilometre value from a specific linear positioning system).

**Key properties:**

| Property | Role |
|---|---|
| `era:hasLRS` | Which LRS this post belongs to |
| `era:kilometer` | Kilometrage value (decimal) |
| `era:netReference` | Position on the topology |

</div>
<div>

```turtle
<_:KP125> a era:KilometricPost ;
    era:hasLRS <_:lps_01> ;
    era:kilometer 125.0 ;
    era:netReference <_:NPR_KP125> .

<_:NPR_KP125> a era:NetPointReference ;
    era:usesPoint <_:TP001> ;
    era:intrinsicCoordinate [
        era:coordinate 0.0
    ] .
```

> The topological position of the KP itself is described by the `NetPointReference`.

</div>
</div>

<!--
Kilometric posts are the physical manifestation of the LRS system on the ground.
They are infrastructure elements in their own right — not just annotation.
era:kilometer holds the decimal value; era:hasLRS points to the LinearPositioningSystem resource.
-->

---
layout: two-cols
---

# 🔗 Primary Location

`era:PrimaryLocation` — TAF/TAP TSI telematics link

A Primary Location (`era:PrimaryLocation`) is a subclass of `era:InfrastructureElement` and links an Operational Point to the TAF/TAP TSI location catalogue (used in freight/passenger telematics).

**Key properties:**

<div class="text-xs">

| Property | Required | Description |
|---|---|---|
| `era:primaryLocationCode` | ✅ | Pattern `[A-Z]{2}[0-9]{5}` |
| `era:primaryLocationName` | — | Human-readable name |
| `era:freightFlag` | — | Freight relevance |
| `era:containerHandlingFlag` | — | Container handling |
| `era:handoverPointFlag` | — | Network handover point |

</div>

> Likely to evolve with the TSI Telematics revision.

::right::

<div class="mt-8">

```turtle
<_:OP001> era:primaryLocation <_:PL001> .

<_:PL001> a era:PrimaryLocation ;
    era:primaryLocationCode "AT12345" ; # REQUIRED
    # Pattern: [A-Z]{2}[0-9]{5}
    era:primaryLocationName
      "Wien Westbahnhof"@en ;
    era:freightFlag true ;
    era:containerHandlingFlag false ;
    era:handoverPointFlag false ;
    era:inCountry country:AUT ;
    era:infrastructureManager <_:0081_IM> ;
    era:netReference <_:NPR_PL001> .
```

> The Primary Location is a **separate resource** linked from any era:InfrastructureElement (but mostly from era:OperationalPoint) via `era:primaryLocation`. It has its own `netReference`.

</div>

<!--
PrimaryLocation is a subclass of InfrastructureElement — it has inCountry, infrastructureManager, netReference.
It is linked FROM the OperationalPoint via era:primaryLocation.
The code pattern must match [A-Z]{2}[0-9]{5} — two uppercase letters followed by exactly 5 digits.
ERA is planning updates to this model as part of the TAF/TAP TSI revision.
-->

---
layout: default
---

# 🌐 Open World Assumption — Never Omit, Always State

**RDF / Open World thinking:**

> If the triple is absent, the answer is **"unknown"**.

```turtle
# Omitting contactLineSystem means:
# "we don't know the electrification status"

# To say "not electrified", you must DECLARE it:
_:TRK001 era:contactLineSystem [
  a era:ContactLineSystem ;
  era:contactLineSystemType era-cls:40
  # era-cls:40 = Not electrified (.../contact-line-systems/40)
] .
```

<v-click>
<div class="mt-4 p-3 bg-yellow-900 rounded text-sm">

⚠️ **This applies to ALL boolean-like properties in RINF.**  No emergency exit? State it explicitly. No gradient? State it explicitly.
Absence only means the data provider hasn't stated it yet.

</div>
</v-click>

<!--
This is arguably the most important conceptual slide of the day for people coming from XML backgrounds.

Practical consequences:
- Non-electrified tracks MUST have a ContactLineSystem with type /40
- Tracks with no gradient restrictions should have maximumGradient = 0, not omit the property
- Tunnels with no special emergency plan still need a document reference if the SHACL shape requires it

The SHACL shapes catch SOME of these (minCount constraints), but not all. The Open World assumption is a mindset change, not just a validation rule.
-->

---
layout: default
---

# ⏰ Temporal Validity Pattern

**Every infrastructure element needs `era:validity`**

<div class="grid grid-cols-2 gap-4">
<div>

```turtle
_:TRK001 a era:RunningTrack ;
    era:validity _:TRK001_validity .

_:TRK001_validity a time:Interval ;
    time:hasBeginning _:TRK001_begin .

_:TRK001_begin a time:Instant ;
    time:inXSDDate "2025-01-01"^^xsd:date .
```

</div>
<div>

**❌ Common mistakes:**

```turtle
# WRONG: era:validFrom does not exist!
_:TRK001 era:validFrom "2025-01-01" .

# WRONG: disjoint classes violation!
_:TRK001 a era:RunningTrack, era:TemporalFeature .

# WRONG: missing the Interval resource
_:TRK001 era:validity "2025-01-01"^^xsd:date .
```

</div>
</div>

<v-click>
<div class="p-3 bg-yellow-900 rounded text-sm mt-2">

⚠️ `era:Feature` and `era:TemporalFeature` are declared `owl:disjointWith`.  
Never type a track/OP as both. The validity is always on a **separate** `time:Interval` resource.

</div>
</v-click>

<!--
The temporal model is one of the trickier parts. ERA's model follows OWL-Time.

The chain is: Feature → era:validity → time:Interval → time:hasBeginning → time:Instant → time:inXSDDate.

Common mistakes:
1. Using era:validFrom — this property doesn't exist in the ERA ontology
2. Typing the element itself as era:TemporalFeature — causes OWL disjointness violation
3. Putting a date literal directly on era:validity — must be an Interval resource

Best practice: use a SPARQL UPDATE post-processing step to add validity to all elements that don't have one yet.
-->

---
layout: default
---

# � Train Detection System (TDS)

`era:TrainDetectionSystem` — linked FROM track via `era:trainDetectionSystem`

<div class="grid grid-cols-2 gap-4 mt-2 text-sm">
<div>

**Required:** `era:trainDetectionSystemType` (maxCount=1)

| Concept | Meaning |
|---|---|
| `train-detection/10` | Track circuit |
| `train-detection/20` | Axle counter |
| `train-detection/30` | Loop |

**Axle-counter-only properties:**
- `era:tdsMaximumMagneticField` → `era:MaximumMagneticField`  
  (directional X/Y/Z in dB µA/m)
- `era:maximumInterferenceCurrent` (A/m)

</div>
<div>

```turtle
<_:TDS001> a era:TrainDetectionSystem ;
    era:trainDetectionSystemType
      <era:concepts/train-detection/20> ;  # REQUIRED
    era:inCountry country:DEU ;
    era:infrastructureManager <_:0080_IM> ;
    era:trainDetectionSystemSpecificCheck
      <era:concepts/train-detection-specific-checks/10> ;
    era:frequencyBandsForDetection
      <era:concepts/FrequencyBandsForDetection/20> ;
    era:maximumInterferenceCurrent 4.0 ;
    era:tdsMaximumMagneticField [
        a era:MaximumMagneticField ;
        era:maximumMagneticFieldDirectionX 110 ;
        era:maximumMagneticFieldDirectionY 110 ;
        era:maximumMagneticFieldDirectionZ 110
    ] .

# Linked FROM the track:
<_:TRK001> era:trainDetectionSystem <_:TDS001> .
```

> Functional resource — **no** `era:netReference`.

</div>
</div>

<!--
TDS is a functional resource — no netReference, no geometry of its own.
Linked from the RunningTrack via era:trainDetectionSystem.
The maximumMagneticField sub-resource is only required for axle counter type (/20).
-->

---
layout: two-cols-header
---

# ⚡ Contact Line System (CLS)

::left::

**Required:** `era:contactLineSystemType` (maxCount=1)

<div class="text-xs">

| Concept | Meaning |
|---|---|
| `contact-line-systems/10` | Overhead contact line |
| `contact-line-systems/40` | **Not electrified** |


**Key rules:**
- Non-electrified tracks **must** still have a CLS with type `/40`
- OCL-only properties (`maxCurrentStandstillPantograph`, `maximumContactWireHeight`, `minimumContactWireHeight`) produce SHACL Warning if absent on OCL, Violation if present on non-OCL
- If track spans multiple CLS: **split the track** ? or aggregate using most restrictive values ?

</div>
::right::

<div class="mt-8">

```turtle
<_:CLS001> a era:ContactLineSystem ;
    era:contactLineSystemType
      <era:concepts/contact-line-systems/10> ; # REQUIRED
      # /10 = OCL, /40 = Not electrified
    era:inCountry country:DEU ;
    era:infrastructureManager <_:0080_IM> ;
    era:energySupplySystem
      <era:concepts/energy-supply-systems/AC10> ;
    era:maxTrainCurrent 300 ;
    # OCL-only properties:
    era:maxCurrentStandstillPantograph 200 ;
    era:maximumContactWireHeight 6.2 ;
    era:minimumContactWireHeight 5.0 .

# Linked FROM the track:
<_:TRK001> era:contactLineSystem <_:CLS001> ;
    # Track-level OCL properties:
    era:tsiPantographHead
      <era:concepts/compliant-pantograph-heads/10> ;
    era:trackRaisedPantographsDistanceAndSpeed
      <_:raisedPantoSpec> .
```

</div>

<!--
CLS is the most complex functional resource.
Non-electrified is a common trap — you must STILL declare a CLS with type /40.
OCL-only properties cause SHACL violations if present on type /40.
Track-level pantograph properties are on the RunningTrack, not the CLS itself.
Aggregation rule: if a track crosses from one electrification zone to another, either split at the boundary or aggregate conservatively.
-->

---
layout: two-cols-header
---

# 📡 ETCS

`era:ETCS` — linked FROM track via `era:etcs`

**Required:** `era:etcsLevelType` (maxCount=1) — _not_ the deprecated `era:etcsLevel`!

::left::

<div class="text-xs">

| Concept | Level |
|---|---|
| `etcs-levels/10` | Level 1 |
| `etcs-levels/20` | Level 2 |
| `etcs-levels/30` | Level 3 |
| `etcs-levels/99` | STM / national |

**SHACL Warning if absent:**
- `era:etcsBaseline`
- `era:etcsMVersion`
- `era:etcsTransmitsTrackConditions`

**Level-1 only:** `era:etcsInfill`

</div>

::right::

<div class="mt-8">

```turtle
<_:ETCS001> a era:ETCS ;
    era:etcsLevelType
      <era:concepts/etcs-levels/20> ;  # REQUIRED — NOT era:etcsLevel!
    era:inCountry country:DEU ;
    era:infrastructureManager <_:0080_IM> ;
    era:etcsBaseline
      <era:concepts/etcs-baselines/30> ;
    era:etcsMVersion
      <era:concepts/etcs-m-versions/ETCSMVersions/33> ;
    era:etcsTransmitsTrackConditions true ;
    era:etcsSystemCompatibility
      <era:concepts/etcs-system-compatibilities/10> ;
    # Level 1 only:
    era:etcsInfill
      <era:concepts/etcs-infills/10> .

# Linked FROM the track:
<_:TRK001> era:etcs <_:ETCS001> .
```

</div>

<!--
Common mistake: using era:etcsLevel (old property) instead of era:etcsLevelType.
Baseline and M_VERSION are not hard required but SHACL will warn.
etcsInfill only makes sense for Level 1 — applying it to Level 2/3 will cause a SHACL issue.
-->

---
layout: default
---

# 📏 Lineside Distance Indication (LDI)

`era:LinesideDistanceIndication` — linked FROM track via `era:linesideDistanceIndication`

> Currently only 1 `era:LinesideDistanceIndication` per Track is supported. But this is under discussion


<div class="grid grid-cols-2 gap-4 mt-2 text-sm">
<div>

**Required properties:**

| Property | Notes |
|---|---|
| `era:linesideDistanceIndicationAppearance` | REQUIRED, **repeatable** |
| `era:linesideDistanceIndicationFrequency` | metres between posts, REQUIRED |

**Optional:**

- `era:linesideDistanceIndicationPositioning` — approximate distance between markers

</div>
<div>

```turtle
<_:LDI001> a era:LinesideDistanceIndication ;
    era:linesideDistanceIndicationAppearance
      <era:concepts/lineside-distance-indication-appearance/10> ;
    # REQUIRED — repeatable if multiple types
    era:linesideDistanceIndicationAppearance
      <era:concepts/lineside-distance-indication-appearance/20> ;
    era:linesideDistanceIndicationFrequency 1000 ;
    # metres between posts — REQUIRED
    era:linesideDistanceIndicationPositioning
      <era:concepts/lineside-distance-indication-positioning/10> .
    # optional

# Linked FROM the track:
<_:TRK001> era:linesideDistanceIndication <_:LDI001> .
```

</div>
</div>

<!--
LDI is the least commonly known functional resource.

Frequency is the spacing in metres between individual distance markers.
-->

---
layout: default
---

# � Border Points

`era:OperationalPoint` with `era:opType` = `op-types/90`

<div class="grid grid-cols-2 gap-4 mt-2 text-sm">
<div>

**Special rules for border points:**

1. **UOPID prefix** starts with `EU` — not a country code  
   (e.g. `EUBP1`, not `DEBP1`)

2. Must have an associated `era:ReferenceBorderPoint` resource with a matching `era:borderPointId`

3. Geometry is **inherited** from the parent OperationalPoint via post-processing

> The list of official border points is published by ERA as a CSV on the [RINF website](https://www.era.europa.eu/domains/registers/rinf_en).

</div>
<div>

```turtle
<_:BP001> a era:OperationalPoint ;
    era:opType
      <era:concepts/op-types/90> ;
    era:uopid "EUBP1" ;
    # "EU" prefix — NOT a country code!
    era:inCountry country:DEU ;
    era:infrastructureManager <_:0080_IM> ;
    era:netReference <_:NPR_BP001> ;
    era:referenceBorderPoint <_:RBP001> .

<_:RBP001> a era:ReferenceBorderPoint ;
    era:borderPointId "EUBP1" .
```

> The `borderPointId` must match the `uopid` of the OperationalPoint.

</div>
</div>

<!--
Border points are a special subtype of OperationalPoint.
The EU prefix on the UOPID signals that the point is administered at EU level, not nationally.
The ReferenceBorderPoint is a separate resource — don't omit it.
The CSV on the ERA RINF website is the authoritative list of current border points.
-->

---
layout: default
---

# 📄 Documents

Linking documents to infrastructure elements (`era:Document`)

<div class="grid grid-cols-2 gap-4 mt-2 text-sm">
<div>

**Workflow:**

1. Upload file in Dataset Manager → _Reference Documents Management_
2. Query the Reference Documents API → get an `id` — a 40-char hex string
3. Construct the URI: `http://data.europa.eu/949/documents/{id}`
4. Use that URI in your Turtle:

**Language requirement:**

Documents must be provided in 2 official EU languages.  
**Recommended:** 2 `era:Document` with each 1 `era:documentUrl` values (one per language file) and a `dcterms:language` property.

</div>
<div>

```turtle
# The Document resource:
<era:documents/a22e9fbd9a969ca6e2cbb4b7093d3b4583c57344>
    a era:Document ;
    foaf:name "emergency_plan.pdf"^^xsd:string ;
    era:documentUrl
      "https://ld4rail.../documents/a22e.../download"
      ^^xsd:anyURI ;
    dcterms:language "en".

<era:documents/b344e533ecbb4322367dde627093d3b4583c57344>
    a era:Document ;
    foaf:name "emergency_plan.pdf"^^xsd:string ;
    era:documentUrl
      "https://ld4rail.../documents/b33f.../download"
      ^^xsd:anyURI ;
    dcterms:language "fr".

# Link from infrastructure element:
<_:TUN001>
    era:document
      <era:documents/a22e9fbd9a969...>, <era:documents/b344e533ecbb43...>  .
```

</div>
</div>

<!--
Documents are referenced from elements like Tunnels (emergency plan), SectionsOfLine (local rules), SwitchesAndCrossings (safety docs).
The 40-char hex id is assigned by the system at upload time — you cannot choose it.
Multiple infrastructure managers have had difficulties with this workflow — it's worth flagging to ERA early.
Provide docs in 2 EU languages; the English + national language combination is the most common approach.
-->

---
layout: default
---

# 🔗 `era:hasPart` & `era:isPartOf`

Prefer to **inferred** containment instead of stating manually

<div class="grid grid-cols-2 gap-4 mt-2 text-sm">
<div>

**What these properties express:**

- `era:OperationalPoint era:hasPart era:Track`  
- `era:SectionOfLine era:hasPart era:Track`  
- `era:Track era:isPartOf era:OperationalPoint`

These **don't need to be set in your Turtle source** — they can be derived from topology overlap using SPARQL UPDATE post-processing.


</div>
<div>

```sparql
# Conceptual post-processing — do NOT write manually:
# (handled by era-topology-relations skill)

CONSTRUCT {
    ?op era:hasPart ?track .
    ?track era:isPartOf ?op .
}
WHERE {
    # track's NLR window overlaps with
    # OP's NLR window on the same LinearElement
    ...
}
```

</div>

</div>

<div class="text-sm">

**Inference patterns:**
1. **Point-in-extent**: a point element (e.g. `KilometricPost`) is within a linear element if its topological offset lies within the linear element's effective window on a shared `LinearElement`
2. **Extent-overlap**: a linear element (e.g. `Track`) is part of an aggregate (e.g. `OperationalPoint`) if their effective windows on a shared `LinearElement` intersect

</div>

<!--
This is one of the most commonly misunderstood aspects.
Providers often try to explicitly state era:hasPart from OP to Track based on their knowledge of the physical layout.
This works in simple cases but breaks when topology is updated — the manual assertions become stale.
The topology-based inference ensures containment is always consistent with the actual network geometry.
-->

---
layout: default
---

# 🔌 `era:connectedTo` — Internal Track Connections

RINF parameter **1.2.4.1 Internal connection**

<div class="grid grid-cols-2 gap-4 mt-2 text-sm">
<div>

**Ontology definition:**

```turtle
era:connectedTo
    a owl:ObjectProperty,
      owl:SymmetricProperty,
      owl:IrreflexiveProperty ;
    rdfs:domain era:Track ;
    rdfs:range  era:Track .
```

Connects two `era:Track` instances (superclass of `RunningTrack` and `Siding`).  
Because it is **symmetric**, `A era:connectedTo B` implies `B era:connectedTo A`.  
Because it is **irreflexive**, a track cannot be connected to itself.

</div>
<div>

<img src="./assets/connected-to.svg" class="max-h-52 w-full object-contain mb-2" />

```turtle
_trackLine1 era:connectedTo _trackA .
_trackLine1 era:connectedTo _trackB .
_trackLine1 era:connectedTo _trackC .

_trackA era:connectedTo _trackLine2 .
_trackB era:connectedTo _trackLine2 .
```

> `_trackA`, `_trackB`, `_trackC` are **not** connected to each other.  
> The unnamed connection between switch 1 and switch 3 is invisible unless explicitly modelled as a `era:Track`.

</div>
</div>

<!--
era:connectedTo answers the question: "which tracks are reachable from this track without reversing direction?"

The limitation is real: if a train arrives on national line 1 in the opposite direction, it can only reach trackC, not trackA — but the property cannot express that asymmetry.

Best practice: infer connectedTo from topology (NetRelation boundaries) rather than stating it manually.
-->

---
layout: section
---

# 🗂️ Dataset Example

### Hands-on exploration

<div class="absolute bottom-6 left-0 right-0 text-center text-xs text-gray-400">
  ① Welcome · ② Ecosystem · ③ Portal · ④ Ontology · <span class="font-semibold text-white">⑤ Dataset</span> · ⑥ Pipeline · ⑦ SHACL · ⑧ Access · ⑨ Q&A
</div>

<!--
Short hands-on section: explore the example railML-derived dataset.
-->

---
layout: default
---

# 🧪 Hands-on: Explore the Example Dataset

<div class="text-lg mt-4">

1. 📂 Open the [railML example dataset](https://github.com/Matdata-eu/raillML-to-ERA) in your editor
2. 🔍 Find an `era:OperationalPoint` — what required properties does it have?
3. 🛤️ Find its tracks — what functional resources are linked?
4. 🗺️ Trace the `era:netReference` chain to the `LinearElement`
5. ✅ Check for `era:validity` — is the temporal pattern correct?

</div>

<div class="mt-6 p-3 bg-gray-800 rounded text-sm">

**💡 Tools:**
- Your code editor (VS Code) for syntax highlighting
- [YasGUI](https://yasgui.matdata.eu/) https://yasgui.matdata.eu/ pointed at a local Fuseki instance
- Repository: https://github.com/Matdata-eu/raillML-to-ERA
- SPARQL endpoint: https://jena.matdata.eu/rinf

</div>


<!--
Give 15 minutes for this exercise. Walk around and help people.

The goal is just to get comfortable navigating real RDF data. Not to complete a full review.

Common findings during this exercise:
- "I can't find a CLS on this not-electrified track" → teachable moment about Open World
- "The netReference chain is confusing" → draw it on the whiteboard
-->

---
layout: center
class: text-center
---

# 🍽️ Lunch Break

### 12:30 – 13:30

<div class="text-6xl mt-4">🍽️</div>

_Back at 13:30 for Data Provisioning Workflow_

---
layout: section
---

# ⚙️ Data Provisioning Workflow

### 13:30 – 14:45

<div class="absolute bottom-6 left-0 right-0 text-center text-xs text-gray-400">
  ① Welcome · ② Ecosystem · ③ Portal · ④ Ontology · ⑤ Dataset · <span class="font-semibold text-white">⑥ Pipeline</span> · ⑦ SHACL · ⑧ Access · ⑨ Q&A
</div>

<!--
75 minutes.
Split: 10 min Norway case study, 35 min pipeline walkthrough, 15 min reference docs, 15 min hands-on.
-->

---
layout: two-cols
---

# 🇳🇴 Case Study: Norway's First Upload

**What we learned from Bane NOR's data provisioning journey:**

<v-clicks>

- 📦 **Source**: internal GIS + asset management systems
- 🔧 **Tool**: SPARQL-Anything + CONSTRUCT queries
- 📐 **Topology**: generated from GIS LineString geometries
- 📍 **Positioning**: topological coordinates interpolated from geometry
- ✅ **Validation**: ~2000 SHACL violations on first run → 12 after fixes

</v-clicks>

::right::

<div class="mt-8 text-sm">
<v-click>

**Key lessons:**

| Challenge | Solution |
|-----------|----------|
| GIS has no ERA topology | Generate from geometry intersection algorithm |
| IM code format changed | Use era:Body + OrganisationRole |
| Missing SKOS inScheme | Add country inScheme triples in post-proc |
| Coordinate order wrong | Validate POINT(lon lat) not (lat lon) |
| Validity missing | SPARQL UPDATE adds it to all elements |

</v-click>
</div>

<!--
The Norway case study is a great example because:
1. They started from scratch — no existing ERA-formatted data
2. They had good GIS data but needed to convert to ERA topology
3. The SHACL validation feedback loop was essential

The key message: it took multiple iterations. The first SHACL run produced 2000 violations. That's normal. The validation feedback loop is the mechanism for improvement.

After addressing the systematic issues (coordinate order, SKOS inScheme, validity pattern), the violations dropped dramatically.
-->

---
layout: default
---

# 🔄 The Provisioning Pipeline

```mermaid
flowchart LR
    A["📤 Upload<br/>.ttl or .nt file"] --> B["🔄 Transform<br/>Format normalisation"]
    B --> C["✅ SHACL<br/>Validation"]
    C --> D["🧠 KG<br/>Generation"]
    D --> E["🌐 Publication<br/>Public endpoint"]

    C -->|"❌ Violations"| F["📋 Validation<br/>Report"]
    F -->|"Fix & re-upload"| A

    style A fill:#2d3748,color:#e2e8f0
    style C fill:#276749,color:#e2e8f0
    style E fill:#1a365d,color:#e2e8f0
    style F fill:#742a2a,color:#e2e8f0
```

<div class="grid grid-cols-3 gap-3 mt-4 text-sm">
<div class="bg-gray-800 rounded p-2">

**Upload**
- Turtle (`.ttl`) or N-Triples (`.nt`)
- Full or partial
- ZIP supported for large files

</div>
<div class="bg-gray-800 rounded p-2">

**Validation**
- ERA RINF SHACL shapes
- Severity: Violation / Warning
- Report downloadable

</div>
<div class="bg-gray-800 rounded p-2">

**Publication**
- SPARQL endpoint updated
- Public visibility
- Dataset versioned

</div>
</div>

<!--
The pipeline is the core workflow. Each stage has a status you can monitor in the Dataset Manager UI.

Important: server-side SHACL validation is slower than local validation. A large dataset can take minutes. This is why local pre-validation is strongly recommended.

The validation report shows each violation with: the resource URI, the property, the constraint that was violated, and the actual/expected values. This is enough information to fix the issue.
-->

---
layout: two-cols
---

# 📤 Full vs Partial Upload

### Full Upload 🔄

Replaces your entire dataset.

**When to use:**
- First submission
- Major restructuring
- Version upgrade (v3.0 → v3.1)

**Steps:**
1. Generate full RDF graph
2. Validate locally with SHACL
3. Upload file → pipeline runs
4. Review validation report

::right::

### Partial Upload ➕

Merged into existing dataset.

**When to use:**
- Regular updates
- New tracks or OPs added
- Property corrections

**Steps:**
1. Generate changed elements only
2. Validate locally
3. Upload delta file
4. Monitor pipeline

<v-click>
<div class="bg-yellow-900 rounded p-2 mt-4 text-sm col-span-2">

⚠️ **Referential integrity**: a partial upload referencing an `era:OperationalPoint`  
must either include that OP or have it already in the published dataset.

</div>
</v-click>

<!--
The partial upload is powerful but requires care around referential integrity.

Example: if you add a new Track that is era:isPartOf an existing OperationalPoint, the OP must already be in the knowledge graph. If you're uploading it for the first time, include the OP in the same upload.

Practical tip: for regular incremental updates, maintain a version control system (Git) for your RDF files. Tag releases against ontology versions.
-->

---
layout: two-cols
---

# 📄 Reference Documents

ERA properties can reference `era:Document` instances:

<v-clicks>

- 🚇 Emergency plans (Tunnels)
- ⚡ Regenerative braking conditions
- ⚠️ Local rules and restrictions
- 📐 Schematic overviews (OPs)

</v-clicks>

<v-click>

```turtle
<_:TUN001> a era:Tunnel ;
    era:document <era:documents/a22e9fb...> .

<era:documents/a22e9fb...> a era:Document ;
    foaf:name "emergency-plan.pdf"^^xsd:string ;
    era:documentUrl
      "https://ld4rail.../documents/a22e9fb.../download"
      ^^xsd:anyURI .
```

</v-click>

::right::

<div class="mt-4 text-sm">
<v-click>

**Workflow to link a document:**

1. Go to *Reference Documents Management* in Dataset Manager
2. Upload your file
3. Note the 40-character hex ID returned
4. Construct the URI: `http://data.europa.eu/949/documents/{id}`
5. Use it in your RDF

</v-click>

<v-click>
<div class="p-2 bg-blue-900 rounded mt-2 text-xs">

💡 **2 languages required!**  
Recommended: 1 `era:Document` with 2 `era:documentUrl` values (one per language)

</div>
</v-click>

</div>

<!--
Documents are a common pain point. Multiple IMs have reported issues with the workflow.

If you have trouble: contact servicedesk@era.europa.eu with the specific error message.

The 40-character hex ID is assigned by the system when you upload. You need to capture it from the API response or query the documents API afterwards.

Language requirement: at least 2 EU official languages. This usually means English + your national language. Provide them as two documentUrl values on the same Document resource.
-->

---
layout: default
---

# 🧪 Hands-on: Upload to UAT

<div class="text-lg mt-4">

1. 🌐 Open: **https://uat.ld4rail.fpfis.tech.ec.europa.eu/**
2. 🔐 Log in with your credentials
3. 📂 Navigate to your country's dataset
4. 📤 Upload the railML example dataset (`.ttl` or `.nt`)
5. ⏳ Monitor pipeline execution — watch each stage
6. 📋 Review the validation report
7. 🔧 Identify any violations and discuss

</div>

<div class="mt-4 p-3 bg-gray-800 rounded text-sm">

**💡 Help:**  
Credentials not working? 👉 Contact servicedesk@era.europa.eu  
Pipeline stuck? Check status, wait 2 min, then refresh.

</div>

<!--
This is the central hands-on exercise of the afternoon section.

Walk around and help people with login issues. These are common — UAT credentials sometimes expire.

The example dataset is specifically designed to include some common patterns (and optionally some deliberate errors to fix).

Encourage people to use their own small real data samples if they have them prepared.
-->

---
layout: center
class: text-center
---

# ☕ Coffee Break

### 14:45 – 15:00

<div class="text-6xl mt-4">☕</div>

_Back in 15 minutes for SHACL Validation_

---
layout: section
---

# ✅ Understanding & Performing SHACL Validation

### 15:00 – 16:00

<div class="absolute bottom-6 left-0 right-0 text-center text-xs text-gray-400">
  ① Welcome · ② Ecosystem · ③ Portal · ④ Ontology · ⑤ Dataset · ⑥ Pipeline · <span class="font-semibold text-white">⑦ SHACL</span> · ⑧ Access · ⑨ Q&A
</div>

<!--
60 minutes.
Split: 25 min SHACL theory + error types, 35 min tools and hands-on.
-->

---
layout: two-cols
---

# 🔍 What is SHACL?

**Shapes Constraint Language** — W3C standard for RDF validation

SHACL shapes define what your data **must** look like:

```turtle
# A SHACL shape for OperationalPoint
era:OperationalPointShape
    a sh:NodeShape ;
    sh:targetClass era:OperationalPoint ;

    # uopid is REQUIRED
    sh:property [
        sh:path era:uopid ;
        sh:minCount 1 ;
        sh:maxCount 1 ;
        sh:datatype xsd:string
    ] ;

    # opType must be a SKOS concept
    sh:property [
        sh:path era:opType ;
        sh:minCount 1 ;
        sh:nodeKind sh:IRI
    ] .
```

::right::

<div class="mt-4 text-sm">

**Constraint types in ERA SHACL:**

| Constraint | Meaning |
|---|---|
| `sh:minCount 1` | **REQUIRED** — must have ≥1 value |
| `sh:maxCount 1` | At most one value |
| `sh:datatype xsd:string` | Specific literal type |
| `sh:nodeKind sh:IRI` | Must be a URI (not a literal) |
| `sh:class era:X` | Referenced resource must be typed |
| `sh:pattern "^[A-Z]{2}"` | Regex pattern on value |

**Severity levels:**
- 🔴 `sh:Violation` — must fix before acceptance
- 🟡 `sh:Warning` — should fix, non-blocking

</div>

<!--
SHACL is the mechanism that turns the ontology into machine-verifiable compliance.

Key insight: the ERA SHACL shapes ARE the authoritative specification of what's required. When in doubt about whether something is required, look at the SHACL shapes.

The shapes file is at: era-shacl/ERA-RINF-shapes.ttl in the ERA GitLab repo.

Severity: Violations block acceptance in some contexts but the current ERA Dataset Manager accepts data with Warnings (yellow) but may reject on Violations (red). Check current behaviour with ERA.
-->

---
layout: default
---

# 📋 Reading a SHACL Validation Report

```turtle
# A typical SHACL validation report
[] a sh:ValidationReport ;
    sh:conforms false ;
    sh:result [
        a sh:ValidationResult ;
        sh:focusNode <https://data.example.eu/_tracks_TRK001> ;
        sh:resultPath era:netReference ;
        sh:resultSeverity sh:Violation ;
        sh:resultMessage "Less than 1 values on era:netReference" ;
        sh:sourceConstraintComponent sh:MinCountConstraintComponent ;
        sh:sourceShape era:RunningTrackShape
    ] .
```

**How to interpret:**

| Field | Meaning |
|---|---|
| `sh:focusNode` | **Which resource** has the problem |
| `sh:resultPath` | **Which property** is affected |
| `sh:resultMessage` | **What's wrong** |
| `sh:sourceShape` | Which SHACL shape triggered it |

<!--
The validation report is your debugging tool. Always start with:
1. How many violations? (vs warnings, which are lower priority)
2. What's the most common pattern? Often one systematic error causes hundreds of violations.
3. Fix the systematic issues first, then tackle individual cases.

Common pattern: thousands of violations all pointing to the same missing triple type → one SPARQL UPDATE to add them all at once.
-->

---
layout: default
---

# 🚨 Most Common Validation Errors

<div class="grid grid-cols-5 gap-4 text-sm mt-2">
<div class="col-span-2">

| # | Error | Fix strategy |
|---|-------|-------------|
| 1 | Missing `era:validity` | SPARQL UPDATE |
| 2 | Coord order swapped | Fix in generation |
| 3 | Missing `skos:inScheme` | Post-proc UPDATE |
| 4 | `netReference` on CLS | Remove, link from track |
| 5 | `xsd:double` vs `xsd:integer` | Datatype UPDATE |
| 6 | Deprecated `era:InfraManager` | v3.1 migration |
| 7 | No CLS for non-electrified | Add type `/40` |

<div class="mt-3 text-xs text-gray-400">

💡 Errors #1 #3 #5 → next slide: one SPARQL UPDATE fixes all

</div>
</div>
<div class="col-span-3 text-xs">

**Error #1 — missing `era:validity` (every element!):**

```turtle
# ❌ Wrong — no validity at all
_:TRK001 a era:RunningTrack .
# ✅ Correct
_:TRK001 era:validity [
  a time:Interval ;
  time:hasBeginning [
    a time:Instant ;
    time:inXSDDate "2025-01-01"^^xsd:date ] ] .
```

**Error #7 — Open World: absent ≠ not electrified:**

```turtle
# ❌ Wrong — omitting CLS means UNKNOWN, not "not electrified"
# ✅ Correct — explicitly declare the type:
_:TRK001 era:contactLineSystem [
  a era:ContactLineSystem ;
  era:contactLineSystemType era-cls:40 ] .
# era-cls:40 = Not electrified (.../contact-line-systems/40)
```

</div>
</div>

<!--
These are the 7 most common issues in practice, roughly in order of frequency.

Key insight: errors #1, #3, and #5 are systematic — they affect nearly every element in a new submission. Fix them all at once with SPARQL UPDATE (next slide).

Errors #2, #4, #6, #7 require modelling changes in the generation pipeline itself.

The Open World assumption (#7) catches people from XML/XML Schema backgrounds where "element absent" = "not applicable". In RDF, absence only means "we don't know". You must make statements explicitly.
-->

---
layout: default
---

# 🔧 Systematic SPARQL UPDATE Fixes

Most errors repeat across thousands of elements — fix them all at once in post-processing:

<div class="grid grid-cols-2 gap-4 text-xs mt-2">
<div>

**Fix #1 — add `era:validity` to all elements missing it:**

```sparql
PREFIX era:  <http://data.europa.eu/949/>
PREFIX time: <http://www.w3.org/2006/time#>
PREFIX xsd:  <http://www.w3.org/2001/XMLSchema#>

INSERT {
  ?e era:validity [
    a time:Interval ;
    time:hasBeginning [
      a time:Instant ;
      time:inXSDDate "2024-01-01"^^xsd:date ] ] }
WHERE {
  VALUES ?t { era:OperationalPoint era:RunningTrack
              era:SectionOfLine era:Signal }
  ?e a ?t .
  FILTER NOT EXISTS { ?e era:validity [] }
}
```

</div>
<div>

**Fix #3 — add `skos:inScheme` to country references:**

```sparql
PREFIX skos: <http://www.w3.org/2004/02/skos/core#>
PREFIX era:  <http://data.europa.eu/949/>

INSERT {
  ?country skos:inScheme
    <http://publications.europa.eu/resource/authority/country>
}
WHERE {
  ?element era:inCountry ?country .
  FILTER NOT EXISTS { ?country skos:inScheme [] }
}
```

**Fix #5 — correct `xsd:double` → `xsd:integer` for speeds:**

```sparql
DELETE { ?e era:maximumPermittedSpeed ?old }
INSERT { ?e era:maximumPermittedSpeed ?corrected }
WHERE {
  ?e era:maximumPermittedSpeed ?old .
  FILTER(datatype(?old) = xsd:double)
  BIND(xsd:integer(str(?old)) AS ?corrected)
}
```

</div>
</div>

<!--
These SPARQL UPDATE patterns are powerful. They turn thousands of violations into zero with a single query.

Run these in post-processing AFTER your initial SPARQL CONSTRUCT generation but BEFORE uploading. Build them into your pipeline permanently so every future run benefits automatically.

The country inScheme fix (#3): ERA's SHACL shapes check that country URIs have a skos:inScheme triple. That triple lives in ERA's own triplestore, not your upload. So your standalone validation will complain until you add it locally.

Fix #5: Check SHACL shapes for other properties that also require xsd:integer — the same pattern applies to gauge, platform height, etc.
-->

---
layout: two-cols
---

# 🛠️ SHACL Validation Tools

### Local: PySHACL

```python
from pyshacl import validate
from rdflib import Graph

data = Graph().parse("my-data.ttl")
shapes = Graph().parse("ERA-RINF-shapes.ttl")

# Apply shape fixes first!
# (exclude-ontology-uris-from-type-check.sparql)

conforms, report, text = validate(
    data,
    shacl_graph=shapes,
    inference="none"
)

if not conforms:
    print(text)
```

**Free and open source. Suitable for automation.**  
⚠️ Slower than MapLib (~250s for large graphs)

::right::

<div class="mt-4 text-sm">

### Local: MapLib

```python
import maplib

m = maplib.Mapping()
m.read_triples("my-data.ttl")
m.read_shacl("ERA-RINF-shapes.ttl",
             named_graph="urn:shapes")

report = m.validate()
```

**Very fast (~1.5s vs 250s for same data)**  
⚠️ Requires paid licence for SHACL validation

<hr class="my-3" />

### Remote: EU Interoperability Test Bed

🌐 [interoperable-europe.ec.europa.eu](https://interoperable-europe.ec.europa.eu/collection/interoperability-test-bed-repository/solution/interoperability-test-bed)

- No local setup required
- Upload dataset + shapes
- Retrieve full validation report
- Good reference implementation

</div>

<!--
For most IMs, PySHACL is the recommended starting point: free, well-documented, and integrates into Python pipelines.

The EU Interoperability Test Bed is excellent for a second opinion — different SHACL engine means different potential edge cases.

IMPORTANT: Apply the shape fixes before running validation. Without them, you will get thousands of spurious warnings about OWL/RDF/SKOS vocabulary URIs that are perfectly valid. These obscure the real issues.

Shape fixes are in the 04-validate/shape-fixes/ directory of the example repository.
-->

---
layout: default
---

# ⚠️ Shape Fixes — Why You Need Them

**Running SHACL without fixes → thousands of spurious warnings:**

<v-clicks>

1. **`InstancesMustHaveTypeShape` fires on vocabulary URIs**  
   `<era:concepts/contact-line-systems/10>` has no `rdf:type` in your data (it's defined in ERA's triplestore)  
   → Fix: `exclude-ontology-uris-from-type-check.sparql`

2. **Deprecated-property checks fire on external vocabulary**  
   GeoSPARQL, OWL-Time properties trip ERA's deprecated-property SHACL shapes  
   → Fix: `exclude-ontology-uris-from-deprecated-check.sparql`

3. **GeoSPARQL `sh:sparql` constraints throw errors**  
   `geof:distance`, `geof:within` — most validators don't implement these  
   → Fix: filter out SPARQLConstraints referencing `geof:` functions

</v-clicks>

<v-click>
<div class="p-3 bg-yellow-900 rounded mt-4 text-sm">

📁 Shape fixes are in `04-validate/shape-fixes/` in the example repository.  
Apply as SPARQL UPDATE against the shapes graph **before** running validation.

</div>
</v-click>

<!--
This is a practical issue that can waste hours if you don't know about it.

The ERA SHACL shapes have some known quirks:
1. They check that every IRI has an rdf:type — but SKOS concepts from ERA's vocabulary are only typed in ERA's own triplestore, not in your upload. So they appear "untyped" to a standalone validator.
2. Deprecated-property shapes sometimes fire incorrectly on external ontology properties.
3. GeoSPARQL extension functions (geof:distance etc.) are not standard SPARQL and most SHACL validators can't evaluate them.

The shape fixes are SPARQL UPDATE queries that modify the shapes graph to exclude these false positives.
-->

---
layout: default
---

# 🧪 Hands-on: Validate & Fix

<div class="grid grid-cols-2 gap-4 mt-4">
<div>

### Exercise 1: Local Validation

1. 📥 Download latest `ERA-RINF-shapes.ttl` from ERA GitLab
2. 🐍 Install pySHACL: `pip install pyshacl`
3. ▶️ Run validation on the example dataset
4. 📋 Count violations vs warnings
5. 🔧 Apply shape fixes and re-run — how many spurrious warnings disappear?

</div>
<div>

### Exercise 2: Introduce & Fix Errors

1. ✏️ Make these deliberate mistakes in the dataset:
   - Remove `era:validity` from one track
   - Swap lat/lon in a geometry
   - Remove `era:netReference` from an OP
2. ▶️ Re-validate
3. 🔍 Find the violations in the report
4. 🛠️ Fix them and validate again

</div>
</div>

<div class="mt-4 p-3 bg-gray-800 rounded text-sm">

💡 **Bonus:** Compare local validation results with the EU Interoperability Test Bed.  
Are there differences? Discuss why.

</div>

<!--
This hands-on is very effective at building intuition for the validation loop.

The deliberate error exercise is particularly valuable: people need to experience the feedback loop firsthand — introduce error, see report, fix, re-validate.

Common observation: different SHACL validators can produce slightly different results. This is normal — some implement more features (especially sh:sparql constraints). The EU Test Bed is a useful reference.
-->

---
layout: section
---

# 🔑 Getting Access, Help & Reporting Issues

### 16:00 – 16:30

<div class="absolute bottom-6 left-0 right-0 text-center text-xs text-gray-400">
  ① Welcome · ② Ecosystem · ③ Portal · ④ Ontology · ⑤ Dataset · ⑥ Pipeline · ⑦ SHACL · <span class="font-semibold text-white">⑧ Access</span> · ⑨ Q&A
</div>

<!--
30 minutes.
Split: 10 min access setup, 20 min GitLab + support channels.
-->

---
layout: two-cols
---

# 🔐 Getting Access

**Data Provisioning Environment:**

- **Production**: https://ld4rail.fpfis.tech.ec.europa.eu/
- **UAT/Test**: https://uat.ld4rail.fpfis.tech.ec.europa.eu/

<v-clicks>

**Steps to get access:**
1. ✉️ Contact **servicedesk@era.europa.eu**
2. Specify: organisation, role, environment needed
3. Single Sign-On (EU Login) credentials assigned
4. Verify login on UAT first

**User roles:**
- **Viewer**: read-only access
- **Data Provider**: can upload datasets
- **Admin**: full dataset management

</v-clicks>

::right::

<div class="mt-6">
<v-click>

**⚠️ Common access issues:**

| Issue | Solution |
|---|---|
| Login loop | Clear cookies, try private browser |
| Credentials expired | Contact Service Desk |
| Wrong environment | Check URL — UAT vs Production |
| No organisation visible | Wait 24h after access granted |
| Dataset Manager not showing | Correct role not assigned |

</v-click>

<v-click>
<div class="mt-4 p-2 bg-green-900 rounded text-sm">

🎯 **Right now**: verify your login to UAT  
https://uat.ld4rail.fpfis.tech.ec.europa.eu/

</div>
</v-click>
</div>

<!--
Take a few minutes now to verify that everyone can log in to the UAT environment.

If someone can't log in, note their details and contact the Service Desk on their behalf. Don't let this block them from participating in the exercises — they can pair with a colleague.

The UAT environment is specifically for testing and training. It's safe to upload test data and try things out here.
-->

---
layout: two-cols
---

# 🐛 Reporting Issues — GitLab

**Issue tracker:**  
https://gitlab.com/era-europe-eu/.../era-ontology/-/issues

**When to create an issue:**

<v-clicks>

- 🐞 Bug in Dataset Manager / pipeline
- 🤔 Question about ontology design
- 💡 Improvement suggestion
- ❌ SHACL validation error that seems wrong
- 📐 Missing concept in a SKOS scheme

</v-clicks>

::right::

<div class="mt-4 text-sm">
<v-click>

**Effective issue report template:**

```
## Problem
What I expected vs what happened.

## Steps to Reproduce
1. Load data: [attach .ttl snippet]
2. Run validation
3. See error: [paste exact error message]

## Context
- ERA Ontology version: v3.1
- Validator: pySHACL 0.26.0
- Data graph size: ~7000 triples

## Labels
bug, shacl, dataset-manager
```

</v-click>
</div>

<!--
GitLab is the primary channel for technical issues. ERA monitors it actively.

A good issue report speeds up resolution dramatically. The key elements:
- What you expected
- What actually happened
- A minimal reproducible example (small .ttl snippet showing the issue)
- Exact version numbers

Labels help ERA triage:
- bug: something is broken
- question: you need clarification
- dataset-manager: pipeline or UI issue
- shacl: validation constraint issue
- KG generation: knowledge graph generation step issue
-->

---
layout: default
---

# 📞 Support Channels

<div class="grid grid-cols-3 gap-4 mt-4">
<div class="bg-gray-800 rounded p-4">

### 🎫 Service Desk

**servicedesk@era.europa.eu**

Use for:
- Account/access issues
- Urgent pipeline problems
- General RINF questions

🕐 Business hours

</div>
<div class="bg-gray-800 rounded p-4">

### 🦊 ERA GitLab

**gitlab.com/era-europa-eu/...**

Use for:
- Ontology bugs
- SHACL shape issues
- Improvement proposals
- Public discussion

🌐 Public, async

</div>
<div class="bg-gray-800 rounded p-4">

### 📧 RINF Team

**RinfProjectTeam@era.europa.eu**

Use for:
- General RINF questions
- No follow-up action needed
- Process/policy questions

✉️ Async

</div>
<div class="bg-gray-800 rounded p-4">

### 🏢 RINF Network

**SharePoint (RINFNet)**

Use for:
- Working group collaboration
- Shared templates & examples
- Meeting minutes & recordings
- Peer discussion between IMs

🔒 EU Login required

</div>
</div>

<div class="mt-4 p-3 bg-blue-900 rounded text-sm">

📖 **User Manual**: https://data-interop.era.europa.eu/RINF-User%20Manual%20v2.0.pdf  
🔗 **Application Guide**: https://data-interop.era.europa.eu/era-vocabulary/rinf-appGuide/  
🏢 **RINF SharePoint**: https://eraeuropaeu.sharepoint.com/sites/RINFNet

</div>

<!--
Summary of all support channels.

Service Desk = human support. Use for anything that requires ERA action (access, urgent issues).
GitLab = technical issue tracker. Use for bugs and improvements. Public means other IMs can see the issues and learn from them too.
RINF Team = project/policy questions.

The User Manual covers a lot of ground and is worth reading before the first submission.
-->

---
layout: default
---

# 🧪 Hands-on: GitLab Issue Tracker

<div class="mt-4">

1. 🌐 Open: https://gitlab.com/era-europa-eu/public/interoperable-data-programme/era-ontology/era-ontology/-/issues

2. 🔍 Browse the open issues — find one related to:
   - Dataset Manager
   - SHACL validation
   - A specific ERA class you work with

3. 📋 Read a recent issue: does it have enough information? What's missing?

4. ✏️ **Draft a sample issue** based on something you encountered today  
   (or a fictional scenario)  
   — Fill in all sections of the template — but **don't submit** unless you have a real issue!

</div>

<!--
This exercise builds the habit of using the issue tracker productively.

Reading existing issues is surprisingly educational: you can see what problems other IMs have encountered, and often find answers to your own questions.

The "draft but don't submit" instruction is important — we don't want to flood the tracker with test issues.
-->

---
layout: section
---

# 💬 Q&A & Open Discussion

### 16:30 – 16:50

<div class="absolute bottom-6 left-0 right-0 text-center text-xs text-gray-400">
  ① Welcome · ② Ecosystem · ③ Portal · ④ Ontology · ⑤ Dataset · ⑥ Pipeline · ⑦ SHACL · ⑧ Access · <span class="font-semibold text-white">⑨ Q&A</span>
</div>

<!--
20 minutes for open questions and discussion.
-->

---
layout: default
---

# 💬 Open Questions & Discussion

**Topics to explore together:**

<v-clicks>

- 🔮 How will ontology upgrades work in the future?  
  _Who migrates existing submitted data when ERA changes the ontology?_

- 🤝 Community of Practice  
  _How can IMs share tools, pipelines, and best practices?_

- ⚡ Functional resources as InfrastructureElements  
  _Should ContactLineSystem, ETCS, TrainDetectionSystem carry their own netReference?_

- 🔄 LDES vs batch uploads  
  _What would event-driven incremental data provisioning look like for your organisation?_

- 🧩 CommonCharacteristicsSubset  
  _Is it helping or causing more problems than it solves?_

</v-clicks>

<!--
These are discussion topics derived from real open questions in the ERA community.

The ontology upgrade question is particularly practical: if ERA publishes v3.2, does all previously submitted data become invalid? How does ERA communicate the migration path?

Encourage IMs to share their own challenges and questions here.
-->

---
layout: section
---

# 🎯 Wrap-up & Next Steps

### 16:50 – 17:00

<div class="absolute bottom-6 left-0 right-0 text-center text-xs text-gray-400">
  ① Welcome · ② Ecosystem · ③ Portal · ④ Ontology · ⑤ Dataset · ⑥ Pipeline · ⑦ SHACL · ⑧ Access · ⑨ Q&A · <span class="font-semibold text-white">🎯 Wrap-up</span>
</div>

---
layout: default
---

# 🎯 Key Takeaways

<v-clicks>

1. 📜 **Legal mandate** — RINF RDF v3.1 submission required by 31 March 2026

2. 🔗 **RDF is the right choice** — graph model fits railway networks naturally; IRIs enable federated data

3. 🏗️ **Architecture first** — topology (LinearElements, NetRelations) is the backbone; everything else positions on it

4. 🔄 **Validate early, validate often** — run SHACL locally before uploading; apply shape fixes first

5. 🌐 **Open World** — never assume absence means false; explicitly state "not electrified", "no restrictions", etc.

6. ⚡ **Functional resources** — ContactLineSystem, ETCS, TrainDetectionSystem have no `netReference` — linked FROM tracks

7. 🆘 **Help is available** — GitLab for technical issues, Service Desk for access, RINF team for questions

</v-clicks>

<!--
Quick mental recap of the most important things from today.

If participants only remember 3 things:
1. The deadline is real — March 31
2. Validate with SHACL before uploading
3. Open World assumption: absence ≠ false
-->

---
layout: two-cols
---

# 🚀 Next Steps

**For Participants:**

<v-clicks>

- ✅ Verify UAT credentials work
- 📖 Re-read today's reference materials
- 📥 Download latest SHACL shapes from ERA GitLab  
  `era-shacl/ERA-RINF-shapes.ttl`
- 🛠️ Set up local validation pipeline (pySHACL)
- 📂 Prepare a small sample of your actual data  
  and run it through the pipeline
- 🎫 Contact Service Desk for production access  
  when ready

</v-clicks>

::right::

<div class="mt-6">
<v-click>

**Useful Resources:**

| Resource | Link |
|---|---|
| 📖 Application Guide | [rinf-appGuide](https://data-interop.era.europa.eu/era-vocabulary/rinf-appGuide/) |
| 🦊 ERA GitLab | [era-ontology](https://gitlab.com/era-europa-eu/public/interoperable-data-programme/era-ontology/era-ontology) |
| 📋 SHACL Shapes | [ERA-RINF-shapes.ttl](https://gitlab.com/era-europa-eu/public/interoperable-data-programme/era-ontology/era-ontology/-/raw/main/era-shacl/ERA-RINF-shapes.ttl) |
| 📝 User Manual | [RINF User Manual](https://data-interop.era.europa.eu/RINF-User%20Manual%20v2.0.pdf) |
| 🔍 SPARQL (custom) | [yasgui.matdata.eu](https://yasgui.matdata.eu/) |
| 🐍 Example repo | [raillML-to-ERA](https://github.com/Matdata-eu/raillML-to-ERA) |

</v-click>
</div>

<!--
The most important next step after today: take a SMALL piece of your real data and run it through the pipeline.

Don't try to convert everything at once. Start with one operational point and its tracks, validate, iterate.

The example repository on GitHub (raillML-to-ERA) is a real end-to-end pipeline that you can learn from and adapt.
-->

---
layout: center
class: text-center
---

<div class="flex justify-center mb-6">
  <img src="/assets/European_Union_Agency_for_Railways_logo.svg" class="h-16" />
</div>

# Thank You! 🙏

### ERA RINF Data Provisioning Workshop

<div class="grid grid-cols-3 gap-4 mt-8 text-sm">
<div class="bg-gray-800 rounded p-3">

**📧 Service Desk**  
servicedesk@era.europa.eu

</div>
<div class="bg-gray-800 rounded p-3">

**🦊 GitLab Issues**  
era-ontology issues tracker

</div>
<div class="bg-gray-800 rounded p-3">

**📧 RINF Team**  
RinfProjectTeam@era.europa.eu

</div>
</div>

<div class="mt-8 text-gray-400 text-sm">

🗓️ Deadline: **31 March 2026** · 🚂 Good luck with your data provisioning!

</div>

<!--
Thank everyone for their participation and engagement.

Remind them that this slide deck is available as reference material.

Encourage them to connect with each other — the community of IMs sharing experiences and tools is valuable.

If there's a follow-up session or community of practice, mention it here.
-->

---
layout: default
---

# 📎 Appendix: KG Generation Tools

<div class="grid grid-cols-2 gap-4 text-sm">
<div>

### ✅ Recommended: SPARQL-Anything

```sparql
PREFIX fx: <http://sparql.xyz/facade-x/ns/>
PREFIX xyz: <http://sparql.xyz/facade-x/data/>

CONSTRUCT {
  ?op a era:OperationalPoint ;
      era:opName ?name ;
      era:uopid ?id .
}
WHERE {
  SERVICE <x-sparql-anything:my-data.xml> {
    # Query your XML as if it were RDF
    ?root xyz:stations/xyz:station ?s .
    ?s xyz:name ?name ;
       xyz:id ?id .
    BIND(IRI(CONCAT("...", ?id)) AS ?op)
  }
}
```

💡 **Tip**: Use the one-eyed-graph approach — convert source data to a plain RDF representation first, then query with clean SPARQL CONSTRUCT.

</div>
<div>

### Other Options

**R2RML / YARRRML**
- W3C standard for relational → RDF
- YAML syntax (YARRRML) is human-friendly
- Good tool support: RMLMapper, Morph-KGC
- ⚠️ Complex for nested data

**OTTR Templates**
- Parameterised templates per ERA class
- Good for large-scale consistent mappings
- Smaller community than R2RML

**DIY Python/Java**
```python
from rdflib import Graph, Namespace
ERA = Namespace("http://data.europa.eu/949/")
g = Graph()
g.add((op_uri, RDF.type, ERA.OperationalPoint))
g.serialize("output.ttl")
```
💡 Avoid this if possible — prefer declarative tools

</div>
</div>

<!--
This appendix slide provides a reference for tool selection.

SPARQL-Anything is the recommended approach for most cases because:
1. SPARQL is a skill you need anyway (for querying and debugging)
2. It handles virtually any source format
3. The one-eyed-graph pattern gives clean SPARQL without SPARQL-Anything specifics

The GitHub repository (raillML-to-ERA) provides a complete working example of the SPARQL-Anything pipeline.

DIY Python: only use this as a last resort. It's hard to maintain and easy to get wrong.
-->

---
layout: default
---

# 📎 Appendix: URI Minting Patterns

<div class="grid grid-cols-2 gap-4 text-sm">
<div>

### ERA Namespace

```
http://data.europa.eu/949/{module}/{class}/{id}
```

**Modules:** `topology`, `trackside`, `onboard`, `body`

```
# Examples:
http://data.europa.eu/949/topology/linearElement/NE-001-SVN
http://data.europa.eu/949/functionalInfrastructure/operationalPoints/ATAhH1K
http://data.europa.eu/949/functionalInfrastructure/signals/SIG-4201
```

**ID character restrictions:**  
✅ `A-Z`, `a-z`, `0-9`, `-`, `_`  
❌ No spaces, `/`, `.`, `(`, `)`, `#`

</div>
<div>

### Own Namespace

```
https://data.yourorg.eu/_className_localId
```

```
# Examples:
https://data.bane-nor.no/_operationalPoints_OP001
https://data.sncf.fr/_tracks_TRK-4201
```

**Requirements:**
- URIs must be **dereferenceable**
- HTTP GET on URI must return a response
- Support content negotiation:
  - `Accept: text/html` → HTML page
  - `Accept: text/turtle` → RDF description

💡 Flat structure easier to manage than nested paths

</div>
</div>

<!--
URI design is a one-time decision that's hard to change later. Both options are valid.

ERA namespace: easy to get started, no infrastructure needed, but you're minting URIs in ERA's namespace — they need to follow ERA's conventions.

Own namespace: requires you to set up a dereferenceable endpoint. An open source tool (URI-Dereferencer on GitHub) makes this easier.

Recommendation: if your organisation plans to publish broader Linked Data, invest in your own namespace with dereferencing. If you just need to submit RINF data, ERA namespace is fine.
-->

---
layout: default
---

# 📎 Appendix: SPARQL Cheat Sheet

<div class="grid grid-cols-2 gap-4 text-sm">
<div>

### Find all OPs in a country

```sparql
PREFIX era: <http://data.europa.eu/949/>
PREFIX country: <http://publications.europa.eu/resource/authority/country/>

SELECT ?op ?name WHERE {
  ?op a era:OperationalPoint ;
      era:opName ?name ;
      era:inCountry country:DEU .
}
LIMIT 10
```

### Check required properties

```sparql
PREFIX sh: <http://www.w3.org/ns/shacl#>
PREFIX era: <http://data.europa.eu/949/>

SELECT ?property WHERE {
  ?shape sh:targetClass era:OperationalPoint ;
         sh:property ?ps .
  ?ps sh:path ?property ;
      sh:minCount 1 .
}
```

</div>
<div>

### Find missing validity

```sparql
PREFIX era: <http://data.europa.eu/949/>

SELECT ?element ?type WHERE {
  VALUES ?type {
    era:OperationalPoint
    era:RunningTrack
    era:SectionOfLine
  }
  ?element a ?type .
  FILTER NOT EXISTS {
    ?element era:validity ?v .
  }
}
```

### Verify SKOS concept

```sparql
PREFIX skos: <http://www.w3.org/2004/02/skos/core#>

ASK {
  <http://data.europa.eu/949/concepts/op-types/10>
    skos:inScheme
    <http://data.europa.eu/949/concepts/op-types/OpTypes>
}
```

</div>
</div>

<!--
These are the most useful SPARQL queries for data provisioning work.

The "Find missing validity" query is particularly useful as a pre-upload check — run it against your graph before validation.

The "Verify SKOS concept" ASK query is useful when you're unsure if a concept URI is valid.

Point people to the ERA SPARQL endpoint and Yasgui for trying these queries interactively.
-->

---
layout: default
---

# 📎 Appendix: Common Turtle Patterns

```turtle
@prefix era:    <http://data.europa.eu/949/> .
@prefix gsp:    <http://www.opengis.net/ont/geosparql#> .
@prefix time:   <http://www.w3.org/2006/time#> .
@prefix xsd:    <http://www.w3.org/2001/XMLSchema#> .
@prefix rdfs:   <http://www.w3.org/2000/01/rdf-schema#> .
@prefix country: <http://publications.europa.eu/resource/authority/country/> .

# ═══ Organisation (v3.1 pattern) ════════════════════════════════════
<era:organisations/0076> a era:Body ;
    era:organisationCode "0076" ;
    rdfs:label "Bane NOR"@no .

<era:organisations/0076_IM> a era:OrganisationRole ;
    era:hasOrganisationRole <era:concepts/organisation-roles/IM> ;
    era:roleOf <era:organisations/0076> .

# ═══ Temporal Validity ═══════════════════════════════════════════════
<_:TRK001_validity> a time:Interval ;
    time:hasBeginning <_:TRK001_begin> .
<_:TRK001_begin> a time:Instant ;
    time:inXSDDate "2025-01-01"^^xsd:date .

# ═══ Country with inScheme ═══════════════════════════════════════════
country:NOR skos:inScheme
    <http://publications.europa.eu/resource/authority/country> .

# ═══ Geometry (POINT — longitude FIRST!) ════════════════════════════
<_:geom_SIG001> a gsp:Geometry ;
    gsp:asWKT "POINT(10.7522 59.9139)"^^gsp:wktLiteral .
```

<!--
A quick reference card of the patterns that trip people up most:
1. Organisation: use era:Body + era:OrganisationRole (not era:InfrastructureManager)
2. Validity: the full chain — Interval → Instant → date
3. Country: must include skos:inScheme
4. Geometry: POINT(lon lat) — longitude FIRST

Print this as a handout for participants.
-->
