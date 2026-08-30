# Geography --- Product Requirements Document

**Status:** v0.2 --- Company Brain / Handoff\
**Domain question:** **מה קורה במרחב?**\
**Architecture:** Federated Spatial Intelligence Layer\
**Default:** Federate + Compute; persist only by explicit decision.

## 1. Executive Summary

Geography מספק לארגון שפה אחידה ויכולות חישוב מרחביות מעל מקורות
גיאוגרפיים authoritative קיימים.

ברירת המחדל אינה בניית מאגר GIS נוסף. מערכות המקור נשארות Source of
Truth; Geography מספק Source Adapters, Canonical Spatial Contract,
federation, spatial reasoning ותוצאות עם provenance, זמן ו-completeness.

עקרון הליבה:

> **Sources own the data. Geography owns the spatial language and
> spatial computation contract.**

תוצאות חישוב הן Query Results כברירת מחדל. Cache מותר לצרכים טכניים בלבד
והוא rebuildable, disposable ו-non-authoritative.

## 2. Problem

מידע מרחבי מפוזר בין מערכות, שכבות ומודלים שונים. ללא Geography משותף כל
consumer נדרש להתחבר למקורות, להבין פורמטים/CRS/זמן, לממש spatial logic
ולבצע synthesis בעצמו. הדבר יוצר כפילות, coupling וחוסר עקביות.

## 3. Product Ownership

Geography הוא בעל הבית על:

-   Canonical Spatial Contract.
-   Source adapters למקורות מרחביים.
-   Federated spatial query.
-   intersects / contains / within / distance / nearest / overlap.
-   aggregation by area / density.
-   layer synthesis.
-   heatmaps.
-   temporal-spatial query כאשר המקורות תומכים.
-   Spatial Intent contract ל-Text → Map.
-   Structured spatial facts ל-Map → Text.
-   provenance, source time, completeness ו-warnings.
-   technical caches.

Geography **אינו** בעל הבית על:

-   Operation lifecycle / plan.
-   זמינות כוח עסקית.
-   operational meaning חוצה דומיינים.
-   Commander attention/recommendations.
-   conversational orchestration.
-   readiness.
-   source-owned GIS entities.
-   historical archive אוטומטי.
-   permanent derived spatial products כברירת מחדל.

## 4. Domain Boundaries

  -----------------------------------------------------------------------
  Domain                  השאלה                   Ownership
  ----------------------- ----------------------- -----------------------
  Operations              מה מתוכנן ומתבצע?       Operation, plan,
                                                  activities,
                                                  dependencies, factual
                                                  operational state

  Geography               מה קורה במרחב?          spatial facts,
                                                  relationships,
                                                  calculations, synthesis

  Context & Meaning       מה המשמעות של הדברים    decomposition,
                          ביחד?                   cross-domain
                                                  correlation, impact and
                                                  meaning

  Commander Experience    מה המפקד צריך להבין     presentation,
                          ולעשות?                 attention,
                                                  investigation,
                                                  decision/action
  -----------------------------------------------------------------------

**Example:** Geography: `Route A intersects Area B for 2.4 km at T`.
Context & Meaning: `השינוי באזור עשוי להשפיע על נתיב המבצע`. Commander
Experience מחליט כיצד להציג זאת.

## 5. Persistence Policy

  Information                                         Default
  --------------------------------------------------- ---------------------------
  Source geometry / attributes                        Federate
  Normalized representation                           Compute
  Spatial relationship                                Compute
  Intersection / proximity result                     Compute
  Layer synthesis                                     Compute
  Heatmap                                             Compute
  Query result                                        Return; do not persist
  Expensive repeated result / tiles                   Cache if justified
  Historical state                                    Query source if supported
  SyntheticLayer / SpatialInsight persistent entity   Requires ADR

> **Compute first. Persist only when a business lifecycle requires it.**

## 6. Canonical Spatial Contract

### GeoEntity

``` yaml
entity_ref: string
entity_type: string
geometry: geometry
source: string
source_entity_id: string
source_updated_at: datetime
valid_from: datetime?
valid_to: datetime?
attributes: object
```

### SpatialQuery

``` yaml
operation: intersects | contains | within | distance | nearest | overlap | aggregate_by_area | density
subjects: [ref/query]
reference_geometry: geometry/ref?
parameters: object
time_context: datetime/range?
filters: object?
```

### SpatialResult

``` yaml
query_id: string
result_type: string
entity_refs: [string]
geometry: geometry?
metrics: object?
calculated_at: datetime
source_refs: [string]
source_versions: [string]?
time_context: object?
completeness:
  status: complete | partial
  unavailable_sources: []
warnings: []
```

`GeoEntity` הוא representation בזמן query/compute ואינו מעיד על
persistence.

## 7. Core Capabilities

### Federated Query

גישה למספר מקורות authoritative דרך חוזה אחיד.

### Spatial Reasoning

חישובים דטרמיניסטיים של יחסים מרחביים.

### Layer Synthesis

שילוב שכבות לצורך query/view ללא יצירת שכבה קבועה כברירת מחדל.

### Heatmaps

density/aggregation לפי מקורות ופרמטרים מוגדרים; Query Product כברירת
מחדל.

### Temporal Geography

החוזה תומך `valid_at`, `valid_from`, `valid_to` וחלונות זמן. Geography
אינו מבטיח היסטוריה שמקור המידע אינו שומר. צורך קריטי ב-materialization
היסטורי דורש ADR.

### Text → Map

Context & Meaning מפרק שאלה עסקית. Geography מקבל spatial intent מוגדר,
מאמת אותו ומריץ חישוב דטרמיניסטי. LLM יכול לפרש intent; הוא אינו מייצר
spatial fact.

### Map → Text

Geography מחזיר facts מובנים על בחירת מפה: entities, distances,
intersections, density, spatial change, source/time. Context & Meaning
אחראי לפרשנות המבצעית.

## 8. Conversational Orchestration

``` text
Commander
   ↓
Commander Experience
   ↓
Context & Meaning
   ↓ intent/decomposition
   ├── Operations / other domain facts
   └── Geography → SpatialResult
   ↓
Context & Meaning → combined operational meaning
   ↓
Commander Experience
```

**Guardrail:** Geography אינו general-purpose chatbot ואינו קורא עצמאית
דומיינים אחרים כדי להשלים משמעות עסקית.

## 9. Reference Scenarios

### RS-01 --- Spatial Proximity

**Question:** אילו ישויות מסוג X נמצאות עד 5 ק"מ ממרחב/Operation Y בזמן
T?\
**Flow:** resolve reference geometry → query source entities → normalize
→ distance/within → return refs, distance, source/time/completeness.\
**Not Geography:** האם הישות "זמינה" או מה משמעות הקרבה למבצע.

### RS-02 --- Layer Synthesis

**Question:** הצג יחד שכבות כוחות, מגבלות ותשתיות באזור X.\
Geography federates selected sources and returns a composed view/query
result while preserving provenance and freshness per source. אין
`SyntheticLayer` persistent כברירת מחדל.

### RS-03 --- Temporal Change

**Question:** מה השתנה במרחב X בין T1 ל-T2?\
Geography מבצע זאת רק מול מקורות שמספקים historical state. מקור ללא
היסטוריה מסומן unavailable/partial; Geography אינו ממציא snapshot.

### RS-04 --- Heatmap

**Question:** הצג צפיפות של entity type X באזור Y בחלון זמן.\
Geography filters → aggregates/density → returns HeatmapResult +
algorithm parameters + sources. ניתן cache; לא authoritative entity.

### RS-05 --- Text → Map

**Question:** "תראה לי את כל X בטווח 3 ק"מ מ-Y."\
Context & Meaning resolves business context and sends constrained
spatial intent. Geography validates → builds SpatialQuery →
deterministic engine → SpatialResult/map.

### RS-06 --- Map → Text

המשתמש מסמן polygon. Geography מחזיר אילו entities נמצאים/חופפים,
מרחקים, density ו-source/time. אם נדרשת משמעות מבצעית, התוצאה עוברת
ל-Context & Meaning.

### RS-07 --- Multi-domain Question

**Question:** "אילו כוחות זמינים הלילה נמצאים עד 5 ק"מ ממבצע X?"\
Operations/Force domain עונה על availability; Geography עונה על
proximity; Context & Meaning עושה intersection עסקי ומנסח משמעות.

## 10. Evidence & Trust

כל SpatialResult צריך לאפשר להבין:

-   sources/source entities;
-   source update time;
-   requested time context;
-   calculation time;
-   algorithm/operation where relevant;
-   completeness;
-   unavailable/stale sources;
-   warnings.

Partial truth must be explicit.

## 11. Functional Requirements

  ID          Requirement
  ----------- ---------------------------------------------------------
  GEO-FR-01   Canonical spatial contract independent of source format
  GEO-FR-02   Source adapters
  GEO-FR-03   Deterministic spatial operations
  GEO-FR-04   Provenance + temporal metadata
  GEO-FR-05   Ephemeral layer synthesis
  GEO-FR-06   Heatmap/density
  GEO-FR-07   Temporal query parameters
  GEO-FR-08   Explicit history-unavailable behavior
  GEO-FR-09   Spatial intent → validated query
  GEO-FR-10   Structured facts for downstream consumers
  GEO-FR-11   Rebuildable cache
  GEO-FR-12   Explicit degraded/partial semantics

## 12. NFRs

-   Versioned APIs/contracts.
-   SLO by operation class.
-   Observability per source and compute stage.
-   Source authorization/classification preserved.
-   No silent semantic degradation.
-   Invalid geometry/CRS/time errors are explicit.
-   Cache cannot become source truth.

## 13. Success Metrics

-   \% spatial consumers using Geography contract vs direct source
    integration.
-   reuse of operations across initiatives.
-   reduction in duplicate spatial logic.
-   query success / partial-result rate.
-   provenance coverage.
-   P50/P95 latency by operation.
-   source onboarding lead time.
-   consumer onboarding lead time.

## 14. Non-Goals

Not a replacement for every GIS; not a Data Lake; not a Digital Twin;
not a general LLM agent; not the operational meaning layer; not
Commander recommendation engine; not automatic historical archive; not
permanent store for every derived result.

## 15. Guardrails

1.  Federate first.
2.  Compute first; persist only with lifecycle.
3.  Sources own data; Geography owns spatial semantics.
4.  Spatial facts come from deterministic execution.
5.  LLM may parse intent, not invent facts.
6.  Temporal contract ≠ historical storage.
7.  Cache ≠ persistence.
8.  Geography facts ≠ operational meaning.
9.  No duplicate geo logic in consumers.
10. New capabilities require a real vertical-slice consumer.

## 16. Open Decisions

-   Must-Connect sources.
-   geometry serialization and CRS strategy.
-   first operation vocabulary.
-   source freshness expectations.
-   query SLOs.
-   authorization/classification.
-   cache technology.
-   partial-result policy.
-   first Text → Map intents.
-   any future persistent derived products.
