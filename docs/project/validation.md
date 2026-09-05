# Core Gaming Validation

## Validation method

Validation is performed after reboot.

```powershell
Get-ItemProperty "HKCU:\Software\Microsoft\GameBar" |
    Select-Object AllowAutoGameMode,AutoGameModeEnabled

Get-ItemProperty "HKCU:\System\GameConfigStore" |
    Select-Object GameDVR_Enabled

Get-ItemProperty `
    "HKLM:\SOFTWARE\Policies\Microsoft\Windows\GameDVR" `
    -ErrorAction SilentlyContinue |
    Select-Object AllowGameDVR

powercfg /getactivescheme

fsutil behavior query DisableDeleteNotify

Get-CimInstance Win32_VideoController |
    Select-Object Name,DriverVersion,DriverDate,Status |
    Format-Table -AutoSize

Get-CimInstance Win32_PageFileUsage |
    Select-Object Name,AllocatedBaseSize,CurrentUsage,PeakUsage |
    Format-Table -AutoSize
```

## Acceptance criteria

- Game Mode reports `1 / 1`.
- Game DVR reports `0`.
- Game DVR policy reports `0`.
- Ultimate Performance is active.
- GPU status is `OK`.
- TRIM is enabled (`DisableDeleteNotify = 0`).
- Pagefile is present.
- System volumes report healthy state during baseline inspection.
- No unresolved baseline error remains after reboot.

## Final state

All six Windows gaming environments in the retained fleet passed their post-reboot baseline checks during the v1.0 setup cycle.
