# openlifu-electrical

## Disclaimer

CAUTION - The system described here has not been evaluated by the FDA and is not designed for the treatment or diagnosis of any disease. It is provided AS-IS, with no warranties. User assumes all liability and responsibility for identifying and mitigating risks associated with using this software.

PCB design files for the [Open-LIFU](https://github.com/OpenwaterHealth) focused ultrasound platform — an open-source system for low-intensity focused ultrasound (LIFU) neuromodulation research.

This repository contains the electrical schematics, Gerber manufacturing files, 3D models, and bills of materials for every printed circuit board in the Open-LIFU hardware stack.

## Repository Structure

```
openlifu-electrical/
├── Array Flex (710-00001)/        # Ultrasound transducer array flex PCB
│   ├── 3D/                        # STEP model for mechanical integration
│   ├── BOM/                       # Bill of materials (.xlsx)
│   ├── Gerber_NCdrills_IPC/       # Manufacturing files (Gerber, drill, IPC)
│   └── Schematic/                 # Circuit schematic (.pdf)
│
├── Console PCB (700-00002)/       # Main console power supply & USB routing board
│   ├── 3D/                        # STEP model
│   ├── BOM/                       # Bill of materials (.xlsx)
│   ├── Gerber/                    # Manufacturing files
│   └── Schematic/                 # Circuit schematic (.pdf)
│
├── Transmit Module (710-00003)/   # High-voltage RF transmit module
│   ├── 3D/                        # STEP model
│   ├── BOM/                       # Bill of materials (.xlsx)
│   ├── Gerber/                    # Manufacturing files
│   └── Schematic/                 # Circuit schematic (.pdf)
│
├── 710-00015-Rev1.zip             # Interconnect/cable assembly design files
├── 720-00001-Rev1.pdf             # System-level electrical documentation
└── LICENSE                        # CERN-OHL-S-2.0
```

## Board Descriptions

### Array Flex (710-00001)

Flexible PCB that interfaces with the 64-element ultrasound transducer array. Routes signals between the acoustic elements and the transmit module.

### Console PCB (700-00002)

The main system board is inside the Open-LIFU console enclosure. Houses the high-voltage (HV) power supply and routes USB communication from the host PC to the power supply and transducer.

### Transmit Module (710-00003)

Controls the generation of high-voltage RF signals delivered to the acoustic elements to produce focused ultrasound. Current revision: **Rev 0.4.1**.

## File Formats

| Folder | Contents | Software |
|--------|----------|----------|
| `Schematic/` | Circuit schematics | Any PDF viewer |
| `Gerber/` | PCB manufacturing files | [Altium](https://www.altium.com/), or any Gerber viewer |
| `BOM/` | Component lists | Microsoft Excel or any spreadsheet application |
| `3D/` | Board models (.step) | Any CAD viewer ([FreeCAD](https://www.freecad.org/), Fusion 360, SolidWorks) |

## Related Repositories

This repo contains the PCB designs. The rest of the Open-LIFU platform lives here:

| Repository | Description |
|------------|-------------|
| [openlifu-python](https://github.com/OpenwaterHealth/openlifu-python) | Python toolbox for treatment planning and simulation |
| [openlifu-desktop-application](https://github.com/OpenwaterHealth/openlifu-desktop-application) | GUI for sonication planning and system control |
| [openlifu-transmitter-fw](https://github.com/OpenwaterHealth/openlifu-transmitter-fw) | Firmware for the transmit module (STM32L443) |
| [openlifu-console-fw](https://github.com/OpenwaterHealth/openlifu-console-fw) | Firmware for the console power PCB |
| [openlifu-transmitter-bl](https://github.com/OpenwaterHealth/openlifu-transmitter-bl) | Transmitter bootloader |
| [openlifu-sdk](https://github.com/OpenwaterHealth/openlifu-sdk) | Hardware I/O interface library |
| [SlicerOpenLIFU](https://github.com/OpenwaterHealth/SlicerOpenLIFU) | 3D Slicer extension for OpenLIFU |
| [OpenLIFU-3DScanner](https://github.com/OpenwaterHealth/OpenLIFU-3DScanner) | 3D mesh capture application |

## Getting Started

**To view schematics:** Open the PDF files in the `Schematic/` folder of any board.

**To inspect or modify PCB layouts:** Import the Gerber files into [Altium](https://www.altium.com/) (free, open-source) or your preferred EDA tool.

**To order boards:** Send the Gerber files and drill files from the `Gerber/` folder to your PCB fabricator. Refer to the BOM for component sourcing.

**To integrate with mechanical designs:** Import the `.step` files from the `3D/` folders into your CAD environment.

## Contributing

We welcome contributions from the hardware community. Please read our [Contributing Guide](https://github.com/OpenwaterHealth/.github/blob/main/CONTRIBUTING.md) before submitting changes.

For hardware contributions specifically:

- **Schematic changes** — export updated PDFs alongside source files
- **BOM updates** — maintain the Excel format with manufacturer part numbers
- **New revisions** — follow the existing part-number and revision naming convention (e.g., `710-00003 Rev 0.4.1`)

## License

This project is licensed under the [CERN Open Hardware Licence Version 2 – Strongly Reciprocal](LICENSE) (CERN-OHL-S-2.0).

## About Openwater

[Openwater](https://openwater.health) is building open-source platforms to democratize medical imaging and neuromodulation technology — reducing medical device development costs through collaborative, open-source engineering.
