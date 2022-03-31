# P2-BLDC-Motor-Control - README
Single and Two-motor driver objects P2 Spin2/Pasm2 for our 6.5" Hub Motors with Universal Motor Driver Board

![Project Maintenance][maintenance-shield]

[![License][license-shield]](LICENSE)


## Single and Two-wheeled Motor Control Objects

There are two objects in our motor control system. There is a lower-level object (**isp\_bldc_motor.spin2**) that controls a single motor and there's an upper-level object (**isp\_steering_2wheel.spin2**) which coordinates a pair of motors as a drive subsystem.

If you are working with a dual motor device then you'll be coding to the interface of this upper-level object as you develop your drive algorithms.  If you were to work with say a three-wheeled device then you may want to create a steering object that can better coordinate all three motors at the same time. Actually this is true for any other number of motors you decide to control. Create you own better suited steering object, base it on this project's 2-wheel version. (*And, if you do please consider contributing your work to this project so it can be available to us all! See: [How to Contribute](https://github.com/ironsheep/P2-BLDC-Motor-Control/tree/develop#how-to-contribute) below.*)

The drive subsystem currently uses two cogs, one for each motor.  Conceptually, the drive system is always running. It is influenced by updating control variable values. When the values change the drive subsystem responds accordingly. The public methods of both the steering object and the motor object simply write to these control variables and/or read from associated status variables returning their current value or an interpretation thereof.

The interfaces for these two objects are described in [BLDC Motor Drive Objects](DRIVE-OBJECTS.md)

## How to Contribute

This is a project supporting our P2 Development Community. Please feel free to contribute to this project. You can contribute in the following ways:

- File Feature Requests or Issues (describing things you are seeing while using our code) at the [Project Issue Tracking Page](https://github.com/ironsheep/P2-BLDC-Motor-Control/issues)
- Fork this repo and then add your code to it. Finally, create a Pull Request to contribute your code back to this repository for inclusion with the projects code. See [CONTRIBUTING](CONTRIBUTING.md)

## References

1. A study of Motor Control and Drive Techniques found in LEGO Mindstorms and in Parallax BlocklyProp is presented in: [Movement API Study](Movement-STUDY.md)

1. [To-scale drawings](DOCs/bot-layout.pdf) of possible rectangular and round robotic drive platforms for Edge Mini Break and JonnyMac P2 Development boards

### Drawing Files

These are the various design files I sent off to be make by [SendCutSend.com](https://sendcutsend.com/) - their prices are quite good!:

1. [Drawing File - outboard wheels (.dwg)](DOCs/DesignFiles/EdgeMiniRoundV1.dwg) - I spec'd 0.250" MDF as the material at ~$29 USD. 
![File w/Outboard Wheels](images/EdgeMiniRoundV1-dwg.png)
1. [Drawing File - enclosed wheels (.dwg)](DOCs/DesignFiles/EdgeMiniRoundV2_encl.dwg) - I spec'd 0.250" MDF as the material at ~$29 USD. 
![File w/Enclosed Wheels](images/EdgeMiniRoundV2_encl-dwg.png)
1. [Drawing File - spacer to drop motors below castors (.dwg)](DOCs/DesignFiles/SpacerV1.dwg) - I spec'd 0.025" MDF as the material w/Ten of these for ~$14.20 USD.</br>
![Spacer](images/SpacerV1.png)

NOTE: the 4 center small holes (for M3 screws) are for mounting the twin motors boards connected to the Mini Edge Breakout Board. 

There are 2 ea. holes for each motor (for 1/4" - 20 Screws.)

There are 4 ea. holes for each castor - (for 1/4" - 20 Screws.)

There are 2 ea. holes for each spacer board (shim) (for 1/4" - 20 Screws.)

### Packaging (order arrives)

This is what I found when I opened my first order:

![Opened Package](images/EdgeMiniRoundV1.jpg)
**The Package arrived with these contents..**  This was quite well packaged. The MDF part was shrink-wrapped to the backing cardboard. The laser cuts were all clean with a little bit of scorch mark on one side of the MDF as you might expect. *And yes, the Skittles package made me smile!*


---

> If you like my work and/or this has helped you in some way then feel free to help me out for a couple of :coffee:'s or :pizza: slices!
>
> [![coffee](https://www.buymeacoffee.com/assets/img/custom_images/black_img.png)](https://www.buymeacoffee.com/ironsheep) &nbsp;&nbsp; -OR- &nbsp;&nbsp; [![Patreon](./images/patreon.png)](https://www.patreon.com/IronSheep?fan_landing=true)[Patreon.com/IronSheep](https://www.patreon.com/IronSheep?fan_landing=true)

---

## Disclaimer and Legal

> *Parallax, Propeller Spin, and the Parallax and Propeller Hat logos* are trademarks of Parallax Inc., dba Parallax Semiconductor

---

## License

Copyright © 2022 Iron Sheep Productions, LLC. All rights reserved.

Licensed under the MIT License.

Follow these links for more information:

### [Copyright](copyright) | [License](LICENSE)

[maintenance-shield]: https://img.shields.io/badge/maintainer-stephen%40ironsheep%2ebiz-blue.svg?style=for-the-badge

[marketplace-version]: https://vsmarketplacebadge.apphb.com/version-short/ironsheepproductionsllc.spin2.svg

[marketplace-installs]: https://vsmarketplacebadge.apphb.com/installs-short/ironsheepproductionsllc.spin2.svg

[marketplace-rating]: https://vsmarketplacebadge.apphb.com/rating-short/ironsheepproductionsllc.spin2.svg

[license-shield]: https://camo.githubusercontent.com/bc04f96d911ea5f6e3b00e44fc0731ea74c8e1e9/68747470733a2f2f696d672e736869656c64732e696f2f6769746875622f6c6963656e73652f69616e74726963682f746578742d646976696465722d726f772e7376673f7374796c653d666f722d7468652d6261646765
