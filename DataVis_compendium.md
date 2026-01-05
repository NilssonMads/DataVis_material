# Data Visualization Compendium (Lectures Summary)

One-stop, Google-Docs-style recap of the lecture PDFs in `Lectures/`. Use it as a study guide or as a checklist when designing and evaluating visualizations.

## Course Map (coverage)
- Intro and pipeline: lecture01
- Visual encoding: lecture02
- Basic charts: lecture03
- Interaction: lecture04
- Visualization design: lecture05
- Data preprocessing: lecture06
- Recap 1st half: lecture07
- Multivariate charts: 08_lecture_cut
- Temporal data: lecture09
- Geospatial data: lecture10
- Graphs and trees: lecture11
- Visual analytics: lecture13
- 3D visualization guest lecture: VisualizationLecture3DViz
- Chart lexicon/cheat sheet: DataVis 2025 Chart Lexicon

## Visualization Pipeline and Models
- Pipeline (Haber, McNabb; Card, Mackinlay): Data -> Data transformation -> Visual mapping -> Rendering -> Perception -> Insight; interaction can steer any stage.
- Munzner nested model: Domain problem -> Data/task abstraction -> Visual encoding/interaction design -> Algorithm implementation. Validate at each level; errors propagate downward.
- van Wijk model: Data + specification -> visualization -> perception -> knowledge; interaction refines specification.

## Visual Encoding (lecture02)
- Marks: points, lines, areas, volumes, cells. Channels: position, length, angle, area, color (hue, luminance, saturation), shape, texture, motion.
- Channel effectiveness (approx.): position > length/angle > area > color luminance > color hue > shape/texture. Match channel type to data type (quantitative vs ordinal vs nominal).
- Labeling: avoid overlap; prefer direct labels over legends; use consistent units and scales; note when log or diverging scales are appropriate.
- Rendering choices: antialias, transparency for overplotting, ordering (draw less important first), aggregation/binning when dense.
- Visual literacy: watch for deceptive choices (truncated axes, 3D bars, mismatched scales).

## Basic Chart Types (lecture03)
- Scatterplots: raw, binned, splatterplots; add density contours for overplotting; connected scatterplots for time-labeled pairs.
- Lines and areas: line charts and stepped variants; area and stacked area for cumulative quantities; beware stacking with mixed baselines.
- Bars and columns: simple, grouped, stacked; histograms for distribution; choose bin sizes carefully.
- Radial variants: radar (few variables), coxcomb/polar area; remember angle and radius perception limits.
- Radial vs Cartesian: use radial for periodic patterns; otherwise Cartesian often clearer.

## Interaction Patterns (lecture04)
- Overview + detail, zoom & pan: start broad, then drill in; maintain context cues (minimap, scale bars).
- Focus + context, lenses: fisheye/lens to magnify local region while showing surroundings.
- Multiple coordinated views with brushing & linking: select in one view to highlight/filter in others; keep consistent encodings across views.
- Tangible and direct manipulation: sketching, dragging, sliders; support undo/redo and visible history.
- Interaction goals: parameter tuning, visual queries, annotation, personalization for diverse tasks.

## Visualization Design (lecture05)
- Problem framing: who are the users, what decisions, what latency? Identify success criteria early.
- Data abstraction: types (tables, networks, spatial, temporal, text), attribute types (quantitative, ordinal, nominal), size, quality.
- Task abstraction: search, lookup, compare, summarize, filter, derive, annotate; map to operations in view.
- Design processes: Design Activity Framework, 5 Design Sheet method; iterate sketches -> prototypes -> evaluation.
- Evaluation: analytical (heuristics, expressiveness/effectiveness), empirical (user tests, A/B, benchmarks), and expert reviews. Close the loop to refine at higher nested-model levels.

## Data Preprocessing (lecture06)
- Challenges: unknown characteristics, bad data (nulls, outliers, mixed types), too many points.
- Profiling: basic stats, distributions, missingness patterns; detect duplicates and inconsistencies.
- Cleaning: type coercion, deduplication, outlier handling, imputation, unit harmonization.
- Reduction: sampling (random, stratified), binning/aggregation (histograms, hex bins, tiles), filtering, feature selection/engineering, normalization/standardization.
- Provenance: track transformations for reproducibility; expose what was filtered or imputed to users.

## Multivariate Visualization (08_lecture_cut)
- Point-based: ternary plots (3 components summing to constant), scatterplot matrices (SPLOMs) with diagonal histograms/density, RadViz and RadViz Deluxe (anchors on circle, barycentric placement).
- Polyline-based: parallel coordinates (quantitative) and parallel sets (binned/categorical); radar charts for small variable counts; consider ordering and scaling of axes.
- Nested/hierarchical: mosaic plots (area-encoded partitions), trellis/small multiples for facetting.
- Other approaches: glyphs (e.g., star plots, Chernoff faces), pixel-based displays; use brushing/linking to combat overplotting.

## Temporal Data (lecture09)
- Characterize time: points vs intervals; regular vs irregular sampling; cyclic patterns (daily/weekly/seasonal); absolute vs relative time.
- Encodings: line/area/stacked for continuous series; timelines/Gantt for tasks; horizon graphs for dense series; small multiples for comparisons; 1D/2D heatmaps.
- Interval reasoning: triangular model (time before/during/after) to choose comparisons; show uncertainty when endpoints fuzzy.
- Event-centric: time maps (time since previous vs until next), outflow diagrams for event sequences; instance plots for sparse events.
- Interaction: stack zooming for long series; ChronoLenses for local magnification without losing context.

## Geospatial Data (lecture10)
- Map foundations: projection choice matters; preserve topology when possible, show scale/legend.
- Area-valued: choropleth (normalized rates), cartogram (area scaled by value).
- Point-valued: dot maps, binned/hex maps, bubble maps; isopleth/contour maps for continuous fields; chorochromatic for categorical points.
- Flow and movement: flow maps/origin-destination, space-time cubes, animated traces; small multiples for time slices.
- Tips: avoid misleading color scales (sequential for magnitude, diverging around neutral); handle MAUP (modifiable areal unit problem) with aggregation choices.

## Graph Visualization (lecture11)
- Terms: nodes, edges; degree; weights; trees (acyclic, rooted), parent/child/sibling/leaf, branching factor.
- Layout families: node-link (force-directed, hierarchical/sugiyama, radial trees), adjacency matrices (good for dense graphs, ordering critical), hybrid approaches.
- Tasks: neighborhood and path finding, cluster/community detection, comparing subgraphs, attribute inspection on nodes/edges.
- Design choices: edge bundling to reduce clutter; encode weights with thickness/opacity; use interaction for filtering and path highlighting; maintain mental map in dynamic graphs.

## 3D Visualization (guest lecture)
- When 3D helps: inherently volumetric data (medical CT/MRI), terrain and architectural models, flow fields, occlusion-aware spatial context.
- Pitfalls: occlusion, perspective distortion, navigation burden; avoid gratuitous 3D for simple tables/bars.
- Techniques: volume rendering, slicing/clipping planes, depth cues (lighting, shadows, fog), interactive camera with landmarks.

## Visual Analytics (lecture13)
- Definition (Keim et al. 2008): combines automated analysis with interactive visualization to enable reasoning on large/complex data.
- Challenges: long-running computation vs real-time interaction; need to expose model state/uncertainty; goals are evolving and often ill-defined.
- Typical loop: data prep -> model/algorithm run -> visual inspection -> steer parameters/select new hypotheses -> rerun -> report; requires provenance and user-in-the-loop controls.

## Chart Lexicon Highlights (DataVis 2025 Chart Lexicon)
- 1D quantitative: histogram, violin, box/whisker, beeswarm.
- 1D qualitative: bar, pie (few categories), waffle, radar (few categories), treemap (if hierarchical/time-scaled areas).
- 1D temporal: instance plot, time map, 1D heatmap.
- 1D spatial (points): dot map, heatmap, binned dotmap.
- 2D quantitative x quantitative: scatter/binned scatter, bubble, heatmap, Marimekko (binned), mosaic (for categorical), parallel sets (binned).
- 2D quantitative x temporal: line/area; stacked bar/area for categorical over time.
- 2D spatial: choropleth/cartogram (areas); bubble/iso/chorochromatic for points; flow maps; space-time cube or small multiples for time.
- 3D or higher: scatterplot matrix, parallel coordinates, ternary (sum-to-1), radar/RadViz (few dims).

## Quick Design Checklist
- Do users and tasks match the chosen encodings? Are scales and units explicit?
- Are color scales appropriate (sequential/diverging/categorical) and accessible (contrast, colorblind-safe)?
- Is overplotting mitigated (binning, opacity, contours, aggregation)?
- Are interactions discoverable and reversible? Are multiple views linked consistently?
- Did preprocessing choices (sampling, imputation, binning) get communicated to viewers?
- Are you evaluating at all nested-model levels (domain -> data/task -> encoding -> algorithm)?

## How to Use
- Start with the course map to jump to relevant lecture PDFs.
- Use the chart lexicon as a quick picker given data types.
- When designing, walk through: data/task abstraction -> pick encodings -> add interaction -> verify with checklist -> evaluate with users.
