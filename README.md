![Header by ChatGPT](./images/header.jpg)

[日本語はこちら](./README_ja.md)

SM-100 is a compact CoreXY 3D printer featuring a 120x70x70 mm build volume within a 200x180x280 mm footprint.
Designed for compact, practical use in small apartments, it utilizes a stainless-steel sheet-metal chassis and runs entirely on 100W USB-PD power.

## But Why?

Living in a small Tokyo apartment with a pet dog makes finding a safe, permanent spot for a 3D printer a challenge.

My previous machine, a Bambu Lab A1 Mini, is an excellent printer. However, as a bed-slinger, it requires more operating space than its footprint suggests.
An open-frame printer also raised two concerns for my living situation: it could be reached by my dog, creating a risk of accidental contact with moving parts, and it made it difficult to vent VOCs and odors outdoors.

SM-100 was designed to solve these issues. Drawing from my experience building compact 3D printers like the [Fraxinus 00w2](https://fraxinus.jp/en/docs/micro-printers/#fraxinus00w2), [Fraxinus 00cw](https://fraxinus.jp/en/docs/community/#fraxinus00cw), [Fraxinus 00tcw](https://x.com/c_bata_/status/1891012343326261727), and [Voron 0.2](https://github.com/voronDesign/Voron-0), I focused on three design priorities:

1. **Compact Footprint**: My use of 3D printers goes through phases. Some months I print often, while in others I barely use one at all. When life gets busy, a printer can sit unused for weeks, and if it takes up too much space, it becomes harder to justify keeping around. For me, compactness is essential to owning a 3D printer long term.
2. **Thermal Management**: Excessive heat in stepper motors can reduce torque and shorten motor life. On my Voron 0.2, which used LDO NEMA 14 steppers, I occasionally ran into skipped steps before adding active cooling. Adding a dedicated fan to each motor would have meant too many fans, so on the SM-100 I placed the A/B/Z motors and electronics in a dedicated lower compartment, where they can all be cooled by the front intake fans.
3. **Fire Safety**: For a machine intended for home use, fire safety is a critical consideration. Using stainless-steel sheet metal for the main structure helps reduce fire risk compared with printed parts, while still providing excellent rigidity.

So far, the SM-100 is my favorite custom 3D printer I have built. As the comparison with the Voron 0.2 below shows, it is fairly compact while still offering practical print quality for everyday use.
It lacks some of the advanced features found in modern commercial printers, such as multi-color printing, but its small number of parts and simple toolhead make maintenance and repairs straightforward. That simplicity is a big part of why I think it is a machine I can keep using for years.

![SM-100 vs Voron V0](./images/sm-100-vs-voron-v0.jpg)

## Design Highlights

**Lower-Mounted Motion System** — Unlike traditional CoreXY designs, the A/B motors are located in the bottom compartment, driving the gantry via 5mm stainless-steel shafts. This lowers the center of gravity and allows the front intake fans to cool the motors and electronics simultaneously.

**Bowden Extruder and Side-Mounted Cooling** — By using a Bowden setup and placing four 4020 part-cooling fans on either side of the print chamber, the toolhead remains extremely light.

**Sheet-Metal Chassis** — Stainless-Steel Sheet-Metal Construction — Compared with aluminum extrusion frames used in printers like the Voron V0, sheet metal provides comparable rigidity with a much thinner profile, enabling the SM-100's compact size. It also offers better fire resistance than printed enclosure parts.

**MGN9C Linear Rails** - The cost of linear rails varies by length, but the 100 mm and 150 mm rails used on the SM-100 are still relatively affordable on AliExpress. Even inexpensive rails tend to have less play than low-cost linear shaft-and-bearing setups. While the Voron 0.2 uses MGN7H rails, I chose MGN9C for the SM-100 because M2 screws are easier to loosen, and in my experience MGN7H rails are more likely to have noticeable play. I have also heard that this tends to get worse with wear over time.

**Support for NEMA14 and NEMA17 Stepper Motors** - I originally planned to use NEMA 14 stepper motors to keep the machine as compact as possible, but I decided to support NEMA 17 as well because they are much easier to source. The motors on my own SM-100 actually came from a cheap donor printer I disassembled. Unless you are aiming for very high print speeds, affordable NEMA 17 motors work just fine.

**USB PD Power Delivery** — By running entirely on 100W USB-PD, the machine eliminates the bulky internal power supply, further reducing the overall footprint.

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

## Acknowledgements

This project was heavily inspired by the Fraxinus 00 series and the Fraxinus community. Specifically, the implementation of Bowden extrusion and USB-PD power in a compact enclosure was influenced by their innovative work.

Fraxinus community: [fraxinus.jp/en/](https://fraxinus.jp/en/)

## License

See the [LICENSE](./LICENSE) file for details.
