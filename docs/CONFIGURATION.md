# Configuration

## Configuration Scope

This document defines how configuration information is organized and published. Exact project-specific configuration is retained under `docs/project/` and/or the repository's operational directories.

## Configuration Rules

- Record the intended state, not just the command used to create it.
- Separate baseline configuration from temporary experiments.
- Keep machine-specific and OS-specific configurations distinguishable.
- Mark incomplete captures as `PENDING`.
- Do not publish secrets or private authentication material.

## Validation

A configuration change is considered complete only after the relevant validation procedure has passed and the result has been recorded.

## Backup Boundary

Large system images, raw private captures, and sensitive backup artifacts should remain outside the public repository unless there is a deliberate and safe reason to publish them.
