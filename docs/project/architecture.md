# Core Gaming Architecture

## Layer model

```text
Hardware
   |
Windows OS
   |
Core Gaming v1.0
   |
+-----------------------------+
| Game runtime / launchers    |
| Game installation           |
| Game-specific configuration |
| Benchmarking                |
| Gameplay                    |
+-----------------------------+
```

Core Gaming is a stable configuration layer between Windows and the gaming workload layer.

## Standard controls

### Performance

The active Windows power scheme is **Ultimate Performance**.

### Scheduling

Windows Game Mode is enabled.

### Capture

Background Game DVR/capture is disabled through user configuration and the Windows GameDVR policy.

### Storage

TRIM remains enabled at the Windows storage stack. Manual `Optimize-Volume -ReTrim` is not routine maintenance.

### Virtual memory

Existing pagefile topology is preserved. Core Gaming does not impose one universal pagefile size because storage layouts differ.

## Stability principle

Performance tuning is subordinate to system stability.

Avoid:
- repeated manual SSD retrim;
- unnecessary pagefile resizing;
- speculative registry tweaks;
- unnecessary GPU-driver replacement;
- aggressive storage optimization;
- changes to the frozen server core.

## Scope boundary

Core Gaming ends when the Windows gaming environment is validated. Game installation and game-specific configuration are workloads above the Core Gaming layer.
