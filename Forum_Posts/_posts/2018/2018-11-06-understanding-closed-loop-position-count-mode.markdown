+---
layout: "Forum Post"
title: "Reading Raw sensor Values from Magsensor Hall Sensors"
date: "2018-11-06 11:20"
---
Hey Luuk,

It ends up that it is very easy to get a raw sensor reading from our hall sensors in the [MGS1600GY] firmware. You can do this by using the `MRS` Controller command, which returns the hall sensor that you give it as an argument, which are sensors `1`-`10`

You can implement this in a [MicroBasic] Script on the sensor using this snippet:

```
dim raw_sensor_arr[9] as integer

For i = 0 AndWhile i < 10
    raw_sensor_arr[i] = getvalue(_MSR, i)
Next
```

Please keep in mind that the raw sensor values will be in Millivolts, and not processed so you will be responsible for processing them yourself. Perhaps this will be the subject of an application note, but it is certainly not something that I have done before.

<!-- Start of Footer -->
<!-- Reference Links -->

[User Manual]:https://www.roboteq.com/index.php/docman/motor-controllers-documents-and-files/documentation/user-manual/272-roboteq-controllers-user-manual-v17/file

[MicroBasic]:https://www.roboteq.com/index.php/technology-menu/microbasic-technology


<!-- For emails, product pages should be the default link for product names -->
<!-- Single Channel Induction -->

[FIM2360S]:https://www.roboteq.com/index.php/component/virtuemart/388/8/motor-controllers/fim2360s-detail?Itemid=0

<!-- Single Channel Brushless -->

[FBL2360S]:https://www.roboteq.com/index.php/component/virtuemart/348/fbl2360s-detail?Itemid=971
[SBL2360S]:https://www.roboteq.com/index.php/roboteq-products-and-services/brushless-dc-motor-controllers/395/sbl2360s-detail

<!-- Brushless -->

[SBL2360]:https://www.roboteq.com/index.php/roboteq-productsS-and-services/brushless-dc-motor-controllers/393/sbl2360-277-detail

<!-- MagSensors -->

[MGS1600GY]:https://www.roboteq.com/index.php/roboteq-products-and-services/magnetic-guide-sensors/320/mgs1600cgy-magnetic-sensor-with-gyroscope-detail

<!-- End of Footer -->
