# Graph Report - Packy2  (2026-05-13)

## Corpus Check
- 44 files · ~299,522 words
- Verdict: corpus is large enough that graph structure adds value.

## Summary
- 609 nodes · 1358 edges · 25 communities detected
- Extraction: 83% EXTRACTED · 17% INFERRED · 0% AMBIGUOUS · INFERRED: 228 edges (avg confidence: 0.8)
- Token cost: 0 input · 0 output

## Community Hubs (Navigation)
- [[_COMMUNITY_Community 0|Community 0]]
- [[_COMMUNITY_Community 1|Community 1]]
- [[_COMMUNITY_Community 2|Community 2]]
- [[_COMMUNITY_Community 3|Community 3]]
- [[_COMMUNITY_Community 4|Community 4]]
- [[_COMMUNITY_Community 5|Community 5]]
- [[_COMMUNITY_Community 6|Community 6]]
- [[_COMMUNITY_Community 7|Community 7]]
- [[_COMMUNITY_Community 8|Community 8]]
- [[_COMMUNITY_Community 9|Community 9]]
- [[_COMMUNITY_Community 10|Community 10]]
- [[_COMMUNITY_Community 11|Community 11]]
- [[_COMMUNITY_Community 12|Community 12]]
- [[_COMMUNITY_Community 13|Community 13]]
- [[_COMMUNITY_Community 14|Community 14]]
- [[_COMMUNITY_Community 15|Community 15]]
- [[_COMMUNITY_Community 16|Community 16]]
- [[_COMMUNITY_Community 17|Community 17]]
- [[_COMMUNITY_Community 18|Community 18]]
- [[_COMMUNITY_Community 19|Community 19]]
- [[_COMMUNITY_Community 20|Community 20]]
- [[_COMMUNITY_Community 28|Community 28]]
- [[_COMMUNITY_Community 29|Community 29]]
- [[_COMMUNITY_Community 30|Community 30]]
- [[_COMMUNITY_Community 32|Community 32]]

## God Nodes (most connected - your core abstractions)
1. `updateAndSave()` - 33 edges
2. `$()` - 26 edges
3. `updateAndSave()` - 26 edges
4. `V` - 25 edges
5. `L()` - 21 edges
6. `r()` - 20 edges
7. `j()` - 20 edges
8. `C()` - 19 edges
9. `y()` - 17 edges
10. `Ye` - 16 edges

## Surprising Connections (you probably didn't know these)
- `He()` --calls--> `j()`  [INFERRED]
  docs\_app\immutable\chunks\4rn19CJ8.js → docs\_app\immutable\nodes\1.CCOQ91-x.js
- `qe()` --calls--> `N()`  [INFERRED]
  docs\_app\immutable\chunks\4rn19CJ8.js → docs\_app\immutable\chunks\COIMkynW.js
- `Ze()` --calls--> `ee()`  [INFERRED]
  docs\_app\immutable\chunks\4rn19CJ8.js → docs\_app\immutable\nodes\0.AlpeKMn4.js
- `V()` --calls--> `L()`  [INFERRED]
  docs\_app\immutable\chunks\4rn19CJ8.js → docs\_app\immutable\chunks\D_lg2ool.js
- `tt()` --calls--> `ae()`  [INFERRED]
  docs\_app\immutable\chunks\4rn19CJ8.js → docs\_app\immutable\chunks\Cx7yElJE.js

## Hyperedges (group relationships)
- **Normalized Trip State Layers** — store_tripStore, storage_indexedDbPersistence, store_normalizedTripModel [EXTRACTED 1.00]
- **Critical Hold Confirmation Flows** — PackingView_criticalItemConfirmation, CriticalConfirmModal_twoStepHoldConfirmation, TaskConfirmModal_holdConfirmation [EXTRACTED 1.00]
- **Ordered Collection Reordering** — ItemList_itemReordering, StageSection_taskReordering, store_updateAndSave [INFERRED 0.85]
- **Legacy Trip Migration Pipeline** — migration_localStorageLegacyTrip, migration_transformToFlatModel, migration_normalizedTripModel, migration_currentTripMetadata [EXTRACTED 1.00]
- **Trip Page Primary Flows** — page_tripInitialization, page_tripCreationFlow, page_tripImportFlow [EXTRACTED 1.00]
- **Section Organization Flows** — page_localDndProjection, page_dragReorderSections, page_assignmentFlow [EXTRACTED 1.00]
- **VISUAL_COMPOSITION** — visual:svelte_logo, shape:orange_outer_mark, shape:white_inner_ribbon [EXTRACTED 0.98]

## Communities

### Community 0 - "Community 0"
Cohesion: 0.05
Nodes (93): _e(), $(), An(), at(), B(), Be(), bn(), br() (+85 more)

### Community 1 - "Community 1"
Cohesion: 0.04
Nodes (78): handleAddField(), handleDeleteGroup(), handleFieldChange(), handleFieldsDndFinalize(), handleRenameGroup(), buildTemplateExport(), buildTripExport(), downloadPackyFile() (+70 more)

### Community 2 - "Community 2"
Cohesion: 0.06
Nodes (49): A(), b(), K(), l(), N(), P(), q(), X() (+41 more)

### Community 3 - "Community 3"
Cohesion: 0.05
Nodes (31): addBag(), addCategory(), addItem(), addStage(), addTask(), assignCategoryToBag(), bind_prop(), deleteBag() (+23 more)

### Community 4 - "Community 4"
Cohesion: 0.06
Nodes (38): at(), Ge(), He(), it(), je(), nt(), qe(), rt() (+30 more)

### Community 5 - "Community 5"
Cohesion: 0.09
Nodes (43): $(), ae(), At(), be(), ce(), Ct(), dt(), Et() (+35 more)

### Community 6 - "Community 6"
Cohesion: 0.12
Nodes (22): _arrayLikeToArray(), _arrayWithoutHoles(), bind_select_value(), _createForOfIteratorHelper(), createMultiScroller(), dispatchConsiderEvent(), findRelevantScrollContainers(), findScrollableParents() (+14 more)

### Community 7 - "Community 7"
Cohesion: 0.11
Nodes (21): deactivateCurrentTrip(), clearTrip(), clearTripState(), createTrip(), createTrip$1(), deactivateCurrentTrip(), deactivateTrip(), deleteTripById() (+13 more)

### Community 8 - "Community 8"
Cohesion: 0.12
Nodes (17): alertToScreenReader(), _arrayWithHoles(), createShadowElData(), _defineProperty(), dispatchFinalizeEvent(), handleZoneFocus(), incrementActiveDropZoneCount(), initAria() (+9 more)

### Community 9 - "Community 9"
Cohesion: 0.14
Nodes (14): decrementActiveDropZoneCount(), destroyAria(), globalClickHandler(), globalKeyDownHandler(), handleDrop(), handleDrop$1(), moveDraggedElementToWasDroppedState(), resetIndexesCache() (+6 more)

### Community 10 - "Community 10"
Cohesion: 0.17
Nodes (12): dndzone(), dndzone$1(), dndzone$2(), hideElement(), isInt(), _objectWithoutProperties(), _objectWithoutPropertiesLoose(), scheduleDZForRemovalAfterDrop() (+4 more)

### Community 11 - "Community 11"
Cohesion: 0.2
Nodes (11): calcDistance(), calcDistanceFromPointToCenter(), copyStylesFromTo(), createDraggedElementFrom(), findCenter(), findCenterOfElement(), getAbsoluteRect(), getFeatureFlag() (+3 more)

### Community 12 - "Community 12"
Cohesion: 0.24
Nodes (11): buildTemplateExport(), buildTripExport(), downloadPackyFile(), formatDate(), formatSaveDate(), formatSaveTime(), generateFilename(), pad2() (+3 more)

### Community 13 - "Community 13"
Cohesion: 0.22
Nodes (9): Category Item Composition, Two Step Hold Confirmation, Item Drag Reordering, Bag Grouped Packing View, Critical Item Confirmation Flow, Stage Task Composition, Task Drag Reordering, Task Hold Confirmation (+1 more)

### Community 14 - "Community 14"
Cohesion: 0.29
Nodes (8): animateDraggedToFinalPosition(), cacheShadowRect(), calcInnerDistancesBetweenPointAndSidesOfElement(), findWouldBeIndex(), getAbsoluteRectNoTransforms(), getBoundingRectNoTransforms(), getVisibleRectRecursive(), isPointInsideRect()

### Community 15 - "Community 15"
Cohesion: 0.4
Nodes (6): destroy_effects(), link(), move(), pause_effects(), reconcile(), skip_to_branch()

### Community 16 - "Community 16"
Cohesion: 0.4
Nodes (6): favicon.svg, Svelte, src/lib/assets/favicon.svg, orange outer Svelte mark, white inner S ribbon, Svelte logo

### Community 17 - "Community 17"
Cohesion: 0.5
Nodes (4): animate(), css_property_to_camelcase(), css_to_keyframe(), dispatch_event()

### Community 18 - "Community 18"
Cohesion: 1.0
Nodes (2): Trip Metadata Editing, Quantity Expression Parser

### Community 19 - "Community 19"
Cohesion: 1.0
Nodes (2): IndexedDB Trip Persistence, Theme Store

### Community 20 - "Community 20"
Cohesion: 1.0
Nodes (2): Bag Edit Flow, Bag Editing Entry Point

### Community 28 - "Community 28"
Cohesion: 1.0
Nodes (1): Category Edit Flow

### Community 29 - "Community 29"
Cohesion: 1.0
Nodes (1): Item Edit Flow

### Community 30 - "Community 30"
Cohesion: 1.0
Nodes (1): Stage Edit Flow

### Community 32 - "Community 32"
Cohesion: 1.0
Nodes (1): Static Prerender Configuration

## Knowledge Gaps
- **14 isolated node(s):** `Quantity Expression Parser`, `IndexedDB Trip Persistence`, `Theme Store`, `Bag Edit Flow`, `Bag Editing Entry Point` (+9 more)
  These have ≤1 connection - possible missing edges or undocumented components.
- **Thin community `Community 18`** (2 nodes): `Trip Metadata Editing`, `Quantity Expression Parser`
  Too small to be a meaningful cluster - may be noise or needs more connections extracted.
- **Thin community `Community 19`** (2 nodes): `IndexedDB Trip Persistence`, `Theme Store`
  Too small to be a meaningful cluster - may be noise or needs more connections extracted.
- **Thin community `Community 20`** (2 nodes): `Bag Edit Flow`, `Bag Editing Entry Point`
  Too small to be a meaningful cluster - may be noise or needs more connections extracted.
- **Thin community `Community 28`** (1 nodes): `Category Edit Flow`
  Too small to be a meaningful cluster - may be noise or needs more connections extracted.
- **Thin community `Community 29`** (1 nodes): `Item Edit Flow`
  Too small to be a meaningful cluster - may be noise or needs more connections extracted.
- **Thin community `Community 30`** (1 nodes): `Stage Edit Flow`
  Too small to be a meaningful cluster - may be noise or needs more connections extracted.
- **Thin community `Community 32`** (1 nodes): `Static Prerender Configuration`
  Too small to be a meaningful cluster - may be noise or needs more connections extracted.

## Suggested Questions
_Questions this graph is uniquely positioned to answer:_

- **Why does `L()` connect `Community 0` to `Community 2`, `Community 4`, `Community 6`?**
  _High betweenness centrality (0.113) - this node is a cross-community bridge._
- **Why does `createMultiScroller()` connect `Community 6` to `Community 0`, `Community 3`?**
  _High betweenness centrality (0.096) - this node is a cross-community bridge._
- **Why does `error()` connect `Community 2` to `Community 0`, `Community 1`, `Community 7`?**
  _High betweenness centrality (0.093) - this node is a cross-community bridge._
- **Are the 6 inferred relationships involving `$()` (e.g. with `u()` and `C()`) actually correct?**
  _`$()` has 6 INFERRED edges - model-reasoned connections that need verification._
- **Are the 6 inferred relationships involving `L()` (e.g. with `.#c()` and `V()`) actually correct?**
  _`L()` has 6 INFERRED edges - model-reasoned connections that need verification._
- **What connects `Quantity Expression Parser`, `IndexedDB Trip Persistence`, `Theme Store` to the rest of the system?**
  _14 weakly-connected nodes found - possible documentation gaps or missing edges._
- **Should `Community 0` be split into smaller, more focused modules?**
  _Cohesion score 0.05 - nodes in this community are weakly interconnected._