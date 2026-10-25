# Repository and Dependency Audit

## Audit status

This is an evidence log. An entry marked **Unknown** has not been verified and must not be treated as implemented.

| Item | Status | Evidence / next action |
|---|---|---|
| Original game engine | Unknown | Identify from lawful, reliable technical documentation or source metadata |
| Original source code available | Unknown | Inspect repository contents and licensing |
| Source language and compiler | Unknown | Determine from actual source files and project manifests |
| Third-party dependencies | Unknown | Inventory include directives, manifests, and linked libraries |
| Graphics API and shader format | Unknown | Identify from source and documented engine requirements |
| Audio backend | Unknown | Identify from source and dependencies |
| Input handling | Unknown | Identify from source and platform assumptions |
| Xbox 360 toolchain available | Unverified | Confirm compiler, linker, headers, and libraries in CI |
| Minimal Xbox executable builds | Not tested | Add a minimal target build only after toolchain is confirmed |
| `default.xex` generated | Not verified | Require successful target link/package logs |
| Runs on Xbox 360 RGH | Not tested | Requires an actual console test and recorded result |

## Evidence collection procedure

1. List all tracked files and identify source, manifests, assets, and build scripts.
2. Read the project license and any third-party notices before reusing code or assets.
3. Record each dependency, version, license, and whether source is available.
4. Identify platform APIs and classify each as portable, replaceable, or target-specific.
5. Confirm toolchain installation and compiler target with version output and a minimal test.
6. Store logs or CI run URLs for every claimed successful build.
7. Record on-console tests separately from desktop tests.

## Reporting rules

- Do not infer that an empty or documentation-only repository contains an implementation.
- Do not count a plan, stub, or placeholder as a working subsystem.
- Do not claim a binary is an Xbox 360 executable without a verified target toolchain and successful build output.
- Do not claim runtime compatibility without testing on the target hardware.
- Keep the license and asset provenance visible throughout development.
