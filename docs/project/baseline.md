# Core Gaming Baseline Specification

**Release:** v1.0

## Required state

| Control | Required state |
|---|---|
| Windows gaming OS | Installed and bootable |
| Game Mode | ON |
| Game DVR | OFF |
| Game DVR policy | OFF |
| Power scheme | Ultimate Performance |
| GPU PnP state | OK |
| GPU driver state | Present and operational |
| NTFS TRIM | Enabled |
| Pagefile | Present and operational |
| System volume | Healthy |
| Cleanup | Completed |
| Post-reboot validation | PASS |

## Preparation sequence

1. Establish Windows baseline.
2. Inspect storage and free-space state.
3. Clean user/system temporary files.
4. Stop Windows Update/BITS services.
5. Clean Windows Update download cache.
6. Restart required services.
7. Run DISM component cleanup.
8. Configure Game Mode.
9. Disable Game DVR/background capture.
10. Confirm Ultimate Performance.
11. Reboot.
12. Run post-reboot validation.
13. Freeze the baseline.

## Storage handling

The baseline does not require manual SSD retrim after cleanup.

TRIM remains enabled so Windows can issue normal TRIM operations through the storage stack. Manual retrim is reserved for an explicit maintenance decision.

## Validation principle

A configuration is accepted from observed post-reboot state, not merely from command completion.
