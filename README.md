# VoltaRF

VoltaRF is a homebrew software defined radio (SDR), it is based on parts found inside a cheap 'n old satellite DVB-S television receiver.

![](https://cdn.hackclub.com/01a0f4a6-1cf1-7ab2-9a29-ce6e490bda89/volta-rf-layer-overview.gif)
![](https://cdn.hackclub.com/01a0f4a4-c322-753e-a820-26821cb9c48e/volta-rf-front.png)
![](https://cdn.hackclub.com/01a0f4a4-b42a-7eef-a88b-945dd3e868cc/volta-rf-back.png)

VoltaRF could Also be used as a good ol' development board around the CH32H417 flagship platform, all GPIOs are exposed!

## Background

Due to the fact that RTL-SDRs are quite hard to find locally (due to restrictions), I have decided to build my own alternative out of already existing and easily available appliances.

The RTL-SDR itself being a by product of a television related product, I decided to base my own SDR on satellite television receiver parts, most notably the RF tuner found inside those.

After some testing I was able of finding out one very common RF tuner chip, the RDA5815. When it was put to testing I was able of getting it to tune in the range of 50MHz and all the way up to 2.5GHz (covering amateur bands, ISM, commercial broadcasting as well as radionavigation and air traffic.)

The RDA5815 tuner claims a bandwidth range of 4MHz all the way up to 40MHz, thankfully the LPF is configurable over I2C. I can only guarantee 4MHz of bandwidth, unless we overclock the ADCs.

## Main Parts

- Qorvo's SGL0622Z (LNA)
- SkyWorks' RDA5815M (RF Interface & Tuner)
- WCH's CH32H417QEU6 (MCU, ADC and USB Interface)
  [Here you can find the entirety of the BOM.](https://github.com/Triax-Labs/volta-rf/blob/main/hardware/production/bom.csv)

## Production

Production is done through [JLCPCB](https://jlcpcb.com)'s PCBA service.

| Item | Price | Qty      | Where                        |
| ---- | ----- | -------- | ---------------------------- |
| PCB  | $8    | 5 Boards | [JLCPCB](https://jlcpcb.com) |
| PCBA | $120  | 5 Boards | [JLCPCB](https://jlcpcb.com) |

_Those are estimated prices, and they don't include shipping._

Production files could be found inside `/hardware/production`, the BOM has been optimized for JLC's library of parts.

When ordering an assembled board, make sure all footprints are rotated in their right place with dots aligning.

Some parts don't exist on JLCPCB, so you will have to source and assemble them yourself, most notable one is the RDA5815M RF tuner chip, you can buy it from AliExpress instead.

---

[![CC BY-NC-ND 4.0](https://licensebuttons.net/l/by-nc-nd/4.0/88x31.png)](http://creativecommons.org/licenses/by-nc-nd/4.0/)
