# Geography --- Source Mapping & Onboarding Contract

**Status:** v0.1 template / execution artifact

## 1. Purpose

This file is the operational bridge between the HLD and real
integrations.

Do not invent source names in the architecture. Each real source must be
added here when its owner, contract and capabilities are known.

## 2. Source Mapping Matrix

  --------------------------------------------------------------------------------------------------------------------------------------------------------------------------
  Source          Business     Entity/Layer     Source of    Access / Query CRS       Temporal     Freshness   Auth /           Required or         Failure      Phase
                  Owner        Types            Truth        Mechanism                Capability   Metadata    Classification   Optional            Behavior     
  --------------- ------------ ---------------- ------------ -------------- --------- ------------ ----------- ---------------- ------------------- ------------ -----------
  **TBD --- First TBD          TBD              Source       TBD            TBD       current /    TBD         TBD              Required for first  explicit     Phase 1
  authoritative                                                                       history?                                  slice               fail if      
  geo source**                                                                                                                                      required     

  **TBD ---       TBD          TBD              Source       TBD            TBD       TBD          TBD         TBD              Optional/Required   partial or   Phase 2
  Second geo                                                                                                                    TBD                 fail by      candidate
  source**                                                                                                                                          semantics    

  **Operations    Operations   area_ref /       Operations   API/contract   n/a/ref   according to yes where   domain auth      contextual input    unresolved   Phase 1
  references**                 geo_entity_ref   owns                                  referenced   resolved                                         ref =        
                                                reference                             source                                                        explicit     
                                                context;                                                                                            error        
                                                Geography                                                                                                        
                                                resolves                                                                                                         
                                                spatial                                                                                                          
                                                entity                                                                                                           
  --------------------------------------------------------------------------------------------------------------------------------------------------------------------------

## 3. Required Adapter Facts

Before implementation, every source must define:

``` yaml
source_name:
business_owner:
technical_owner:
supported_entity_types: []
access_method:
source_crs:
geometry_types: []
supports_bbox_query:
supports_attribute_filter:
supports_time_query:
history_capability:
source_updated_at_available:
expected_freshness:
auth_model:
classification:
rate_limits:
availability_slo:
```

## 4. Adapter Responsibilities

Each adapter owns:

-   source authentication / authorization propagation;
-   source-specific query translation;
-   pagination/rate-limit handling;
-   geometry parsing;
-   CRS normalization;
-   temporal field mapping;
-   provenance extraction;
-   source error translation;
-   freshness extraction;
-   source-specific retry behavior.

It does **not** redefine source business truth.

## 5. Must-Connect Gate

A source is Phase 1 Must-Connect only if:

1.  the Golden E2E cannot be proven without it;
2.  a real consumer needs it;
3.  owner is identified;
4.  access is available;
5.  test data exists;
6.  geometry/CRS are understood;
7.  authorization is approved;
8.  failure semantics are defined.

Existing in the organization is not sufficient justification.

## 6. Source Capability Matrix

For each onboarded source, mark support:

  Capability                  Yes/No   Notes
  --------------------------- -------- -------
  Entity lookup by ID                  
  Bounding-box query                   
  Polygon/area query                   
  Attribute filtering                  
  Current geometry                     
  Historical geometry                  
  `source_updated_at`                  
  Stable source entity ID              
  Pagination                           
  Bulk query                           
  Event/change notification            
  Classification metadata              

## 7. Freshness

Geography does not create arbitrary confidence scores.

Freshness should derive from:

``` text
source_updated_at
+ source-specific expected freshness/SLA
+ query calculated_at
```

A stale result is explicitly marked; it is not silently discarded or
represented as current.

## 8. CRS / Geometry Checklist

Before source onboarding:

-   identify source CRS;
-   choose canonical computation CRS strategy;
-   validate conversion;
-   define supported geometry types;
-   define invalid geometry behavior;
-   define large geometry limits;
-   create known spatial fixtures for testing.

**Never guess coordinates or CRS.**

## 9. Temporal Checklist

For each source:

-   current only or historical?
-   valid-time fields available?
-   event-time vs update-time?
-   retention period?
-   can state be queried at arbitrary T?
-   if not, what response should Geography return?

Lack of history does not trigger automatic persistence.

## 10. Security Checklist

-   consumer identity propagation;
-   source authorization;
-   classification;
-   cross-source aggregation sensitivity;
-   result filtering;
-   sensitive query audit;
-   cache restrictions for classified data.

## 11. Onboarding Definition of Done

A source is onboarded when:

-   adapter contract is documented;
-   real query works;
-   provenance/time metadata are returned;
-   CRS conversion is tested;
-   failure behavior is tested;
-   auth/classification is approved;
-   observability exists;
-   at least one consumer uses it through Geography rather than direct
    integration.
