# P2-BLDC-Motor-Control - README
Single and Two-motor driver objects P2 Spin2/Pasm2 for our 6.5" Hub Motors with Universal Motor Driver Board

![Project Maintenance][maintenance-shield]

[![License][license-shield]](LICENSE)

## The Project

Provide ready-to-use objects easily incorporated into your own code which control Brushless DC  (BLDC) motors via the [Parallax 64010 Universal Motor Driver P2 Add-on Boards](https://www.parallax.com/product/universal-motor-driver-p2-add-on-board/)  These boards can be used with either the:

- [Parallax 64020 P2 Edge Module Breadboard](https://www.parallax.com/product/p2-edge-module-breadboard/) - larger, extra unused pins
- or [Parallax 64019 P2 Edge Mini Breakout Board](https://www.parallax.com/product/p2-edge-mini-breakout-board/) - smaller fewer unused pins

NOTE: *If you wish to add more than a couple of sensors to your platform then you'll want to use the larger of the two as it provides more unused pins.*

Parallax offers a pair of the [6.5" Hoverboard wheels along with mounting hardware](https://www.parallax.com/product/6-5-hub-motors-with-encoders-and-mounting-blocks-bundle/) which is perfect for use with the drivers from this project.


## Table of Contents

On this Page:

- [Motor Object Introduction](https://github.com/ironsheep/P2-BLDC-Motor-Control#single-and-two-wheeled-motor-control-objects) - overview of the objects provided by this project
- [System Diagram](https://github.com/ironsheep/P2-BLDC-Motor-Control#system-diagram) - quick visual overview of the motor and steering runtime structure
- [DEMOs](https://github.com/ironsheep/P2-BLDC-Motor-Control#demos) - Example files that show how to interact with the motor control and steering objects provided by this project
- [How to Contribute](https://github.com/ironsheep/P2-BLDC-Motor-Control#how-to-contribute) - we welcome contributions back to this project for all of us to use. Learn how, here!

Additional pages:

- [Steering and Motor control](DRIVE-OBJECTS.md) - the object public interfaces
- [Drawings](DRAWINGS.md) - .dwg files you can use to order your own platform inexpensively
- [Background Sources we used to develop our public interfaces](Movement-STUDY) - Interfaces of Blockly Prop robotic control objects, LEGO Mindstorms motor control / steering as well as Digital Continuous Rotation Servo interfaces


## Single and Two-wheeled Motor Control Objects

There are two objects in our motor control system. There is a lower-level object (**isp\_bldc_motor.spin2**) that controls a single motor and there's an upper-level object (**isp\_steering_2wheel.spin2**) which coordinates a pair of motors as a drive subsystem.

If you are working with a dual motor device then you'll be coding to the interface of this upper-level steering object as you develop your drive algorithms.  If you were to work with say a three-wheeled device then you may want to create a steering object that can better coordinate all three motors at the same time. Actually this is true for any other number of motors you decide to control. Create your own better-suited steering object, base it on this project's 2-wheel version. (*And, if you do please consider contributing your work to this project so it can be available to us all! See: [How to Contribute](https://github.com/ironsheep/P2-BLDC-Motor-Control/tree/develop#how-to-contribute) below.*)

The drive subsystem currently uses two cogs, one for each motor and a third cog for active tracking of wheel position. Conceptually, the drive system is always running. It is influenced by updating control variable values. When the values change the drive subsystem responds accordingly. The public methods of both the steering object and the motor object simply write to these control variables and/or read from associated status variables returning their current value or an interpretation thereof.

The interfaces for these two objects are described in [BLDC Motor Drive Objects](DRIVE-OBJECTS.md)

---

## System Diagram

The following diagram shows the nested motor control and sense subsystem comprised of the two objects: steering and motor control.

![Motor Control System Diagram](./images/objects-cogs.png)

In this diagram there are three **rectangular objects** depicting files (yellow background) of code. There are three methods within the files (white and green backgrounds) that are run in separate cogs.  The **arrows** attempt to show which objects interact with each other and also show with which object the user application can interact.  The gear icon indicates which are runing in their own Cog. You can see that the users' top-leve control application runs in its own Cog as well.

## DEMOs

A small number of demos are provided with this project:

| Spin2 File Name(s) | Demonstration
| --- | --- | 
| [demo\_single_motor.spin2](demo_single_motor.spin2) | Provides example code for controlling a single motor and position sensing of the single motor.
| [demo\_dual_motor.spin2](demo_dual_motor.spin2) | Provides example code for controlling a pair of motors and using the 2-wheel steering object.
| [demo\_dual\_motor_rc.spin2](demo_dual_motor_rc.spin2) | Provides example code for using our FlySky Remote Controller and the SBUS receiver to control the pair of motors via the 2-wheel steering object 


## How to Contribute

This is a project supporting our P2 Development Community. Please feel free to contribute to this project. You can contribute in the following ways:

- File Feature Requests or Issues (describing things you are seeing while using our code) at the [Project Issue Tracking Page](https://github.com/ironsheep/P2-BLDC-Motor-Control/issues)
- Fork this repo and then add your code to it. Finally, create a Pull Request to contribute your code back to this repository for inclusion with the projects code. See [CONTRIBUTING](CONTRIBUTING.md)

## References

1. A study of Motor Control and Drive Techniques found in LEGO Mindstorms and in Parallax BlocklyProp is presented in: [Movement API Study](Movement-STUDY.md)

1. [To-scale drawings](DOCs/bot-layout.pdf) of possible rectangular and round robotic drive platforms for Edge Mini Break and JonnyMac P2 Development boards

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
