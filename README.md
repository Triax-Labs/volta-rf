# VoltaRF

VoltaRF is a homebrew software defined radio (SDR), it is based on parts found inside a cheap 'n old satellite DVB-S television receiver.

## Parts
- Qorvo's SGL0622Z (LNA)
- SkyWorks' RDA5815 (RF Interface & Tuner)
- WCH's CH32V317WCU6 (MCU, ADC and USB Interface)
- China's AMS1117-3.3v (Voltage Regulator, _yes_)

The RDA5815 tuner claims a bandwidth range of 4MHz all the way up to 40MHz, thankfully the LPF is configurable over I2C.

As of right now, this all only sits inside a design file, firmware still needs to be written. The goal is simple, clock both ADCs really fast, sample I and Q at the same time, stream those samples over USB UAC, let the computer do the rest.

---
[![CC BY-NC-ND 4.0](https://licensebuttons.net/l/by-nc-nd/4.0/88x31.png)](http://creativecommons.org/licenses/by-nc-nd/4.0/)
