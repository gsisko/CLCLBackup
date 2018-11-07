---
layout: "FAQ"
title: "Missing Configuration File"
date: "2018-11-07 11:25"
---

#Q: Control Unit or Power Unit Configuration Menu is Missing

If Roborun+, RoboMag, or any other RoboteQ control application for the PC can't find a configuration or power menu, it should show an error window. Here is an example from Roborun+:

![](assets/markdown-img-paste-2018110711310615.png "Control unit or Power Unit configuration files are missing")

Our PC control utilities throw these errors because they cannot match a configuration menu tree to the device they are connecting to. When our utilites connect to a RoboteQ device, they query the model number and family using the `?TRN` runtime query. For instance, here is the startup log from an [MDC2460]:

```
# C
?trn
TRN=MDC2XXX:MDC2460
?FID
FID=Roboteq v2.0 MDC2XXX 10/03/2018
# C
#
```

In this instance Roborun+ will use the response from `?TRN` to locate a configuration menu tree file. For the above example, Roborun+ will try to locate `MDC2460.xml` for the Control Unit configuration file and  `RCB2XXX.xml` for the  The RoboteQ control utility will look in the `Trees` folder of its install directory. For Roborun+, this should be `C:\Program Files (x86)\Roboteq\Roborun Plus\Trees` by default.

If you are receiving this error, the RoboteQ cannot find the files in the trees folder. You should check to see if they are there manually, and make sure their names match the output of `?TRN`. If they are missing, please ensure that you have the [latest version][Files Download] of the application you are using. If you have the latest version and are still missing the correct tree files, or cannot upgrade to the latest version of the Utility, please send an email to [techsupport@roboteq.com](mailto:techsupport@roboteq.com).

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

<!-- For emails, prodcuct pages should be the default link for product names -->
<!-- Single Channel Induction -->

[FIM2360S]:https://www.roboteq.com/index.php/component/virtuemart/388/8/motor-controllers/fim2360s-detail?Itemid=0

<!-- Single Channel Brushless -->

[FBL2360S]:https://www.roboteq.com/index.php/component/virtuemart/348/fbl2360s-detail?Itemid=971
[SBL2360S]:https://www.roboteq.com/index.php/roboteq-products-and-services/brushless-dc-motor-controllers/395/sbl2360s-detail

<!-- Brushless -->

[SBL2360]:https://www.roboteq.com/index.php/roboteq-products-and-services/brushless-dc-motor-controllers/393/sbl2360-277-detail

<!-- Single Channel Brushed -->

[XDC2460S]: https://www.roboteq.com/index.php/component/virtuemart/335/xdc2230-319-326-detail?Itemid=970

<!-- Brushed -->

[MDC2460]: https://www.roboteq.com/index.php/component/virtuemart/313/mdc2460-274-detail?Itemid=970
[XDC2460]: https://www.roboteq.com/index.php/component/virtuemart/326/xdc2230-319-detail

<!-- MagSensors -->

[MGS1600GY]:https://www.roboteq.com/index.php/roboteq-products-and-services/magnetic-guide-sensors/320/mgs1600cgy-magnetic-sensor-with-gyroscope-detail


<!-- END Email Footer -->
