# Awesome Framework

[![Awesome](https://awesome.re/badge.svg)](https://awesome.re)

A fork of a curated list of projects, tools, documentation and resources related to the Framework Laptop family.

This fork includes compatibility information for:

* **FW12** — Framework Laptop 12
* **FW13** — Framework Laptop 13
* **FW13 Pro** — Framework Laptop 13 Pro
* **FW16** — Framework Laptop 16

## Compatibility legend

Compatibility labels are intentionally conservative:

* ✅ **Verified** — officially supported by Framework or explicitly tested on that model.
* 🟡 **Expected** — not directly tested on that exact model, but expected to work because it uses the same standard, form factor or interface.
* ⚠️ **Generation-specific** — compatibility depends on the Mainboard / CPU generation, port position or configuration.
* ❌ **Incompatible** — known physical or technical incompatibility.
* ❔ **Unknown** — compatibility has not been verified.

> **Important**
> Compatibility with one Framework model does **not automatically** imply compatibility with every other Framework model.
>
> For example, Framework Expansion Cards share a common ecosystem across the Laptop 12, 13, 13 Pro and 16, while RAM, SSD form factors, Mainboards, chassis parts and required charger wattage can differ substantially.

## Contents

* [Disclaimer](#disclaimer)
* [Compatibility](#compatibility)
* [Expansion Cards](#expansion-cards)
* [Mainboard Development](#mainboard-development)
* [Embedded Controller Firmware Mods](#embedded-controller-firmware-mods)
* [Linux Support](#linux-support)
* [Accessories](#accessories)

  * [Chargers](#chargers)
  * [Docking Stations](#docking-stations)
  * [Cases and Sleeves](#cases-and-sleeves)
  * [Expansion Card Storage](#expansion-card-storage)
* [Hardware Support](#hardware-support)

  * [Storage](#storage)
  * [Memory](#memory)
  * [WiFi Cards](#wifi-cards)
* [Troubleshooting](#troubleshooting)
* [Community](#community)
* [Contributing](#contributing)

## Disclaimer

This repository and the resources within it are **COMPLETELY UNOFFICIAL** and not in any way endorsed or supported by Framework.

Your use of these guides and projects is **AT YOUR OWN RISK** and **MAY VOID YOUR WARRANTY.**

We ask that you do not reach out to Framework support about problems caused by unofficial modifications. For community projects, use the project's GitHub Issues/Discussions or the Framework community instead.

> **Note**
> Parts listed as community validated are not necessarily on Framework's list of officially supported parts.
>
> `✅ Verified` can mean either **officially supported** or **actually tested by the community**, depending on the description. These two should not be considered equivalent.

## Compatibility

### Framework Expansion Card ecosystem

Official Framework Expansion Cards use the same Expansion Card ecosystem across:

| Model                   | Expansion Cards |
| ----------------------- | --------------- |
| Framework Laptop 12     | ✅ Supported     |
| Framework Laptop 13     | ✅ Supported     |
| Framework Laptop 13 Pro | ✅ Supported     |
| Framework Laptop 16     | ✅ Supported     |

The **capabilities of individual slots can differ**, especially for DisplayPort, USB4, Thunderbolt and USB power.

Third-party Expansion Cards following Framework's mechanical and electrical specification are generally marked `🟡 Expected` on models on which the author has not explicitly tested them.

### Power adapters

Framework currently pairs/recommends approximately:

| Model                   | Framework adapter |
| ----------------------- | ----------------: |
| Framework Laptop 12     |         60W USB-C |
| Framework Laptop 13     |         60W USB-C |
| Framework Laptop 13 Pro |        100W USB-C |
| Framework Laptop 16     |        240W USB-C |

A lower-power USB-C PD charger may still negotiate charging on some models, but that does **not** make it equivalent to the recommended adapter.

For this list:

* A charger validated on **FW13** can normally also be suggested for **FW12** when it meets the same USB-PD requirements and wattage.
* A 60–65W charger is **not automatically marked fully compatible with FW13 Pro or FW16** simply because USB-C charging works.
* Chargers meeting or exceeding the manufacturer's recommended wattage can be considered separately.

### Storage form factors

| Model                   | Main SSD form factor               |
| ----------------------- | ---------------------------------- |
| Framework Laptop 12     | M.2 2230 NVMe                      |
| Framework Laptop 13     | M.2 2280 NVMe                      |
| Framework Laptop 13 Pro | M.2 2280 NVMe                      |
| Framework Laptop 16     | M.2 2280 NVMe + secondary M.2 2230 |

This means an M.2 2280 SSD listed for FW13 **must not be assumed compatible with FW12**.

### Memory

Memory compatibility is particularly generation-dependent.

* Older Intel Framework Laptop 13 generations use **DDR4 SO-DIMM**.
* Newer Framework Laptop 13 AMD generations use **DDR5 SO-DIMM**.
* Framework Laptop 12 uses **DDR5 SO-DIMM**.
* Framework Laptop 16 uses **DDR5 SO-DIMM**.
* Framework Laptop 13 Pro varies by Mainboard; some versions use **DDR5 SO-DIMM**, while Intel Core Ultra Series 3 uses **LPCAMM2**.

Always check the exact Mainboard generation before purchasing RAM.

---

## Expansion Cards

Framework uses the same physical Expansion Card ecosystem across FW12, FW13, FW13 Pro and FW16, but port capabilities depend on the Mainboard and slot used.

* [Josh_Cook]()

  * [UART Expansion Card](https://github.com/jyancat/UART-Expansion-Card) / [Store](https://lectronz.com/products/uart-expansion-card) — Complete UART Expansion Card, available pre-assembled or as design files.
  * **Compatibility:** 🟡 FW12 · ✅/🟡 FW13 · 🟡 FW13 Pro · 🟡 FW16
  * Third-party card. Models not explicitly tested by the project should be considered expected rather than verified.

* [Spacehuhn](https://www.youtube.com/watch?v=IML9c_MsyQU)

  * [ESP32-S3 Expansion Card](https://github.com/SpacehuhnTech/framework) / [Store](https://spacehuhn.store/products/framework-esp32-s3-expansion-card) — ESP32-S3 development board with NeoPixel RGB LED and QWIIC/Stemma QT connector.
  * **Compatibility:** 🟡 FW12 · ✅/🟡 FW13 · 🟡 FW13 Pro · 🟡 FW16

* [Frameoscope](https://github.com/jlcjak/frameoscope) — Oscilloscope Expansion Card with 40 MSPS sampling rate, 10 MHz bandwidth and ngscopeclient support.

  * **Compatibility:** 🟡 FW12 · ✅/🟡 FW13 · 🟡 FW13 Pro · 🟡 FW16

* [DongleHider+](https://github.com/LeoDJ/FW-EC-DongleHiderPlus) — Expansion Card that hides USB dongles internally while retaining an external USB-A port.

  * **Compatibility:** 🟡 FW12 · ✅/🟡 FW13 · 🟡 FW13 Pro · 🟡 FW16

* [Framework 2 USB-C Expansion Card](https://github.com/altrup/Framework-2-USB-C-Expansion-Card) — Work-in-progress Expansion Card providing two USB-C ports with USB 3.2 support.

  * **Compatibility:** 🟡 FW12 · 🟡 FW13 · 🟡 FW13 Pro · 🟡 FW16
  * ⚠️ Actual USB speed, display output, USB-PD and other functionality may depend on the host Expansion Card slot.

     
* [Framework Expansion Card HDMI Shell](https://www.printables.com/model/1594979-framework-expansion-card-hdmi-shell#preview.file.OGQLU) — Replacement 3D-printable shell for the Framework HDMI Expansion Card, useful if you want to customize your Expansion Card aesthetically or if the original shell is broken.

  * **Compatibility:** ✅ FW12 · ✅ FW13 · ✅ FW13 Pro · ✅ FW16
  * Uses the standard Framework Expansion Card form factor; exact fit with different HDMI Expansion Card revisions should be checked before printing.


---

## Mainboard Development

Most older community Mainboard projects were designed around the Framework Laptop 13 Mainboard.

Framework Laptop 13 and Framework Laptop 13 Pro Mainboards share substantial official chassis compatibility, but this does **not automatically validate old third-party enclosures** for every newer Mainboard.

Framework Laptop 12 and Framework Laptop 16 use different Mainboard/chassis designs.

* [Mainboard Reference](https://github.com/FrameworkComputer/Mainboard) — Official physical and electrical Mainboard reference and 3D-printable enclosure.

  * **Compatibility:** ⚠️ FW13 · ⚠️ FW13 Pro
  * Check the exact Mainboard generation/reference files before fabrication.

* [WhatTheFilament](https://github.com/whatthefilament)

  * [Framework-Motherboard-Reference-CAD](https://github.com/whatthefilament/Framework-Motherboard-Reference-CAD) — To-scale CAD reference of the Mainboard.

    * **Compatibility:** ✅/⚠️ FW13 · 🟡 FW13 Pro · ❌ FW12 · ❌ FW16

  * [Frame-WorkStation](https://github.com/whatthefilament/Frame-WorkStation) — Desktop enclosure.

    * **Compatibility:** ✅/⚠️ FW13 · 🟡 FW13 Pro · ❌ FW12 · ❌ FW16

  * [Framework-Desktop-Adapter](https://github.com/whatthefilament/Framework-Desktop-Adapter) — ATX mount adapter.

    * **Compatibility:** ✅/⚠️ FW13 · 🟡 FW13 Pro · ❌ FW12 · ❌ FW16

  * [Framework-Tablet](https://github.com/whatthefilament/Framework-Tablet) — Tablet conversion case.

    * **Compatibility:** ✅/⚠️ FW13 · 🟡 FW13 Pro · ❌ FW12 · ❌ FW16

  * [FrameStation](https://github.com/whatthefilament/FrameStation) — Game-console-style enclosure.

    * **Compatibility:** ✅/⚠️ FW13 · 🟡 FW13 Pro · ❌ FW12 · ❌ FW16

  * [Framework-Test-Bench](https://github.com/whatthefilament/Framework-Test-Bench) — Development/test bench.

    * **Compatibility:** ✅/⚠️ FW13 · 🟡 FW13 Pro · ❌ FW12 · ❌ FW16
   
  * [Beth Deck rev. 1.5](https://www.printables.com/model/1051411-framework-portable-handheld-case-beth-deck-rev-15?lang=it) — 3D-printable portable handheld enclosure built around a Framework Laptop 13 Mainboard, turning it into a handheld-style portable computer.

    * **Compatibility:** ✅/⚠️ FW13 Mainboard · 🟡 FW13 Pro Mainboard · ❌ FW12 · ❌ FW16
    * ⚠️ Mainboard generation and physical fit should be checked before building.


* [DIY Perks — "Triple-Screen Laptop DONE RIGHT!"](https://www.youtube.com/watch?v=aUKpY0o5tMo) — Custom triple-screen portable computer using a Framework Mainboard and battery.

  * **Compatibility/reference:** FW13-based project.
  * Newer Mainboards may require adaptation.

---

## Embedded Controller Firmware Mods

EC firmware is **Mainboard-generation-specific**. Do not flash EC firmware simply because two systems are both called Framework Laptop 13.

* [DHowett](https://github.com/DHowett) — AKA *The EC Guy*

  * [Hacking your Framework Laptop’s EC for fun and profit](https://www.howett.net/posts/2022-04-adding-an-ec-feature-1/) — Good introduction to Framework EC hacking.

    * **Compatibility:** ⚠️ FW13 / generation-specific

  * [ECTool.EFI](https://github.com/DHowett/FrameworkHacksPkg) — EFI Shell application for interacting with/flashing supported ECs.

    * **Compatibility:** ⚠️ Mainboard-specific

* [EC Firmware Source Code](https://github.com/FrameworkComputer/EmbeddedController)

  * **Compatibility:** ⚠️ Check the branch and exact Mainboard before use.

---

##  Support

* [Official Framework Linux Support](https://frame.work/linux) — Officially supported distros and setup guides.

  * **Compatibility:** ✅ FW12 · ✅ FW13 · ✅ FW13 Pro · ✅ FW16, depending on generation/distro.

* [Official Battery Life Instructions](https://knowledgebase.frame.work/en_us/optimizing-ubuntu-battery-life-Sye_48Lg3) — Instructions for increasing battery life on Ubuntu.

  * **Compatibility:** ⚠️ Primarily follow the guide for the model/generation it documents; some concepts may apply elsewhere.

* [Arch Wiki — Framework Laptop](https://wiki.archlinux.org/title/Framework_Laptop) — Community-maintained Framework Linux information.

  * **Compatibility:** ⚠️ Multiple Framework generations/models; check the relevant subsection.

* [LinuxLaptops Wiki — 2022 Framework Laptop DIY Edition 12th Gen Intel](https://github.com/lhl/linuxlaptops/wiki/2022-Framework-Laptop-DIY-Edition-12th-Gen-Intel-Batch-1)

  * **Compatibility:** ✅ FW13 12th Gen Intel only.

* [Common Problems](/linux/common-problems.md) — Collection of common Linux problems and solutions.

  * **Compatibility:** ⚠️ Check each issue individually.
 
* [FrameFetch](https://github.com/pietraTarzanelli/FrameFetch) — Framework-focused terminal hardware dashboard inspired by Fastfetch. It renders hardware information around an ASCII representation of the Framework Laptop mainboard and can also run as a lightweight live system monitor.

  * **Compatibility:** ❔ FW12 · ✅/⚠️ FW13 · ❔ FW13 Pro · ❔ FW16
  * Currently developed and tested primarily on selected Framework Laptop 13 revisions, especially AMD Ryzen AI 300 Series systems. Other Framework generations and configurations may require additional support or calibration.
  * Linux-oriented; hardware detection depends on the kernel, firmware and system interfaces exposed by the specific machine.


---

## Accessories

### Chargers

#### Official Framework Power Adapter

* [Official Framework Power Adapter](https://frame.work/products/power-adapter?v=FRANCEPH0B) — Framework first-party USB-PD adapter.
* **Compatibility:**

  * ✅ FW12 — 60W is Framework's standard adapter class.
  * ✅ FW13 — 60W is Framework's standard adapter class.
  * ✅ FW13 Pro — Framework confirms both its 60W and 100W adapters are compatible with FW13/FW13 Pro.
  * ⚠️ FW16 — can use USB-C PD, but Framework recommends a much higher-power adapter for normal/full-performance use.

#### Anker 65W Nano

* [Anker 65W Nano](https://www.amazon.com/dp/B08T5QN2TR) — Community-validated single-port 65W USB-PD charger.
* **Compatibility:**

  * 🟡 FW12 — meets/exceeds the normal 60W adapter class.
  * ✅ FW13 — community validated.
  * ⚠️ FW13 Pro — below Framework's normal 100W recommendation.
  * ⚠️ FW16 — substantially below Framework's normal 240W recommendation.

#### Anker 735 Charger (Nano II 65W)

* [Anker 735 Charger](https://www.anker.com/eu-en/products/a2667) — Community-validated 65W USB-PD/PPS charger with two USB-C ports and one USB-A port.
* **Compatibility:**

  * 🟡 FW12
  * ✅ FW13
  * ⚠️ FW13 Pro
  * ⚠️ FW16

> A charger being able to negotiate USB-PD does not mean it can sustain the laptop's maximum performance or prevent battery discharge under heavy load.

---

### Docking Stations

* [Official Thunderbolt Compatibility](https://knowledgebase.frame.work/does-the-framework-laptop-support-thunderbolt-rkjEJn4Jt) — Framework information on Thunderbolt/USB4 support.

  * **Compatibility:** ⚠️ Generation-specific.

* [Anker 777 Thunderbolt 4 Docking Station](https://www.amazon.com/gp/product/B0928W3XHD) — HDMI, USB-A, USB-C, SD and audio.

  * ✅ **FW13 12th Gen Intel + Ubuntu 22.04:** community validated; original report states all I/O worked out of the box.
  * ⚠️ **FW13:** Thunderbolt/USB4 capability depends on Mainboard generation.
  * ⚠️ **FW12:** 13th Gen Intel does not provide Thunderbolt; newer Intel Core Series 3 systems do.
  * ⚠️ **FW13 Pro:** depends on Mainboard; Intel Core Ultra Series 3 is Thunderbolt-certified, while AMD implementations use USB4.
  * 🟡 **FW16:** AMD systems expose USB4 on supported ports; exact dock functionality should still be checked.

---

### Cases and Sleeves

Physical accessories should be treated separately from electronic compatibility.

* [Case Logic Reflect 13"](https://www.caselogic.com/en-us/laptop-bags/laptop-sleeves/case-logic-reflect-13-laptop-sleeve-_-3204690) — Community [tested](https://github.com/Morpheus636/awesome-framework/issues/10#issuecomment-1325427414) laptop sleeve.

  * ✅ FW13
  * 🟡 FW13 Pro — likely suitable as a generic 13" sleeve, but not marked tested here.
  * ⚠️ FW12 — physically smaller; may fit loosely rather than correctly.
  * ❌ FW16
  * Do **not** get the MacBook-specific version referenced by the original report, as it does not fit the tested FW13 correctly.

* [Tomtoc Laptop Shoulder Bag 13–13.5"](https://www.amazon.com/dp/B072L4R2DY) — Community [validated](https://github.com/Morpheus636/awesome-framework/issues/10#issuecomment-1325465369).

  * ✅ FW13
  * 🟡 FW13 Pro
  * ⚠️ FW12 — oversized
  * ❌ FW16

* [FINPAC Hard Case for 13" MacBook](https://www.amazon.com/dp/B088WNMW8N) — Community [validated](https://github.com/Morpheus636/awesome-framework/issues/10#issuecomment-1325754958) carrying case.

  * ✅ FW13
  * 🟡 FW13 Pro
  * ⚠️ FW12
  * ❌ FW16

---

### Expansion Card Storage

These accessories store loose Framework Expansion Cards and are mostly independent of laptop model because the Expansion Card form factor is shared.

* [Expansion Card Holder](https://github.com/josh1244/Expansion_Card_Holder) — 3D-printable holder for four Framework Expansion Cards.

  * **Compatibility:** ✅/🟡 FW12 · FW13 · FW13 Pro · FW16 Expansion Cards

* [Framework Card Storage](https://github.com/aristeu/framework_card_storage) — OpenSCAD Expansion Card storage case with magnetic closure.

  * **Compatibility:** ✅/🟡 FW12 · FW13 · FW13 Pro · FW16 Expansion Cards

---

## Hardware Support

### Storage

#### Official compatibility

* [Officially Validated SSD List](https://knowledgebase.frame.work/en_us/what-storage-ssd-parts-are-compatible-with-the-framework-laptop-rJOOeHU0_)

  * ⚠️ Always select the exact Framework model/Mainboard.

#### M.2 2280 SSDs

The SSDs below are **M.2 2280 NVMe** drives.

Therefore:

* ❌ **FW12** — FW12 uses an M.2 2230 SSD slot.
* ✅/🟡 **FW13** — M.2 2280 supported.
* ✅/🟡 **FW13 Pro** — M.2 2280 supported.
* ✅/🟡 **FW16** — M.2 2280 supported as its primary SSD slot.

Individual controller/firmware compatibility can still differ.

* [SK Hynix Gold P31](https://www.amazon.com/dp/B08DKB5LWY) — Community validated. Available in 500GB, 1TB and 2TB.

  * **Compatibility:** ❌ FW12 · ✅ FW13 · 🟡 FW13 Pro · 🟡 FW16

* [Crucial P2](https://www.amazon.com/gp/product/B086BGWNY8/) — Community validated. Available in 256GB, 500GB, 1TB and 2TB.

  * **Compatibility:** ❌ FW12 · ✅ FW13 · 🟡 FW13 Pro · 🟡 FW16

* [EDILOCA EN600 Pro](https://ediloca.net/products/ediloca-en600-pro-ssd-2tb-pcle-3-0x4-nvme-m-2-2280-up-to-3500mb-s-internal-solid-state-drive-slc-cache-3d-nand-tlc-graphene-cooling-sticker-storage-for-pc-desktop-and-laptops) — Community validated M.2 2280 NVMe SSD.

  * **Compatibility:** ❌ FW12 · ✅ FW13 · 🟡 FW13 Pro · 🟡 FW16

* [Western Digital PC SN530](https://documents.westerndigital.com/content/dam/doc-library/en_us/assets/public-western-digital/product/internal-drives/pc-sn530-ssd/product-brief-sn530-ssd.pdf) — Community validated NVMe SSD.

  * ⚠️ **Check the exact physical size before purchasing**, since PC SN530 variants exist in different M.2 form factors.
  * **Compatibility:** ⚠️ Model/variant dependent.

---

### Memory

#### Official compatibility

* [Officially Validated DRAM List](https://knowledgebase.frame.work/en_us/what-memory-dram-parts-are-compatible-with-the-framework-laptop-ry_jbS8Ru)

  * ⚠️ RAM compatibility depends heavily on Mainboard generation.

#### DDR4-3200 modules

The following modules are DDR4 SO-DIMMs and therefore belong to **older Intel Framework Laptop 13 generations**, not the newer DDR5 platforms.

* [Crucial CT2K16G4SFD832A](https://www.amazon.com//dp/B07Q7T9NSC) — Community validated DDR4-3200 CL22 RAM, 32GB kit (2×16GB).

  * ✅ FW13 with DDR4 Mainboard
  * ❌ FW12
  * ❌ FW13 AMD DDR5 generations
  * ❌ FW13 Pro
  * ❌ FW16

* [SK Hynix HMAA1GS6CJR6N](https://www.amazon.com/dp/B0BM9YL1C5/) — Community validated DDR4-3200 RAM, 8GB.

  * ✅ FW13 with DDR4 Mainboard
  * ❌ FW12
  * ❌ FW13 DDR5 Mainboards
  * ❌ FW13 Pro
  * ❌ FW16

* [SK Hynix HMA851S6CJR6N](https://www.amazon.com/dp/B092RK7KLM/) — Community validated DDR4-3200 RAM, 4GB.

  * ✅ FW13 with DDR4 Mainboard
  * ❌ FW12
  * ❌ FW13 DDR5 Mainboards
  * ❌ FW13 Pro
  * ❌ FW16

> Do not classify RAM compatibility only by chassis name. Always include the Mainboard generation.

---

### WiFi Cards

* [Officially Validated WiFi Card List](https://knowledgebase.frame.work/en_us/what-wifi-parts-are-compatible-with-the-framework-laptop-rytGfHU0d)

  * **Compatibility:** ⚠️ FW12 · FW13 · FW13 Pro · FW16
  * WiFi compatibility depends on Mainboard/chipset generation and should be checked individually.

---

## Troubleshooting

When adding troubleshooting entries, specify the affected model and preferably the Mainboard generation.

Recommended format:

`[FW13 / AMD Ryzen AI 300] Description of problem`

or

`[FW12 / Intel 13th Gen] Description of problem`

Avoid generic `[Framework Laptop]` labels when the issue is hardware-specific.

---

## Community

* [Framework Forums](https://community.frame.work)
* [Framework Discord](https://discord.com/invite/Framework)
* [Framework Subreddit](https://reddit.com/r/framework)

---

## Contributing

This list's Contribution Guidelines can be found [here.](/contributing.md)

When contributing a new hardware item, please include compatibility information where possible:

```text
Compatibility:
✅ FW13 — tested
🟡 FW13 Pro — expected, same interface
❌ FW12 — incompatible form factor
❔ FW16 — not tested
```

Whenever possible, distinguish between:

1. **Officially supported**
2. **Community tested**
3. **Expected to work because of a shared standard**
4. **Not tested**
5. **Known incompatible**

This prevents compatibility with one Framework generation from being incorrectly propagated to unrelated models.
