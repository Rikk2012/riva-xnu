# MSM8917 SoC layer

This directory is deliberately minimal. It identifies the SoC and its four Cortex-A53 cores but does not claim that any of the HakiOS SC7280-family drivers apply.

## Memory-map status

No physical addresses or IRQs are asserted yet. This is intentional: a guessed MMIO address can hang or destabilize the target. Fill this table only from the exact Redmi 5A DTB and verify against the matching board firmware.

| Block | DT node / source | Base | Size | IRQ | Status |
|---|---|---:|---:|---:|---|
| DRAM | `/memory` | TBD | TBD | n/a | not extracted |
| reserved memory | `/reserved-memory` | TBD | TBD | n/a | not extracted |
| GIC | interrupt-controller node | TBD | TBD | TBD | not extracted |
| architected timer | `arm,armv8-timer` | architectural | n/a | TBD | not extracted |
| UART / debug console | chosen stdout-path + UART node | TBD | TBD | TBD | not extracted |
| display / MDP / DSI | display nodes | TBD | TBD | TBD | not extracted |
| eMMC | MMC controller node | TBD | TBD | TBD | not extracted |
| touch | I2C/SPI controller + touchscreen node | TBD | TBD | TBD | not identified |
| PMIC / SPMI | PMIC and arbiter nodes | TBD | TBD | TBD | not extracted |

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

The current common HakiOS SoC-argument generator is documented for the newer SC7280 layout; it is not a substitute for an MSM8917-specific parser and manual review.
