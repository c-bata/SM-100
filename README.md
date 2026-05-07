![Header by ChatGPT](./images/header.jpg)

SM-100 is a compact CoreXY 3D printer featuring a 120x70x70 mm build volume within a 200x180x280 mm footprint. Built for safety and space-efficiency in small apartments, it utilizes a stainless-steel sheet-metal chassis and runs entirely on 100W USB-PD power.

## But Why?

Living in a small Tokyo apartment with a pet dog makes finding a safe, permanent spot for a 3D printer a challenge.

My previous machine, a Bambu Lab A1 Mini, is an excellent printer. However, as a "bed-slinger," it requires more operating space than its footprint suggests. Additionally, placing an open-frame printer where a dog can reach it risks accidental contact with moving parts and exposure to VOCs (Volatile Organic Compounds) during the melting process.

SM-100 was designed to solve these issues. Drawing from my experience building small-form-factor printers like the [Voron 0.2](https://github.com/voronDesign/Voron-0) and [Fraxinus 00w2](https://fraxinus.jp/en/docs/micro-printers/), I focused on three design priorities:

1. **Ultra-compact footprint**: Achieved by using a Bowden extruder, side-mounted part cooling, and external USB-PD power to eliminate the need for an internal PSU.
2. **Safety and Durability**: Utilizing stainless-steel sheet metal for a rigid, fire-resistant structure.
3. **Thermal Management**: Placing A/B/Z motors and electronics in a dedicated bottom compartment to keep them cool (via front intake fans).

Below is a size comparison with the Voron V0.

![SM-100 vs Voron V0](./images/sm-100-vs-voron-v0.jpg)

## Design Highlights

**Lower-Mounted Motion System** — Unlike traditional CoreXY designs, the A/B motors are located in the bottom compartment, driving the gantry via 5mm stainless-steel shafts. This lowers the center of gravity and allows the front intake fans to cool the motors, electronics, and Z-drive simultaneously without requiring extra airflow in the upper chamber.

**Bowden Extruder and Side-Mounted Cooling** — By using a Bowden setup and mounting four 4020 part-cooling fans to the sides of the enclosure, the toolhead remains extremely light. This reduction in mass significantly improves motion quality for such a small-scale machine.

**Stainless-Steel Sheet-Metal Construction** — Aluminum extrusions (common in printers like the Voron V0) typically require 15–20 mm of clearance per member, which adds significant bulk. Sheet metal provides comparable rigidity with a much thinner profile, enabling the SM-100's compact size. Furthermore, the bolt-together panel design offers better fire resistance and easier maintenance; individual panels can be removed to access components without a full teardown.

**USB PD Power Delivery** — By running entirely on 100W USB-PD, the machine eliminates the bulky internal power supply, further reducing the overall footprint and simplifying cable management.

## CAD Files

| Front View | Rear View |
| ---------- | --------- |
| ![CAD front view](./images/cad-front.jpg) | ![CAD rear view](./images/cad-rear.jpg) |

The current CAD archive is available here:

- [CAD/SM-100.step.zip](./CAD/SM-100.step.zip)

The archive currently contains the main STEP file for the project.

> [!WARNING]
> **Experimental Release**: Some components (pulleys, belts, screws, motors, bearings, and sensors) are currently excluded from the CAD data to respect third-party redistribution licenses. Full assembly files and manuals are not yet available. Building this printer is currently considered a high-difficulty task.

Depending on community interest, I plan to provide:

- Complete assembly CAD files
- A full Bill of Materials (BOM)
- Detailed assembly instructions

## Current Status

SM-100 is currently a prototype and should be treated as experimental hardware. This repository serves as a design documentation release rather than a complete, ready-to-build consumer guide.

## Acknowledgements

This project was heavily inspired by the Fraxinus 00 series and the Fraxinus community. Specifically, the implementation of Bowden extrusion and USB-PD power in a compact enclosure was influenced by their innovative work.

Fraxinus community: [fraxinus.jp/en/](https://fraxinus.jp/en/)

## License

See the [LICENSE](./LICENSE) file for details.
