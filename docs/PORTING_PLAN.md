# Code of Honor 2 — Xbox 360 Port Plan

## Status and evidence policy

This document is a technical planning baseline, not evidence that the game currently builds or runs on Xbox 360. Do not mark a milestone complete until its source changes, build output, and test result are recorded.

Target: Xbox 360 RGH homebrew environment. Intended packaging goal: `default.xex`, produced only after a compatible toolchain and link configuration are validated.

## Parallel workstreams

### A. Source and dependency inventory
- Identify the original game's engine, source availability, language, compiler assumptions, and third-party dependencies.
- Record which components are available as source and which require replacement.
- Do not copy proprietary game assets or code without the necessary rights.

### B. Platform abstraction
- Define interfaces for filesystem access, timing, input, audio, and graphics.
- Keep platform-specific code behind narrow interfaces so desktop test builds can exercise logic independently.
- Document Xbox 360-specific assumptions instead of silently substituting desktop APIs.

### C. Rendering and content pipeline
- Inventory rendering features and shader/material assumptions before selecting an implementation.
- Create a minimal test scene using original or newly created test assets.
- Measure frame time and memory use on the target when hardware is available.

### D. Input, audio, and game loop
- Define controller mapping and input state transitions.
- Separate audio backend integration from gameplay code.
- Add deterministic tests for timing, pause/resume, and device initialization failure paths.

### E. Build and packaging
- First establish a host-side configure/build/test path for any portable modules.
- Validate the Xbox 360 compiler, linker, SDK headers/libraries, and final executable format separately.
- Produce `default.xex` only after the toolchain and linker configuration are verified; never rename an unrelated binary and call it an Xbox executable.

### F. Validation and reporting
- Track source implementation, successful compilation, automated tests, and on-console execution as separate measures.
- Attach build logs and test summaries to each milestone.
- Report unknowns as unknown; do not estimate a global completion percentage until the codebase and dependencies have been inventoried.

## Milestone sequence

1. **M0 — Repository baseline:** inspect files, license, branch state, and dependencies.
2. **M1 — Build feasibility:** document required toolchain and confirm a minimal target program can compile.
3. **M2 — Portable foundation:** establish platform interfaces and host-side tests.
4. **M3 — Subsystem prototypes:** validate graphics, input, audio, storage, and timing independently.
5. **M4 — Integration:** connect only components that have test evidence.
6. **M5 — Target packaging:** link and package the application as `default.xex`.
7. **M6 — Console validation:** record launch behavior, logs, stability, performance, and known limitations.

## Current checkpoint

The repository's README currently contains only the project title. The source inventory, engine identification, dependency audit, and target toolchain validation remain unverified. The next engineering task is to populate the repository with evidence-backed findings before committing to a porting architecture.
