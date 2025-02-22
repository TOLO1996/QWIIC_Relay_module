# QWIIC_Relay_module
QWIIC Relay module, TCA9534A
## Introduction
The module described in the project allows you to control 4 relays and read 4 digital inputs (opto-isolated) using the I2C bus. The use of connectors compatible with other QWIIC boards allows for easy integration with other system boards. Equipping the boards with pass-through connectors allows for easy cascading of individual modules. 

**Due to the current consumption and the level of relay control voltages, the modules must be powered from an external source.**

**The module can be operated by Arduino or Raspberry PI, since the voltage level on the i2c bus is 3.3V, additional voltage translators may be needed when using 5V systems.**

A full description of QWIIC can be found on the manufacturer's website https://www.sparkfun.com/qwiic

## Description of operation
The device diagram is visible in the image below. The heart of the device is the TCA9534A integrated circuit, a popular 8-channel GPIO expander operating on the I2C bus. The device addresses can be set using jumpers on the underside of the printed circuit board. There can be up to 8 devices on the bus with addresses from 0x20 to 0x27. Four channels of the device (From P0 to P3) were connected to the ULN2003LVPWR integrated circuit, the task of this integrated circuit is to control relays K1 to K4, HFD23-003-1ZS relays were used here, which offer a coil operating voltage of 3.3V and small dimensions.

The entire device is powered by 3.3V supplied by the TLV76150DCYR system. Due to the current consumption of the board's relays, it cannot be powered from the QWIIC connector. However, it is possible to use this voltage (if one device of this type is used on the bus or works only with inputs), the J16 jumper at the bottom of the PCB is used for this purpose.


Digital inputs are built using PC817SC optocouplers. LEDs L1 to L4 indicate input activation. If we do not care about galvanic isolation. we can install jumpers J5, J8, J7, J6
A more detailed description of the use of inputs/outputs is provided later in the material. 

Because the connectors compatible with the J10, J9 socket (BM04B-SRSS-TB(LF)(SN)) are difficult to crimp due to the fine raster. An additional J11 connector is provided. In its place, you can install a Molex_22232061 socket or a regular goldpin list (as in the photos)
![SCH_I2C_Expander_1-Sheet_1](https://github.com/user-attachments/assets/cec7471b-dee0-4159-924e-d8eba222154f)

## Connecting the device
### I2C interface
### Configuration
### Inputs
### Outputs

## Software Example
