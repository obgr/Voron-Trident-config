# Work in progress!
# Voron Trident To be serialized

## Repo layout
printer.cfg includes subconfig and submacros from config.d and macros.d respectively.

## Hardware
- Voron Trident
  - BTT Octopus Pro
  - Raspberry Pi 4
  - Steppers from LDO
    - A/B: 2x 42STH40-2004MAC
    - Z: 3x 42STH40-1684L300E
    - Extruder: [Bondtech LGX® Large Gears eXtruder](https://www.bondtech.se/product/lgx-large-gears-extruder/)
  - [Noctua NF-A6x25 FLX](https://noctua.at/en/nf-a6x25-flx) for electronics cooling.
  - [Voron X/Y Hall Effect Endstop](https://fermio.xyz/fermio-labs-gmbh/voron-x-y-hall-effect-endstop/endstop)
  - X Gantry
    - Phaetus Dragon HF
    - [Bondtech CHT Nozzle](https://www.bondtech.se/product/bondtech-cht-coated-brass-nozzle/)
    - PT1000 Termistor from E3D
    - High Precision Heater Cartridge from E3D.
    - Afterburner
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

## Planned changes
- Null

# How do i use a git repo as config dir?
When you clone a repo, the name of the repository will most likely not be klipper_config.

There is a way to link your config repo to be read from a standard configured klipper install.

*This is done with <mark>Symbolic links</mark>*.

## Preparation

Generate and add an ssh key to github to upload config changes direct to github.

## Symbolic link magic

Clone a repo
```
cd
git clone git@github.com:USER/Voron-0.1-config.git
```
Remove klipper_config folder.
```
rm -rf klipper_config/
```
Create a symbolic link named klipper_config that points to your repository
```
ln -s Voron-0.1-config/ klipper_config
```

Klipper will now read config from your repository via the symbolic link.

If you want, you can also create a link to your newly generated klipper.bin to always have it available in your config directory.
```
ln -s ~/klipper/out/klipper.bin ~/klipper_config/klipper.bin
```
