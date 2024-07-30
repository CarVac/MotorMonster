# MotorMonster

MotorMonster is intended to be a 5x TMC2160 stepper driver board for 3D printers and other applications, that is actually designed to properly drive the optimal currents for high performance NEMA 17 motors: just north of 2.8 amps RMS.

Many existing 3D printer boards use improper sense resistors.
The BTT SKR Pico, for example, has a limit of 1.4 amps RMS due to its high sense resistor values.
Conversely, the BTT Kraken overspecs its currents with extremely low sense resistors, leaving the TMC drivers starved for sense voltage resolution.

Other boards use StepStick drivers for modularity, but those have worse thermal dissipation than integrated drivers.

The goal of this project is to have a focused, single-board solution for high performance motor driving, leaving everything else to be left to a standard 3D printer motherboard.
With 5 drivers, it should be suitable for 4WD CoreXY + an extruder, or cross gantry + an extruder.

The MCU is an RP2040, which may be a tad bit slow for the very fastest applications but it's a chip I have a lot of experience with, reducing development risk.

# Acknowledgements

The RP2040 and supporting circuitry is based on https://github.com/Armastardo/OpenRectangleTemplate
