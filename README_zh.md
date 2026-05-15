![Header by ChatGPT](./images/header.jpg)

[English](./README.md) | [日本語](./README_ja.md) | 简体中文 | [한국어](./README_ko.md)

SM-100 是一款紧凑型 CoreXY 3D 打印机，在 200x180x280 mm 的占地内实现了 120x70x70 mm 的成型体积。
它面向小户型中的日常实用场景而设计，采用不锈钢钣金机架，并且整机仅依靠 100W USB-PD 供电。

## But Why?

在东京狭小的公寓里和一只小狗一起生活时，要给 3D 打印机找到一个安全且可以长期摆放的位置，并不是一件容易的事。

我之前使用的 Bambu Lab A1 Mini 是一台非常优秀的打印机。但作为一台 bed-slinger，它实际使用时所需要的空间比外形尺寸看起来更大。
开放式机架在我的居住环境里还有两个顾虑：一是狗有可能接触到机器，存在误碰运动部件的风险；二是很难把 VOC 和异味顺利排到室外。

SM-100 正是为了解决这些问题而设计的。结合我制作 [Fraxinus 00w2](https://fraxinus.jp/en/docs/micro-printers/#fraxinus00w2)、[Fraxinus 00cw](https://fraxinus.jp/en/docs/community/#fraxinus00cw)、[Fraxinus 00tcw](https://x.com/c_bata_/status/1891012343326261727) 以及 [Voron 0.2](https://github.com/voronDesign/Voron-0) 等紧凑型 3D 打印机的经验，我在设计时尤其重视以下三个方向。

1. **Compact Footprint**: 我使用 3D 打印机的频率有明显的阶段性。有些月份会频繁打印，也有些时候几乎完全不用。忙起来时，打印机可能会连续几周闲置，如果它占用的生活空间太大，就会越来越难以合理地长期保留。对我来说，足够紧凑是长期拥有一台 3D 打印机的重要前提。
2. **Thermal Management**: 步进电机温度过高会导致扭矩下降，并缩短使用寿命。我之前那台使用 LDO NEMA 14 电机的 Voron 0.2，在加入主动散热之前，偶尔会因为扭矩下降而出现丢步。如果给每个电机都单独加一个风扇，风扇数量又会变得太多。因此在 SM-100 上，我把 A/B/Z 电机和电子部件都集中放在下方独立舱室中，由前部进风风扇统一冷却。
3. **Fire Safety**: 对于一台要在家中使用的机器来说，防火性非常重要。主结构使用不锈钢钣金，相比大量依赖打印件的结构，可以在保持高刚性的同时进一步降低起火风险。

到目前为止，SM-100 是我最喜欢的一台自制 3D 打印机。下面和 Voron 0.2 的对比图也能看出，它在保持日常使用所需打印质量的同时，整体尺寸仍然相当紧凑。
它没有近年商用打印机常见的一些高级功能，例如多色打印，但它的零件数量较少，工具头结构也很简单，因此维护和维修都比较直接。正因为这种简洁性，我认为它是一台可以长期使用下去的机器。

![SM-100 vs Voron V0](./images/sm-100-vs-voron-v0.jpg)

## Design Highlights

**Lower-Mounted Motion System** — 与传统 CoreXY 设计不同，A/B 电机位于底部舱室，通过 5 mm 不锈钢轴驱动龙门。这不仅降低了整机重心，也让前部进风风扇可以同时冷却电机和电子部件。

**Bowden Extruder and Side-Mounted Cooling** — 通过采用 Bowden 结构，并在打印腔两侧各布置 4020 零件冷却风扇，工具头得以保持极轻的重量。

**Sheet-Metal Chassis** — 与 Voron V0 等机型使用的铝型材框架相比，钣金结构可以用更薄的截面实现相近的刚性，这也是 SM-100 能够做得如此紧凑的原因之一。同时，它的防火性也优于使用打印件作为外壳的方案。

**MGN9C Linear Rails** - 线性导轨的价格会随着长度明显变化，但 SM-100 使用的 100 mm 和 150 mm 导轨在 AliExpress 上仍然相对容易接受。即便是便宜的导轨，通常也比低成本的光轴加轴承方案更不容易出现明显间隙。Voron 0.2 使用的是 MGN7H，但我在 SM-100 上选择了 MGN9C，因为 M2 螺丝更容易松动，而且以我的经验来看，MGN7H 更容易出现较明显的晃动。我也听说这种问题会随着磨损而变得更加明显。

**Support for NEMA14 and NEMA17 Stepper Motors** - 我原本计划使用 NEMA 14 步进电机，以尽可能让机器保持紧凑，但考虑到 NEMA 17 更容易买到，最终也提供了对 NEMA 17 的支持。我自己这台 SM-100 上使用的电机，实际上就来自一台被我拆解的廉价二手打印机。如果不是追求非常高的打印速度，价格实惠的 NEMA 17 电机已经完全够用。

**USB PD Power Delivery** — 整机仅使用 100W USB-PD 供电，因此无需体积较大的内置电源，也进一步压缩了整机占地。

## CAD Files

| Front View | Rear View |
| ---------- | --------- |
| ![CAD front view](./images/cad-front.jpg) | ![CAD rear view](./images/cad-rear.jpg) |

当前的 CAD 压缩包可在这里获取：

- [CAD/SM-100.step.zip](./CAD/SM-100.step.zip)

目前该压缩包中包含的是项目的主 STEP 文件。

> [!WARNING]
> **Experimental Release**: 由于需要尊重第三方再分发许可，部分组件（包括皮带轮、皮带、螺丝、电机、轴承和传感器）目前没有包含在 CAD 数据中。完整装配文件和装配说明也尚未提供。目前要制作这台打印机，整体难度仍然较高。

如果社区有足够兴趣，我计划后续补充：

- 完整装配 CAD 文件
- 完整物料清单（BOM）
- 详细装配说明

## Acknowledgements

这个项目深受 Fraxinus 00 系列以及 Fraxinus 社区的启发。尤其是在紧凑型机箱中实现 Bowden 挤出和 USB-PD 供电的思路，直接受到了他们创新实践的影响。

Fraxinus community: [fraxinus.jp/en/](https://fraxinus.jp/en/)

## License

详细信息请参阅 [LICENSE](./LICENSE)。
