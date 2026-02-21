# Doors Linux

Doors Linux is a custom Arch-based Linux distribution built using ArchISO.
The project focuses on controlled system identity, minimal configuration layering, and reproducible ISO builds.

Doors Linux does not fork or modify Arch Linux packages.
It defines a custom build profile on top of the official ArchISO tooling.


## Overview

Doors Linux is an exploration of Linux distribution construction using the ArchISO framework. The project demonstrates how a live ISO can be customized through:

* Profile configuration
* Package selection control
* Bootloader configuration
* Root filesystem overlays
* Identity and branding customization

The system remains aligned with upstream Arch Linux.


## Architecture

Doors Linux is built using:

* ArchISO
* pacman
* systemd-boot
* Bash scripting

The distribution is generated from a custom ArchISO profile. All modifications occur at the configuration and overlay level.

No upstream Arch packages are redistributed in modified form.


## Repository Structure

```
doors-linux/
├── profile/
│   ├── airootfs/
│   ├── efiboot/
│   ├── profiledef.sh
│   └── packages.x86_64
├── screenshots/
├── README.md
└── LICENSE
```

### profile/

Contains the ArchISO build profile used to generate the live ISO.

* `airootfs/` — Root filesystem overlay applied during ISO creation
* `efiboot/` — Bootloader configuration
* `profiledef.sh` — ISO metadata and build configuration
* `packages.x86_64` — Package selection list


## Build Requirements

* Arch Linux host system
* archiso package
* Sufficient disk space (5–10 GB recommended)
* Root privileges

Install ArchISO:

```bash
sudo pacman -S archiso
```


## Building the ISO

Clone the repository:

```bash
git clone https://github.com/yourusername/doors-linux.git
cd doors-linux/profile
```

Build the image:

```bash
sudo mkarchiso -v .
```

The ISO will be generated in the `out/` directory.


## Design Principles

* Minimal surface area
* Transparent configuration
* Reproducible builds
* Clear separation between upstream packages and local customization
* No unnecessary abstraction layers


## Roadmap

* Custom ISO profile stabilization
* Bootloader configuration refinement
* Optional lightweight desktop environment
* Installer automation
* Automated build workflow (CI)

## License

MIT License

* Add a technical deep-dive section explaining ArchISO internals
* Or prepare it for a “real distribution” announcement level README
