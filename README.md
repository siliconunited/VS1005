# VS1005
> VS1005 product family is the new flagship and VLSI Solution's first MP3 system-on-a-chip.
> The features of VS1005 are particularly suited for portable audio devices, docking stations, and portable recorder applications.
> The Hi-speed USB (480 Mbit/s) host function is useful in systems that require audio playback capability from external media such as USB memory sticks or drives, opening up many new applications in AV receivers and radio players. USB slave mode is also supported.
> The Ethernet interface provides Internet streaming capability over wired lines. I2S extends digital connectivity with other ICs. The RTC and battery backed registers provide alarm functions as well as very low power - low speed modes for the DSP.
> The VS1005 SoC takes a new approach in application development when compared to VLSI's earlier products. The multitasking operating system VSOS and the object code library MegaLib offer services that can be utilized with VLSI Solution's Integrated Development Environment VSIDE. This combination makes writing applications to VS1005's 256 KiB RAM memory a straightforward and intuitive process. To further extend VS1005's usability, code can be loaded dynamically from any non-volatile memory, including VS1005's optional internal 1024 KiB flash memory. The internal flash memory can be protected, making it possible for developers and third parties to protect their code.
> The MegaLib library includes all VLSI Solution's existing codecs: MP3 and Ogg Vorbis encoders, MP2, MP3, WMA, OGG, AAC LC, FLAC, IMA and WAV PCM decoders, and other functions: FM including RDS, file I/O, device drivers, application loading, multitasking, graphical interface functions, audio processing, etc.

# Firmware Status
> VS1005g has hardware support for a great number of different devices and interfaces. However, supporting all these devices and interfaces in a consistent way so that users can combine functionality of them at will does require some time.
This page shows the current VS1005g firmware's and applications' development status for VSOS3, as well as a simple roadmap for future development.

## Existing
Support for these devices and signal processing algorithms already exist and has been released.
### Codecs
- Encoders: Ogg Vorbis, MP3
- Decoders: MP3, WAV PCM, Ogg Vorbis, WMA, FLAC, AAC-LC
### Drivers
#### Audio
- Analog audio in/out
- I2S digital audio I/O, master and slave
- S/PDIF digital audio output
- Secondary audio path (using DAOSET registers)
- Equalizer
- DC removal
- Slave input (e.g. I2S) synchronization
#### Nand flash (Single-Level)
- Native hardware SD Card
- Full-Speed USB mass-storage device
- Full-Speed USB host (experimental)
- LCD
#### Other
- Dynamically linked libraries (allows loading and unloading of codecs, drivers, libraries)
- FAT12 / FAT16 / FAT32 support
- Optional UART VSOS Shell environment
- FM tuner example
- RDS decoding for FM tuner
- Selectable horizontal / vertical LCD operation
- Resistive LCD touch interface
- Multithread resource support
- Boot from internal flash, external SPI flash
- Volume control
- RTC operations

## In Queue
These pieces of firmware are already well under development.
### Codecs
- Decoders: ALAC (5/2016), DSD64 (5/2016)
- Encoders: WAV PCM
### Drivers
- Nand flash (Multi-Level)
- 10BaseT Ethernet (driver exists, still needs debugging)
### Other
- Boot from Nand flash

## To Do
These pieces of firmware still need lots of work: they are very complex, or have not yet been written or ported to VS1005.
### Drivers
- Hi-Speed USB device / host
- SAR A/D converters
- S/PDIF digital audio receiver
### Other
- Software protection
- JTAG debug support


# Features
## Power
- Single power input
- Internal voltage regulators
- 5-input multiplexed SAR for monitoring
- Optional battery for RTC and backup registers

## Analog Audio
- 2 x 24-bit / 96kHz DAC
- 3 x 24-bit / 192kHz ADC
- Integrated FM tuner with RDS, Japanese band included (76-108 MHz)
- Stereo headphone output
- Stereo microphone amplifier

## Digital Audio
- S/PDIF input and output (+AES/EBU support)
- I2S input and output
- 24-bit sample rate converter
- High-speed USB slave or host
- Ethernet interface

## Memory
- SD card interface
- Optional embedded flash
- NAND flash interface
- Internal SRAM (256 KiB) and ROM (256 KiB)

## General Purpose I/O
- Hi-Speed USB (480 Mbit/s) host / device
- PWM output
- UART
- 2 SPI buses, host and slave mode supported
- Resistive Touch Screen interface
- JTAG interface for hardware debug
- 8-bit bus for LCD

## Other Hardware Features
- Operates with a single clock
- Optional real-time clock
- Embedded flash memory can be copy protected
- Power button pin, software-controlled power-off

## VSOS Firmware Highlights
- Programs are written using VLSI Solution's Integrated Development Environment VSIDE
- Decoders: MP3, WMA, Ogg Vorbis, AAC LC, FLAC, ALAC, DSD, RIFF WAV
- Encoders: MP3, Ogg Vorbis
- DSP audio features: EarSpeaker, Parametric EQ, VU Meter, Mixer, Speed Shifter, Pitch Shifter, etc
- File I/O for SD cards and NAND flash.
- FM tuner and RDS decoder
- USB host and slave libraries
- VSOS Shell Environment for easy prototyping and software development
- Graphical display with resistive touch speed control

# Product Variations
| Device ID | MP3 Encoder | MP3 Decoder | Embedded 8Mbit Flash |
| --------- | ----------- | ----------- | -------------------- |
| VS1005G-Q | 						| 			X 		| 										 |
| VS1005G-F-Q | 					| 			X 		| 						X 			 |
| VS1205G-Q | 			X 		| 			X 		| 										 |
| VS1205G-F-Q | 		X 		| 			X 		| 						X 			 |
| VS8005G-Q | 						| 						|											 |
| VS8005G-F-Q | 					|							|							X				 |
