# Graph Report - Packy2  (2026-05-12)

## Corpus Check
- 42 files · ~298,248 words
- Verdict: corpus is large enough that graph structure adds value.

## Summary
- 552 nodes · 1244 edges · 22 communities detected
- Extraction: 84% EXTRACTED · 16% INFERRED · 0% AMBIGUOUS · INFERRED: 202 edges (avg confidence: 0.8)
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

## God Nodes (most connected - your core abstractions)
1. `V` - 30 edges
2. `$()` - 30 edges
3. `updateAndSave()` - 26 edges
4. `C()` - 23 edges
5. `L()` - 22 edges
6. `R()` - 20 edges
7. `y()` - 17 edges
8. `U()` - 16 edges
9. `Ye` - 16 edges
10. `ge` - 15 edges

## Surprising Connections (you probably didn't know these)
- `r()` --calls--> `V`  [INFERRED]
  docs\_app\immutable\chunks\C8Ck_GPV.js → docs\_app\immutable\chunks\CVQ9EmUX.js
- `Z()` --calls--> `$()`  [INFERRED]
  docs\_app\immutable\chunks\CaEtWWdu.js → docs\_app\immutable\chunks\DR8F_ih-.js
- `Se()` --calls--> `H()`  [INFERRED]
  docs\_app\immutable\chunks\DlY2v1EQ.js → docs\_app\immutable\chunks\DR8F_ih-.js
- `we()` --calls--> `Ke()`  [INFERRED]
  docs\_app\immutable\entry\app.BxFx6Pa5.js → docs\_app\immutable\chunks\DTfgJWaI.js
- `U()` --calls--> `toString()`  [INFERRED]
  docs\_app\immutable\chunks\CaEtWWdu.js → docs\_app\immutable\nodes\2.D9yB5uDF.js

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
Cohesion: 0.04
Nodes (94): $(), An(), at(), B(), Be(), bn(), br(), bt() (+86 more)

### Community 1 - "Community 1"
Cohesion: 0.08
Nodes (47): $(), ae(), At(), be(), ce(), Ct(), dt(), Et() (+39 more)

### Community 2 - "Community 2"
Cohesion: 0.06
Nodes (40): I(), q(), R(), oe(), at(), B(), $e(), Ge() (+32 more)

### Community 3 - "Community 3"
Cohesion: 0.06
Nodes (16): bind_prop(), CategorySection(), css_property_to_camelcase(), css_to_keyframe(), flip(), get_option_value(), get_zoom(), ItemList() (+8 more)

### Community 4 - "Community 4"
Cohesion: 0.07
Nodes (34): addBag(), addCategory(), addStage(), clearTrip(), clearTripState(), deactivateCurrentTrip(), deactivateTrip(), deleteTripById() (+26 more)

### Community 5 - "Community 5"
Cohesion: 0.1
Nodes (25): y(), _(), current(), D(), data(), ee(), error(), F() (+17 more)

### Community 6 - "Community 6"
Cohesion: 0.09
Nodes (30): Bag Edit Flow, Bag Editing Entry Point, Category Edit Flow, Category Item Composition, Two Step Hold Confirmation, Item Edit Flow, Item Drag Reordering, Bag Grouped Packing View (+22 more)

### Community 7 - "Community 7"
Cohesion: 0.13
Nodes (23): u(), c(), f(), p(), S(), _arrayLikeToArray(), _arrayWithoutHoles(), bind_select_value() (+15 more)

### Community 8 - "Community 8"
Cohesion: 0.11
Nodes (19): addItem(), addTask(), assignCategoryToBag(), deleteBag(), deleteCategory(), deleteItem(), deleteStage(), deleteTask() (+11 more)

### Community 9 - "Community 9"
Cohesion: 0.12
Nodes (16): decrementActiveDropZoneCount(), destroyAria(), dndzone(), dndzone$1(), dndzone$2(), hideElement(), isInt(), _objectWithoutProperties() (+8 more)

### Community 10 - "Community 10"
Cohesion: 0.19
Nodes (13): buildTemplateExport(), buildTripExport(), downloadPackyFile(), formatDate(), formatSaveDate(), formatSaveTime(), generateFilename(), pad2() (+5 more)

### Community 11 - "Community 11"
Cohesion: 0.2
Nodes (12): dispatchConsiderEvent(), findShadowElementIdx(), globalClickHandler(), globalKeyDownHandler(), handleDraggedEntered(), handleDraggedIsOverIndex(), handleDraggedLeft(), handleDrop() (+4 more)

### Community 12 - "Community 12"
Cohesion: 0.2
Nodes (11): calcDistance(), calcDistanceFromPointToCenter(), copyStylesFromTo(), createDraggedElementFrom(), findCenter(), findCenterOfElement(), getAbsoluteRect(), getFeatureFlag() (+3 more)

### Community 13 - "Community 13"
Cohesion: 0.25
Nodes (9): createTrip(), createTrip$1(), importPackyFile(), migrateFromLocalStorage(), normalizeTrip(), now(), run_tasks(), saveTrip$1() (+1 more)

### Community 14 - "Community 14"
Cohesion: 0.22
Nodes (9): alertToScreenReader(), _arrayWithHoles(), dispatchFinalizeEvent(), handleZoneFocus(), initAriaOnBrowser(), instructionToHiddenDiv(), _iterableToArrayLimit(), _nonIterableRest() (+1 more)

### Community 15 - "Community 15"
Cohesion: 0.29
Nodes (8): createShadowElData(), _defineProperty(), incrementActiveDropZoneCount(), initAria(), _objectSpread2(), ownKeys(), registerDropZone(), registerDropZone$1()

### Community 16 - "Community 16"
Cohesion: 0.29
Nodes (8): animateDraggedToFinalPosition(), cacheShadowRect(), calcInnerDistancesBetweenPointAndSidesOfElement(), findWouldBeIndex(), getAbsoluteRectNoTransforms(), getBoundingRectNoTransforms(), getVisibleRectRecursive(), isPointInsideRect()

### Community 17 - "Community 17"
Cohesion: 0.4
Nodes (6): destroy_effects(), link(), move(), pause_effects(), reconcile(), skip_to_branch()

### Community 18 - "Community 18"
Cohesion: 0.4
Nodes (6): favicon.svg, Svelte, src/lib/assets/favicon.svg, orange outer Svelte mark, white inner S ribbon, Svelte logo

### Community 19 - "Community 19"
Cohesion: 0.6
Nodes (5): Current Trip Metadata, Legacy localStorage Trip Data, migrateFromLocalStorage, Normalized Trip Model, transformToFlatModel

### Community 20 - "Community 20"
Cohesion: 0.5
Nodes (2): r(), w

### Community 28 - "Community 28"
Cohesion: 1.0
Nodes (1): Static Prerender Configuration

## Knowledge Gaps
- **10 isolated node(s):** `Delete Category Cascade Cleanup`, `Theme Store`, `Bag Editing Entry Point`, `Category Edit Flow`, `Item Edit Flow` (+5 more)
  These have ≤1 connection - possible missing edges or undocumented components.
- **Thin community `Community 20`** (4 nodes): `r()`, `w`, `.constructor()`, `C8Ck_GPV.js`
  Too small to be a meaningful cluster - may be noise or needs more connections extracted.
- **Thin community `Community 28`** (1 nodes): `Static Prerender Configuration`
  Too small to be a meaningful cluster - may be noise or needs more connections extracted.

## Suggested Questions
_Questions this graph is uniquely positioned to answer:_

- **Why does `L()` connect `Community 0` to `Community 2`, `Community 5`, `Community 7`?**
  _High betweenness centrality (0.119) - this node is a cross-community bridge._
- **Why does `createMultiScroller()` connect `Community 7` to `Community 0`, `Community 3`?**
  _High betweenness centrality (0.099) - this node is a cross-community bridge._
- **Why does `$()` connect `Community 1` to `Community 2`, `Community 5`?**
  _High betweenness centrality (0.073) - this node is a cross-community bridge._
- **Are the 6 inferred relationships involving `V` (e.g. with `r()` and `_e()`) actually correct?**
  _`V` has 6 INFERRED edges - model-reasoned connections that need verification._
- **Are the 10 inferred relationships involving `$()` (e.g. with `Z()` and `oe()`) actually correct?**
  _`$()` has 10 INFERRED edges - model-reasoned connections that need verification._
- **Are the 22 inferred relationships involving `C()` (e.g. with `y()` and `data()`) actually correct?**
  _`C()` has 22 INFERRED edges - model-reasoned connections that need verification._
- **Are the 7 inferred relationships involving `L()` (e.g. with `ge()` and `.#c()`) actually correct?**
  _`L()` has 7 INFERRED edges - model-reasoned connections that need verification._