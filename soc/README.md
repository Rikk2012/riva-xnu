# MSM8917 SoC layer

This directory is deliberately minimal. It identifies the SoC and its four Cortex-A53 cores but does not claim that any of the HakiOS SC7280-family drivers apply.

## To populate

Use the exact Redmi 5A DTB, not a DTB from a different Xiaomi model or a generic MSM8917 board. Record and verify:
- `/memory` and all `reserved-memory` regions;
- `/cpus`, enable-method and PSCI/conduit details;
- GIC distributor/redistributor (if present), interrupt cells and timer interrupts;
- clock, reset, power-domain and regulator topology;
- SPMI/PMIC, RPM, watchdog and thermal nodes;
- display controller, panel, DSI/MDP, framebuffer handoff;
- touch controller bus/address/IRQ/reset GPIO;
- eMMC controller and its DMA/IOMMU mapping.

Do not put unverified values in `soc.args`. The current common HakiOS SoC-argument generator is documented for the newer SC7280 layout; it is not a substitute for an MSM8917-specific parser and manual review.
