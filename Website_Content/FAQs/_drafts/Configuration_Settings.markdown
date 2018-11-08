---
layout: "FAQ"
title: "Configuration Settings are Resetting on Power Up"
date: "2018-11-08 11:02"
Author: Gabriel Isko
---

##Q: My device's configuration settings are not being saved after a power cycle or Reboot

Configuration settings must be saved to flash manually when they are changed.

##Steps to Save configuration settings to Flash Memory

* If you are editing your configuration settings from the Run Tab of Roborun+, please make sure you save your settings to the controller:

* If you are configuring your settings from serial commands, or a MicroBasic script you will have to save them to flash using the `!EES` runtime command.  This can be done from the console tab of Roborun+:

* You can also invoke `!EES` from your MicroBasic script:

```c
setcommand(_EES, 1 )
```

##Further Questions

Please reference the `!EES` documentation in **SECTION 19: Command Reference** of our [User Manual]. If you still have questions please email [techsupport@roboteq.com](mailto:techsupport@roboteq.com).


<!--START FAQ Footer -->

<!-- Reference Links -->

[User Manual]:https://www.roboteq.com/index.php/docman/motor-controllers-documents-and-files/documentation/user-manual/272-roboteq-controllers-user-manual-v17/file
[MicroBasic]:https://www.roboteq.com/index.php/technology-menu/microbasic-technology
[C API]:https://www.roboteq.com/index.php/docman/motor-controllers-documents-and-files/nxtgen-downloads-1/application-programming-interface/348-roboteq-linux-winapi-manual/file
[Files Download]:https://www.roboteq.com/index.php/support/downloads



<!-- END FAQ Footer -->
