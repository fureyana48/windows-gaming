# Architecture

## Overview

Describe the system as layers and components. Keep the architecture focused on responsibilities and boundaries rather than transient implementation details.

## Layers

1. **Hardware / Platform** — physical host or target platform.
2. **Core / Operating System** — stable OS and foundational configuration.
3. **Project Layer** — the configuration or workload documented by this repository.
4. **Operational Layer** — validation, maintenance, backup, and recovery procedures where applicable.

## Boundaries

Project-specific architecture is documented under `docs/project/`. The root documentation defines the common model; project documents provide the detailed implementation.

## Change Rule

Architectural changes should be recorded in `CHANGELOG.md` and, when significant, in a release note under `docs/releases/`.
