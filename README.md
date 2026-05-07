![Header by ChatGPT](./images/header.jpg)

SM-100 is a compact enclosed CoreXY 3D printer built around stainless-steel sheet-metal parts and USB PD 100W power delivery.

## At a Glance

- Overall size: approx. 200 x 180 x 280 mm (W x D x H)
- Build volume: 120 x 70 x 70 mm
- Motion system: CoreXY with leadscrew Z
- Structure: stainless-steel sheet-metal enclosure
- Linear motion: 100 mm rails
- Power input: USB PD 100W
- Control system: SKR Pico + Raspberry Pi Zero 2W
- Extruder: Bowden setup

## But Why?

I live in a small apartment in Tokyo with a small dog, so finding a safe place for a 3D printer has always been difficult.
My previous machine was a Bambu Lab A1 Mini — excellent hardware, but a bed-slinger takes up more space than its footprint suggests, and placing it where a dog can reach it risks accidental contact with moving parts.
I was also uneasy about running a machine that melts plastic in an open format near a small animal for extended periods, both because of the physical hazard and the VOC exposure.

![SM-100 vs Voron V0](./images/sm-100-vs-voron-v0.jpg)

That led me to design a compact enclosed CoreXY printer that keeps moving parts contained, reduces emissions inside the enclosure, and fits more naturally into an everyday living space.
Having built several small printers — including the Voron 0.2 and Fraxinus 00w2 — SM-100 draws on those experiences and focuses on the details I most wanted to improve.

The design is built around three priorities:

1. keeping the overall footprint as small as possible through a Bowden extruder, side-mounted part cooling, and external USB PD 100W power instead of an internal PSU
2. using stainless-steel sheet-metal parts for rigidity and fire resistance
3. placing the A/B/Z motors and electronics in the bottom compartment so they stay near the front intake fans and out of the hotter upper compartment

## Design Highlights

**Lower-Mounted Motion System** — Unlike most CoreXY printers, the A/B motors sit in the bottom compartment and drive the gantry through 5 mm stainless-steel shafts. This lowers the center of gravity and lets the front intake fans cool the motors, electronics, and Z drive together without needing dedicated airflow in the upper chamber.

**Bowden Extruder and Side-Mounted Cooling** — Using a Bowden setup and mounting the four 4020 part-cooling fans on the sides of the enclosure rather than on the toolhead keeps the toolhead light and compact, which helps with motion quality in a small machine.

**Stainless-Steel Sheet-Metal Construction** — Aluminium extrusion profiles, as used in machines like the Voron V0, typically require 15–20 mm of cross-section per member. In a machine this small, that bulk has a significant impact on the overall footprint. Sheet-metal parts can achieve comparable rigidity at a fraction of the thickness, which is one of the key reasons SM-100 can stay as compact as it is. The stainless-steel construction also reduces fire risk and makes the machine easier to service: individual panels can be removed to access the bed, toolhead, or electronics for re-tightening or replacement without tearing down the whole printer.

**USB PD Power** — The printer runs entirely on USB PD 100W, eliminating the need for an internal PSU and keeping the overall footprint small.

## About CAD File

| Front View | Rear View |
| ---------- | --------- |
| ![CAD front view](./images/cad-front.jpg) | ![CAD rear view](./images/cad-rear.jpg) |

The current CAD archive is available here:

- [CAD/SM-100.step.zip](./CAD/SM-100.step.zip)

The archive currently contains the main STEP file for the project.

> [!WARNING]
> Some components are intentionally not included in the CAD data yet.
> This applies to parts such as pulleys, belts, screws, motors, bearings, linear guides, and sensors, because I have not fully verified the redistribution licenses for those third-party CAD models.
> At the moment, full assembly files are not included, no assembly manual is available, and building this printer is still considered highly difficult.

If there is enough interest, I may later provide:

- complete assembly CAD files
- a BOM
- assembly instructions
- additional documentation after confirming the licenses of third-party models

## Current Status

SM-100 is a prototype and should be treated as experimental hardware.
It represents a tested design direction, but this repository is not yet intended to be a complete public build guide.

At this stage, the project is best understood as a design and documentation release rather than a ready-to-reproduce printer platform.

## Acknowledgements

Many of the design ideas behind this printer were inspired by the Fraxinus 00 series created by the Fraxinus community, especially the use of Bowden extrusion and USB PD power delivery in a compact enclosed machine.
I appreciate the work the community has shared and the influence it had on this project.

Fraxinus community: [fraxinus.jp/en/](https://fraxinus.jp/en/)

## License

See the [LICENSE](./LICENSE) file for details.
