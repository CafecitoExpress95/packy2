# Graph Report - ./src  (2026-04-27)

## Corpus Check
- Corpus is ~8,904 words - fits in a single context window. You may not need a graph.

## Summary
- 170 nodes · 242 edges · 8 communities detected
- Extraction: 85% EXTRACTED · 14% INFERRED · 0% AMBIGUOUS · INFERRED: 35 edges (avg confidence: 0.78)
- Token cost: 721 input · 930 output

## Community Hubs (Navigation)
- [[_COMMUNITY_Route Mutations|Route Mutations]]
- [[_COMMUNITY_Component Workflows|Component Workflows]]
- [[_COMMUNITY_Import And Store|Import And Store]]
- [[_COMMUNITY_Migration And Shell|Migration And Shell]]
- [[_COMMUNITY_IndexedDB Storage|IndexedDB Storage]]
- [[_COMMUNITY_Export Formatting|Export Formatting]]
- [[_COMMUNITY_Trip Header|Trip Header]]
- [[_COMMUNITY_Favicon Asset|Favicon Asset]]

## God Nodes (most connected - your core abstractions)
1. `updateAndSave()` - 25 edges
2. `Normalized Trip Data Model` - 10 edges
3. `getDB()` - 9 edges
4. `Trip Manager Page` - 9 edges
5. `generateFilename()` - 7 edges
6. `Update Item Fields` - 6 edges
7. `migrateFromLocalStorage` - 6 edges
8. `saveTemplate()` - 5 edges
9. `IndexedDB Trip Persistence` - 5 edges
10. `Tab Persistence` - 5 edges

## Surprising Connections (you probably didn't know these)
- `handleSaveTemplate()` --calls--> `saveTemplate()`  [INFERRED]
  routes\+page.svelte → lib\export.js
- `handleSaveTrip()` --calls--> `saveTrip()`  [INFERRED]
  routes\+page.svelte → lib\storage.js
- `clearTripState()` --calls--> `clearTrip()`  [INFERRED]
  lib\store.js → lib\storage.js
- `refreshTripList()` --calls--> `getAllTrips()`  [INFERRED]
  routes\+page.svelte → lib\storage.js
- `handleSave()` --calls--> `updateTrip()`  [INFERRED]
  lib\components\TripHeader.svelte → lib\store.js

## Hyperedges (group relationships)
- **Normalized Trip State Layers** — store_tripStore, storage_indexedDbPersistence, store_normalizedTripModel [EXTRACTED 1.00]
- **Critical Hold Confirmation Flows** — PackingView_criticalItemConfirmation, CriticalConfirmModal_twoStepHoldConfirmation, TaskConfirmModal_holdConfirmation [EXTRACTED 1.00]
- **Ordered Collection Reordering** — ItemList_itemReordering, StageSection_taskReordering, store_updateAndSave [INFERRED 0.85]
- **Legacy Trip Migration Pipeline** — migration_localStorageLegacyTrip, migration_transformToFlatModel, migration_normalizedTripModel, migration_currentTripMetadata [EXTRACTED 1.00]
- **Trip Page Primary Flows** — page_tripInitialization, page_tripCreationFlow, page_tripImportFlow [EXTRACTED 1.00]
- **Section Organization Flows** — page_localDndProjection, page_dragReorderSections, page_assignmentFlow [EXTRACTED 1.00]
- **VISUAL_COMPOSITION** — visual:svelte_logo, shape:orange_outer_mark, shape:white_inner_ribbon [EXTRACTED 0.98]

## Communities

### Community 0 - "Route Mutations"
Cohesion: 0.11
Nodes (29): handleAddItem(), handleAddTask(), handleConfirmed(), handleDndFinalize(), addBag(), addCategory(), addItem(), addStage() (+21 more)

### Community 1 - "Component Workflows"
Cohesion: 0.09
Nodes (31): Bag Edit Flow, Bag Editing Entry Point, Category Edit Flow, Category Item Composition, Two Step Hold Confirmation, Item Edit Flow, Item Drag Reordering, Bag Grouped Packing View (+23 more)

### Community 2 - "Import And Store"
Cohesion: 0.09
Nodes (22): importPackyFile(), normalizeTrip(), clearTripState(), createTrip(), deleteTripById(), calculateDays(), formatDate(), handleAddBag() (+14 more)

### Community 3 - "Migration And Shell"
Cohesion: 0.17
Nodes (18): Static Prerender Configuration, Root App Shell, Theme Toggle, Current Trip Metadata, Legacy localStorage Trip Data, migrateFromLocalStorage, Normalized Trip Model, transformToFlatModel (+10 more)

### Community 4 - "IndexedDB Storage"
Cohesion: 0.19
Nodes (15): clearTrip(), createTrip(), deactivateTrip(), deleteTripById(), getAllTrips(), getDB(), getTrip(), saveTrip() (+7 more)

### Community 5 - "Export Formatting"
Cohesion: 0.36
Nodes (11): buildTemplateExport(), buildTripExport(), downloadPackyFile(), formatDate(), formatSaveDate(), formatSaveTime(), generateFilename(), pad2() (+3 more)

### Community 6 - "Trip Header"
Cohesion: 0.4
Nodes (3): formatDate(), handleSave(), ordinal()

### Community 7 - "Favicon Asset"
Cohesion: 0.4
Nodes (6): favicon.svg, Svelte, src/lib/assets/favicon.svg, orange outer Svelte mark, white inner S ribbon, Svelte logo

## Ambiguous Edges - Review These
- `Theme Store` → `SvelteKit HTML Shell`  [AMBIGUOUS]
  src/app.html · relation: conceptually_related_to

## Knowledge Gaps
- **12 isolated node(s):** `Delete Category Cascade Cleanup`, `Bag Editing Entry Point`, `Item Edit Flow`, `Category Edit Flow`, `Stage Edit Flow` (+7 more)
  These have ≤1 connection - possible missing edges or undocumented components.

## Suggested Questions
_Questions this graph is uniquely positioned to answer:_

- **What is the exact relationship between `Theme Store` and `SvelteKit HTML Shell`?**
  _Edge tagged AMBIGUOUS (relation: conceptually_related_to) - confidence is low._
- **Why does `handleSaveTemplate()` connect `Import And Store` to `Export Formatting`?**
  _High betweenness centrality (0.071) - this node is a cross-community bridge._
- **Why does `saveTemplate()` connect `Export Formatting` to `Import And Store`?**
  _High betweenness centrality (0.066) - this node is a cross-community bridge._
- **What connects `Delete Category Cascade Cleanup`, `Bag Editing Entry Point`, `Item Edit Flow` to the rest of the system?**
  _12 weakly-connected nodes found - possible documentation gaps or missing edges._
- **Should `Route Mutations` be split into smaller, more focused modules?**
  _Cohesion score 0.11 - nodes in this community are weakly interconnected._
- **Should `Component Workflows` be split into smaller, more focused modules?**
  _Cohesion score 0.09 - nodes in this community are weakly interconnected._
- **Should `Import And Store` be split into smaller, more focused modules?**
  _Cohesion score 0.09 - nodes in this community are weakly interconnected._