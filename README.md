# riva-xnu
Nothing


## HakiOS Redmi 5A bring-up

Experimental device scaffold for Xiaomi Redmi 5A (`riva`, Qualcomm MSM8917 / Snapdragon 425). The configuration intentionally disables unported phone drivers and does not invent MMIO addresses, IRQs, or a UEFI platform description.

See:
- [Device status](device.conf)
- [riva defconfig](configs/riva_defconfig)
- [MSM8917 SoC layer](soc/README.md)
- [Mu-Silicium UEFI bring-up notes](uefi/README.md)
- [GitHub Actions build](.github/workflows/build-riva.yml)

This repository is a build/bring-up scaffold, not a claim of a bootable Redmi 5A port. The UEFI job remains skipped until the actual riva Mu-Silicium package and locally extracted, device-owned XBL driver payload are available.
