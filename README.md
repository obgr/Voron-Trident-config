# Work in progress!
# Voron Trident  VT.638

## Repo layout
printer.cfg includes subconfig and submacros from config.d and macros.d respectively.

## Hardware
- Voron Trident
  - BTT Octopus Pro
  - Raspberry Pi 4
  - Steppers from LDO
    - A/B: 2x 42STH40-2004MAC
    - Z: 3x 42STH40-1684L300E
  - [Noctua NF-A6x25 FLX](https://noctua.at/en/nf-a6x25-flx) for electronics cooling.
  - [Voron X/Y Hall Effect Endstop](https://fermio.xyz/fermio-labs-gmbh/voron-x-y-hall-effect-endstop/endstop)
  - X Gantry
    - E3d Revo Voron
    - [Bondtech CHT Nozzle](https://www.bondtech.se/product/bondtech-cht-coated-brass-nozzle/)
    - Extruder: [Bondtech LGX® Large Gears eXtruder](https://www.bondtech.se/product/lgx-large-gears-extruder/)
    - Stealthburner
    - Sunnon Fan
  - Bed
    - [VORON Build Plate, 250 x 250 mm from Fermio Labs](https://fermio.xyz/fermio-labs-gmbh/voron-build-plate-250-x-250-mm/)
    - [Keenovo Silicone Heatmat, 240 x 240 mm, 230 V/AC, 300 W](https://fermio.xyz/keenovo-international-group-limited/keenovo-silicone-heatmat-240-x-240-mm-230-v-ac-300-w/)

## Software
- [Klipper](https://github.com/Klipper3d/klipper)
  - [KIAUH](https://github.com/th33xitus/kiauh)
  - [Fluidd](https://github.com/fluidd-core/fluidd)

## Mods
- [Klicky probe](https://github.com/jlas1/Klicky-Probe)
- [Trident Inverted Electronics](https://github.com/VoronDesign/VoronUsers/tree/main/printer_mods/LoganFraser/TridentInvertedElectronics)
- [Wobble X](https://github.com/MirageC79/Interfaces-for-WobbleX-integration/tree/main/Voron/Trident)

## Planned changes
- [Trident Spool Holders](https://github.com/VoronDesign/VoronUsers/tree/master/printer_mods/elcrni/V2.4-Trident-Spool-Holders)
- LEDs

# How do i use a git repo as config dir?

Generate and add an ssh key to github to upload config changes direct to github.


Clone a repo
```bash
cd printer_data
rm -rf config/
git clone git@github.com:USER/Voron-0.1-config.git config
```


Klipper will now read config from your repository via the symbolic link.

If you want, you can also create a link to your newly generated klipper.bin to always have it available in your config directory.
```
ln -s ~/klipper/out/klipper.bin ~/printer_data/config/klipper.bin
```
