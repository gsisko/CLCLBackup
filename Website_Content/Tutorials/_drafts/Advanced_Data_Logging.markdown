---
layout: Tutorial
title: Advanced Data logging
date: '2018-11-08 14:39'
---

Advanced Topics in Data Logging and Time Series Analysis
===============


Monitoring the performance of a RoboteQ motor controller is essential to mastering the usage of our motor controllers. In this article, we will be demonstrating the advanced techniques that RoboteQ engineers use when setting up a motor controller, deploying a controller in a field application, or troubleshooting the performance of a motor control setup by datalogging and analyzing values.

Prerequisites
---------------
If you are unfamiliar with how to log data from our Motor controller's using the Run Tab of Roborun+, please consult our [Data Logging Tutorial].

This article also assumes that you are familiar with general RoboteQ terminology, including our operating modes (*Open Loop*, *Closed Loop*, etc.) and some of the internal interfaces for commanding values from our motor controller (*Motor Commands*, *Feedback Signal*, etc.). If you are not familiar with any of these terms in the context of RoboteQ products, please consult our [User Manual].

Debugging a Motor During Setup
----------------------

One of the first tasks that occur when connecting a controller to a motor is to ensure that the controller configuration is correct, and that all hardware connections to the motor are working. The first step is always to run the motor in Open Loop mode. From Page 86 our [User Manual]:

> In [Open Loop] mode, the controller delivers an amount of power proportional to the command
> information. The actual motor speed is not measured.

The best way to think of Open Loop control is as a direct voltage control. The *Motor Command* issued to an *Open Loop* Motor channel, the supply voltage is proportionally applied to the motor output. The formula for this application is given as:

$$ D_{PWM}= .1\% * M_c $$ 

Where $D_{PWM}$ is the output *PWM* signal duty cycle and $M_C$ is the motor command. For practical purposes, you can think of the output duty cycle as the voltage output of the controller.

>Note: Keep in mind that for Brushless and AC induction controllers, the output voltage is not a DC current. For Brushless controllers, it is commuted based on the controller's *Switching Mode*. In an AC Induction controller, it is output as a 3 phase AC signal. However, in both of these controllers, the output is still in the form of a *PWM* signal, so the analogy still holds.

When you have a controller hooked up in open loop mode, you should be using the run tab to debug the

<!-- TODO Fix link to Published tutorial on website, rather than Gabe's Github mirror -->
[Data Logging Tutorial]:https://github.com/gsisko/RoboteQ-Support-Documents/blob/master/Website_Content/Tutorials/_posts/2018/2018-11-08-using-run-tab-to-debug-data.markdown
<!--START Email Footer -->

<!-- Reference Links -->

[User Manual]:https://www.roboteq.com/index.php/docman/motor-controllers-documents-and-files/documentation/user-manual/272-roboteq-controllers-user-manual-v17/file
[MicroBasic]:https://www.roboteq.com/index.php/technology-menu/microbasic-technology
[C API]:https://www.roboteq.com/index.php/docman/motor-controllers-documents-and-files/nxtgen-downloads-1/application-programming-interface/348-roboteq-linux-winapi-manual/file
[Files Download]:https://www.roboteq.com/index.php/support/downloads

<!-- Application Notes -->

[AGV Application Note]:https://www.roboteq.com/index.php/applications/100-how-to/278-building-a-magnetic-track-guided-agv


<!-- FAQs -->

[RS232/TTL FAQ]:https://www.roboteq.com/index.php/support/setup-troubleshooting-faq/93-support/361-q-connecting-to-arduino

<!-- 3rd Party Links -->

[ROS Driver]:https://github.com/g/roboteq

<!-- For emails, product pages should be the default link for product names -->
<!-- Single Channel Induction -->

[FIM2360S]:https://www.roboteq.com/index.php/component/virtuemart/388/8/motor-controllers/fim2360s-detail?Itemid=0

<!-- Single Channel Brushless -->

[FBL2360S]:https://www.roboteq.com/index.php/component/virtuemart/348/fbl2360s-detail?Itemid=971
[SBL2360S]:https://www.roboteq.com/index.php/roboteq-products-and-services/brushless-dc-motor-controllers/395/sbl2360s-detail

<!-- Brushless -->

[SBL2360]:https://www.roboteq.com/index.php/roboteq-products-and-services/brushless-dc-motor-controllers/393/sbl2360-277-detail
[FBL2360]:https://www.roboteq.com/index.php/roboteq-products-and-services/brushless-dc-motor-controllers/324/fbl2360-detail

<!-- Single Channel Brushed -->

[XDC2460S]: https://www.roboteq.com/index.php/component/virtuemart/335/xdc2230-319-326-detail?Itemid=970

<!-- Brushed -->

[MDC2460]: https://www.roboteq.com/index.php/component/virtuemart/313/mdc2460-274-detail?Itemid=970
[XDC2460]: https://www.roboteq.com/index.php/component/virtuemart/326/xdc2230-319-detail

<!-- MagSensors -->

[MGS1600GY]:https://www.roboteq.com/index.php/roboteq-products-and-services/magnetic-guide-sensors/320/mgs1600cgy-magnetic-sensor-with-gyroscope-detail
[OTS1600]: https://www.roboteq.com/index.php/roboteq-products-and-services/magnetic-guide-sensors/426/ots1600-sensor-detail

<!-- END Email Footer -->
