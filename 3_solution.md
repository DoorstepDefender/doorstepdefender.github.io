---
layout: page
title: Solution
permalink: /solution/
---

Our final product to combat Porch Piracy incorporates 2 parts:
* [Securing Packages](#securing-packages-trash-can)
* [Detecting Packages](#detecting-packages)

## Securing Packages: Trash Can

* Trash Cans are cheap and readily available for us to use​.
* Excellent starting-point since a trash can already has​ an openable lid​ and space to store both small and large packages.
* Ultimate camouflage against porch pirates from the streets and near to your porch​.

<img src="/res/solution/trash_can_2.png" alt="Trash Can" height=200>

### Our Modifications
* One-way opening where packages can be delivered​.
    - Dual flaps to contain package​.
* Locking rear access door for the owner to easily retrieve their packages​.

<img src="/res/solution/trash_can_1.png" alt="Trash Can" height=200>
<img src="/res/solution/trash_can_3.png" alt="Trash Can" height=200>

### Building Prototype
* Purchased a trash can, ​hinges, and a mailbox ​lock​.
* Cut a flap out of ​the back of the ​trash can​.
* Cut hole for mailbox ​lock and mount ​hard stop​.
* Install mailbox ​lock and test​.
* Cut and shape plywood ​sheet​.
* Mount the two halves of plywood to the trash can using sturdy hinges. Use a hacksaw and a Dremel to remove the sharp ends. Use hot glue to secure the screws and hinges after the Dremel sparks melted the plastic a bit. ​
* Glue trash to the ​plywood to complete ​the illusion, including ​trash handles​.

## Detecting Packages
### The Hardware
* To detect packages, we decided to utilize a [VL6180X](https://www.adafruit.com/product/3316) ToF (Time of Flight) distance sensor.
    * Factors such as price, availability, and consistency led us to this sensor.
* The sensor operates over the I²C interface.
* The sensor is connected to a Raspberry Pi 4 computer

### The Software
* Created a custom I2C hardware driver program to read values the sensor​
* Examined datasheets and consulted experts.​
* Created this program in C++ using the BSD sockets API to facilitate hardware communication.​

### The App
* Mobile app to communicate with the Raspberry Pi over Bluetooth.​
* Visualization of Package status within the app.​
* Notifications when status changes (Delivered or removed).​

<img src="/res/solution/app.png" alt="Trash Can" height=200>

* The Mobile App is programmed in Java.​
* The App runs a foreground service on the Mobile Device that continues running after the app is closed.​
    - This service maintains a Bluetooth connection with the Raspberry Pi.​
    - Allows for notifications to be delivered when App is closed.​

### Production Changes
* Use a simpler computer for production​
* Decrease price, reduce size, etc.​
* Integrate battery or other power solution​
* Make waterproof?​
* Switch from RFCOMM Bluetooth communication to Web Based TCP communication​
    - Allow for connectivity when not home.​

### Incorporation into Package-Securing Solution
* The package detection solution could be placed inside the Trash Can​
* Could also be a standalone product with the addition of a speaker to scare off thieves.​
    - Similar to ['Package Pad'](/brainstorming/#package-detecting-pad) concept.
    - The speaker can play an audio recording when a package is removed from the sensor’s view.​

    ​