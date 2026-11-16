# rivaPkg placeholder

No valid Mu-Silicium DSC/FDF exists here yet. This directory is a marker for the future MSM8917 platform package.

Before adding build files, inspect the exact Mu-Silicium tree produced by `uefi/apply.sh riva`, then derive the package from the closest supported Qualcomm platform only after comparing:
- SoC/board identifiers and SEC/PEI initialization;
- memory map and reserved regions;
- GIC, timer, UART and watchdog;
- display and storage DXE drivers;
- device-specific XBL driver binaries and their INF metadata.

A package that compiles is not necessarily bootable; validate it on the actual Redmi 5A.
