# riva Mu-Silicium UEFI platform — not yet implemented

The common HakiOS UEFI build expects a device platform under `devices/riva/uefi/files/`. The platform must be based on the actual Redmi 5A XBL firmware and its device tree.

This scaffold intentionally does not invent a `.dsc`, `.fdf`, memory map, DXE driver list, or Qualcomm package name. The upstream redwood platform is for a much newer SoC and cannot be copied as an MSM8917 platform.

## Required work

1. Identify the exact Redmi 5A board variant and firmware build.
2. Obtain the matching XBL image from the device's own firmware package.
3. Extract the device's UEFI drivers locally with UEFIReader into `uefi/files/Binaries/riva/`.
4. Inspect the extracted INF files and determine the real Mu-Silicium package, library classes, protocols, and DXE dispatch order.
5. Create the MSM8917 `rivaPkg` DSC/FDF and the platform configuration from verified DTB/XBL data.
6. Build and test UEFI independently before attempting to start XNU.

Do not commit proprietary extracted driver binaries. Keep them local or supply them to a private build environment. The GitHub Actions workflow skips the UEFI job while the local driver payload is absent.
