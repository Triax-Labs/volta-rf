# VoltaRF

VoltaRF is a homebrew software defined radio (SDR), it is based on parts found inside a cheap 'n old satellite DVB-S television receiver.
<img width="1570" height="891" alt="gif showing PCB layers" src="https://github.com/user-attachments/assets/7834f187-9ba2-4d0f-aab8-66bedd255f9f" />

## Parts
- Qorvo's SGL0622Z (LNA)
- SkyWorks' RDA5815M (RF Interface & Tuner)
- WCH's CH32V317WCU6 (MCU, ADC and USB Interface)
- China's AMS1117-3.3v (Voltage Regulator, _yes_)

The RDA5815 tuner claims a bandwidth range of 4MHz all the way up to 40MHz, thankfully the LPF is configurable over I2C.

## Production
Production is done through [JLCPCB](https://jlcpcb.com)'s PCBA service. Revision I should be around 60$ for both the PCB as well as assembly at the quantity of 5 boards.

Production files could be found inside `/hardware/production`, the BOM has been optimized for JLC's library of parts.

Revision I should be around 60$ for both the PCB as well as the assembly, this excludes shipping costs however.

When ordering an assembled board, make sure all footprints are rotated in their right place with dots aligning.

Some parts don't exist on JLCPCB, so you will have to source and assemble them yourself, most notable one is the RDA5815M RF tuner chip, you can buy it from AliExpress instead.

## Firmware
Given that I hadn't received a prototype board yet, firmware remains a to be desired thing.

This all only sits inside a design file. However, the idea is simple, clock both ADCs really fast, sample I and Q at the same time with each ADC, stream those samples over USB UAC using DMA, and let the computer do the rest.

---
[![CC BY-NC-ND 4.0](https://licensebuttons.net/l/by-nc-nd/4.0/88x31.png)](http://creativecommons.org/licenses/by-nc-nd/4.0/)
