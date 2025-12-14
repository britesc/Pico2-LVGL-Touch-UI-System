# Project Outline – Pico2 LVGL Touch UI System

Author:     Julian
Date:       2025-12-12 12:22:00
Version:    0.0.1
GitHub:     <https://github.com/britesc/Pico2-LVGL-Touch-UI-System.git>

## 1. Project Name

EARS-2025
Code Location: D:\Dev\Pico2 LVGL Touch UI System

## 2. Purpose and Goals

The purpose of this Project is to design and produce a Device that will allow a UK Serviceman to configure it to respond to a number of Role Dependent Scenarios.
It should be registered to the User by their ZAP Number and accessed via a User Configurable Password.
The Device should be able to not only record User specific information, but be able to accept subordinate information for aggregation and to send information to a superior Chain of Command (CoC).

    2.1. It needs to be minimal in size.
    2.2 It needs to have a touch screen display for interaction.
    2.3. It needs to be rechargeable battery operated.
    2.4. It needs to be IP67 or higher.
    2.5. For an unqualified User, there should be "No User Serviceable Parts", to maintain integrity of the Device.
    2.6. The Device should be designed and produced with Security of Information as a Main Driver.

## 3. Application Requirements

    3.1  Clock.
    3.2  GPS.
    3.3  Compass.
    3.4  User Configurable.
    3.5  Role Implementable.
    3.6  Received Data.
    3.7  Transmit Data.
    3.8  Distance Travelled Data.
    3.9  Sealed IP67 Enclosure.
    3.10 Simple User Touch Display.
    3.11 Rechargeable Batteries.
    3.12 Sealed Pogo Connections.
    3.13 ABS Enclosure.
    3.14 Whole Screen Morse Flash Beacon.
    3.15 LoRa Distress Beacon.

## 4. Hardware Overview

The device should be constructed from the following components.

    4.0.1 An ABS enclosure of the following dimensions
        4.0.1.1 Height = 50mm (with addition Display Bezel).
        4.0.1.2 Width = 98mm.
        4.0.1.3 Depth = 66mm.
    4.0.2 A Dual Core Microcontroller Unit.
        4.0.2.1 Raspberry Pi Pico 2350.
        4.0.2.2 Espressif ESP32-S3.
    4.0.3 A Capacitive Touch Display Unit.
        4.0.3.1 Minimum Landscape Resolution of 320x240 Pixels.
        4.0.3.2 Maximum Landscape Resolution of 320x480 Pixels.
    4.0.4 GPS Module.
    4.0.5 LoRa Module.
    4.0.6 Pogo Pins Connector.
    4.0.7 On/Off Switch.
        4.0.7.1 Miniature Rocker On/Off Switch.
        4.0.7.2 Miniature Push Button On/Off Switch.
    4.0.8 Self constructed Through Hole Board fitted with the appropriate Headers and Wiring.
    4.0.9 Miniature Haptic Vibration Engine.

### 4.1 Microcontroller

### 4.2 Display

### 4.3 Touch Panel

### 4.4 Power Requirements

    4.4.1 The Device will be equipped with a 3.7vdc rechargeable Lithium Battery.
    4.4.2 The Device can be powered by a special USB cable that can be plugged into a charger or another product such as a Laptop or PC that is fitted with a USB charging/data port.
    4.4.3 Whilst connected to an external power source, the internal batteries will be charged; allowing the Device to operate in an autonomous environment.

## 5. Software Architecture

The Device will run on compiled .uf2 (USB Flashing Format) file format, which will be produced via the following software applications.

### 5.1 LVGL Version

The underlying version of Lightweight Versatile Graphics Library (LVGL) is currently 9.4.0 at the time of writing of this Document.

### 5.2  EEZ Studio Version

Due to the Background Colour Bug in EEZ Studio 0.24.0 a combination of EEZ Studio 0.23.2 and EEZ Studio 0.24.0.

### 5.3  Platform IO Version

Platform.io 3.3.4 is the build processor. It is installed as an extension within VSCode.

### 5.4  VSCode Version

VSCode 1.107.0 is the IDE used to develop the .uf2 used by the Device.

### 5.5 File Structure

### 5.6 Drivers

### 5.7 PlatformIO Configuration

## 6. UI Requirements

### 6.1 Navigation Flow

### 6.2 Widgets Needed

### 6.3 Accessibility Considerations

## 7. Milestones

### 7.1 Alpha Hardware Bring-Up

### 7.2 Basic LVGL Rendering

### 8. Acknowledgements

Assistance has been obtained from ChatGPT 5.1 Large Language Model (LLM).

### 9. Unsorted Work

1. Initial screen is blank with a black background.
2. It is loaded from Core0.
3. It is immediately followed by an animation.
4. It is loaded from Core0.
5. At the same time the Eeprom is read and some Global Variables are set.
6. If the Eeprom has not been configured, it is initialised.
7. It is loaded from Core1.
8. On termination of the animation, dependent upon the status of the global variables different screens are displayed to the User.
9. It is loaded from Core0.
10. If the ZapNumber and/or Password has not been assigned, a screen with this functionality is displayed.
11. If the ZapNumber is not configured, the password option is disabled.
12. There is also a re-initialise Eeprom button, long
13. There is also an Info Button, which displays the App Version Number and Device Serial Number.
14. There is also a reboot button.
15. The loop can only be terminated by powering off the device.
16. If the ZapNumber has been entered into Eeprom the ZapNumber button is disabled.
17. It is now no longer possible to change the ZapNumber other than by re-initialising the Eeprom.
18. The password may be changed at the User's discretion.
19. If the ZapNumber button is selected, a ZapNumber entry screen is displayed.
20. Either the ZapNumber is entered and subsequently written to Eeprom or if cancelled, returns to the previous screen as does the Eeprom update.
21. If the password button is selected, a password entry and confirmation screen is displayed.
22. If entered a special hash is written to the Eeprom which returns to the previous screen.
23. If cancelled the previous screen is presented.
24. This loop will continue until all required information is collected.
