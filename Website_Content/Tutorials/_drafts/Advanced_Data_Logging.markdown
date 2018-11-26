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

This article also assumes that you are familiar with general RoboteQ terminology, including our operating modes (*Open Loop*, *Closed Loop*, etc.) and some of the internal interfaces for commanding values from our motor controller (*Motor Commands*, *Feedback Signal*, etc.). If you are not familiar with any of these terms in the context of RoboteQ products, please consult our [User Manual].

Open Loop Motors - a Quick Rundown
----------------------

One of the first tasks that occur when connecting a controller to a motor is to ensure that the controller configuration is correct, and that all hardware connections to the motor are working. The first step is always to run the motor in Open Loop mode. From Page 86 our [User Manual]:

> In [Open Loop] mode, the controller delivers an amount of power proportional to the command
> information. The actual motor speed is not measured.

The best way to think of Open Loop control is as a direct voltage control. The *Motor Command* issued to an *Open Loop* Motor channel, the supply voltage is proportionally applied to the motor output. The formula for this application is given as:

$$ D_{PWM}= .1\% * M_c $$

Where $D_{PWM}$ is the output *PWM* signal duty cycle, or the *Motor Power*, and $M_C$ is the *Motor Command*. For practical purposes, you can think of the output duty cycle as the voltage output of the controller.

>Note: Keep in mind that for Brushless and AC induction controllers, the output voltage is not a DC current. For Brushless controllers, it is commuted based on the controller's *Switching Mode*. In an AC Induction controller, it is output as a 3 phase AC signal. However, in both of these controllers, the output is still in the form of a *PWM* signal, so the analogy still holds.

Therefore, when we drive a motor in Open Loop mode we want to make sure the following occurs:

- When we send the channel a *Motor Command*, the motor power quickly responds.
- That the *Motor Power* of the controller changes at a fixed ramping speed until it reaches the *Motor Command* value, and then it stays there.
- That, as the rotor of the motor applies torque, we see current drawn, or *Motor Amps*

Creating a Log
-----------------

Using the *Run Tab* in Roborun+ we can [log data values][Data Logging Tutorial] from the controller to ensure that the previous three conditions are occurring. This is the output of a Brushed Motor running in Open Loop Mode on an [SDC2160]:

![](assets/markdown-img-paste-20181121152240183.png)

Running this MicroBasic Snippet:

```
top:
	setcommand(_G, 1, 1000)
	wait(3000)
	setcommand(_G, 1, 0)
	wait(3000)
	setcommand(_G, 1, -1000)
	wait(3000)
	setcommand(_G, 1, 0)
	wait(3000)
goto top
```

Here it looks like our controller is achieving the first two parameters that we are looking for: it is accepting new *Motor Commands* and it is adjusting *Motor Power* correctly in *Open Loop* mode. However, by looking at the Run Tab graph, it would appear that the motor isn't drawing current. Perhaps we should take a closer look at the Data...

Saving and Examining a Log
--------
By hitting the save button (![](assets/markdown-img-paste-20181121155025950.png)) we can save a log of the actual samples that the run tab is using as a Tab column delimited, newline row delimited text file. For instance, here is an excerpt of a log saved of the above Dataset:
```
Time Stamp	          Motor Power 1	Motor Command 1	Battery Amps 1
11/21/2018 3:21:28 PM	0	0	0
11/21/2018 3:21:28 PM	0	0	0
[...]
[...]
11/21/2018 3:21:29 PM	0	0	0
11/21/2018 3:21:29 PM	0	0	0
11/21/2018 3:21:29 PM	0	0	0
11/21/2018 3:21:30 PM	176	1000	0
11/21/2018 3:21:30 PM	376	1000	0.1
11/21/2018 3:21:30 PM	576	1000	0.2
11/21/2018 3:21:30 PM	776	1000	0.2
11/21/2018 3:21:30 PM	976	1000	0.2
11/21/2018 3:21:30 PM	1000	1000	0.1
11/21/2018 3:21:30 PM	1000	1000	0.1
11/21/2018 3:21:30 PM	1000	1000	0.1
11/21/2018 3:21:30 PM	1000	1000	0.1
11/21/2018 3:21:30 PM	1000	1000	0.1
11/21/2018 3:21:31 PM	1000	1000	0.1
11/21/2018 3:21:31 PM	1000	1000	0.1
11/21/2018 3:21:31 PM	1000	1000	0.1
11/21/2018 3:21:31 PM	1000	1000	0.1
11/21/2018 3:21:31 PM	1000	1000	0.1
11/21/2018 3:21:31 PM	1000	1000	0.1
11/21/2018 3:21:31 PM	1000	1000	0.1
11/21/2018 3:21:31 PM	1000	1000	0.1
11/21/2018 3:21:31 PM	1000	1000	0.1
11/21/2018 3:21:31 PM	1000	1000	0.1
```

Here we can see the raw values that the run tab has logged from the controller. Now it is clear - the motor was drawing current! Just not very much, since it was an unloaded motor.

When you save a log of the controller values, each sample is given it's own time stamp, in the format of `MM/DD/YYYY (H)H:MM:SS`. Notice how their are currently 10 samples per second in the log. What if we want a higher resolution sample? What is preventing this? If we look at the *Controller Log* form the console tab, we get our answer:

![](assets/markdown-img-paste-2018112116011573.png)

The controller isn't just debugging the values we want to log, it is also sending tons of other values, such as *Analog Input* values (`AI`) or the *Pulse Input* values (`PI`). These values debugs are actually what is going on under the hood to power the rest of the run tab status lights. We can disable it Using the checkmark boxes in each section:
![](assets/markdown-img-paste-20181121160838664.png)

And when we check the log generated with the sections disabled:
```
Time Stamp	Motor Power 1	Motor Command 1	Battery Amps 1
11/21/2018 4:03:51 PM	0	0	0
11/21/2018 4:03:51 PM	0	0	0
11/21/2018 4:03:51 PM	0	0	0
11/21/2018 4:03:51 PM	0	0	0
11/21/2018 4:03:51 PM	0	0	0
11/21/2018 4:03:51 PM	0	0	0
11/21/2018 4:03:51 PM	0	0	0
11/21/2018 4:03:51 PM	0	0	0
11/21/2018 4:03:51 PM	0	0	0
11/21/2018 4:03:51 PM	0	0	0
11/21/2018 4:03:51 PM	0	0	0
11/21/2018 4:03:51 PM	0	0	0
11/21/2018 4:03:51 PM	0	0	0
11/21/2018 4:03:51 PM	0	0	0
11/21/2018 4:03:51 PM	0	0	0
11/21/2018 4:03:51 PM	0	0	0
11/21/2018 4:03:51 PM	0	0	0
11/21/2018 4:03:51 PM	0	0	0
11/21/2018 4:03:51 PM	0	0	0
11/21/2018 4:03:51 PM	0	0	0
11/21/2018 4:03:51 PM	0	0	0
11/21/2018 4:03:51 PM	0	0	0
11/21/2018 4:03:51 PM	0	0	0
11/21/2018 4:03:51 PM	0	0	0
11/21/2018 4:03:51 PM	0	0	0
11/21/2018 4:03:51 PM	0	0	0
11/21/2018 4:03:51 PM	0	0	0
11/21/2018 4:03:51 PM	0	0	0
```

We get almost 30 samples per second. We can get even more if we increase the Baud settings of the controller, however the minimum time between samples will be 10ms (100Hz sample rate).

Graphing a Log Using Excel
-----------------------

We have designed our data logs to be very accessible to tabular data programs. Using an external program it becomes very easy to exam our data using a program like Excel. For instance, let's paste the contents of the first Open Loop log we generated into Excel:

1. First copy the contents of your motor log.
2. Then Highlight cell `A1` in a blank Excel table:
3.
 ![](assets/markdown-img-paste-20181121162234359.png)
3. And finally, paste your log (Ctrl+V):

![](assets/markdown-img-paste-20181121161913240.png)

Excel is automatically able to parse the delimited data and separate each column into rows and columns. Make sure you have `A1` highlighted when you paste, or it may not automatically parse the data correctly.

Once the data is in excel, we can take advantage of Excels rich graphing features, wich are far beyond the capabilities of the graph previewer that is included in the run tab of Roborun+. All we have to do is insert an XY scatter plot with our data selected:

![](assets/markdown-img-paste-20181121163527606.png)

And Voila!

![](assets/markdown-img-paste-20181121163722736.png)

... Or not. Excel had a little bit of trouble with the data selection. We have to help it out by deleting the range for our Horizontal Axis Labels. Just right click and choose "Select Data":

![](assets/markdown-img-paste-20181121163934942.png)

Click the Edit Button for the Horizontal Axis Labels:

![](assets/markdown-img-paste-20181121164059760.png)

And delete eveything in the Axis label range before clicking okay:

![](assets/markdown-img-paste-20181121164217131.png)

And we are left with a beautiful excel scatter plot:

![](assets/markdown-img-paste-20181121164428205.png)

Ah, that's much better.

Analyzing our Data with Python and NumPy
-----------------------
We can use other tools than Excel to manipulate our data. If we want to perform advanced analysis, importing the data to Python is not a bad idea. In Python we can use a variety of tools to manipulate and perform analysis on our motor logs.

Let's import our motor logs into a [NumPy](http://www.numpy.org/) array in Python. Here is a snippet that does that

```Python
import numpy

MotorData = np.genfromtxt('Brushed_OpenLoop.txt', skip_header = 1) #Skip data label headers
MotorData = MotorData[:, 3:] #skip time frame columns
```

Like Excel, NumPy will also automatically parse our data. In the above example, I also took the liberty of skipping the series label header (`skip_header = 1`) as well as stripping away the timestamps (`MotorData[:, 3:]`).

Once we have the data as a NumPy array, analysis becomes a breeze. For instance, sticking on the topic of plotting the data, we can use [plot.ly](https://plot.ly/#/) to generate an interactive graph:

<iframe src="assets/OpenLoopPlot.html" style="border:none;" height="800" width="100%"></iframe>

The sky is the limit when it comes to manipulating the data behind our motor logs and gaining insight about the performance of the RoboteQ motor controller. If you can't perform some cool motor analysis using our data logging, drop [techsupport@roboteq.com](mailto:techsupport@roboteq.com) an email and let us know.

<!-- TODO Make this link a link to the data logging Tutorial -->
[Data Logging Tutorial]:2018-11-08-using-run-tab-to-debug-data.markdown
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
[SDC2160]:https://www.roboteq.com/index.php/roboteq-products-and-services/brushed-dc-motor-controllers/307/sdc2160-detail
[MDC2460]: https://www.roboteq.com/index.php/component/virtuemart/313/mdc2460-274-detail?Itemid=970
[XDC2460]: https://www.roboteq.com/index.php/component/virtuemart/326/xdc2230-319-detail

<!-- MagSensors -->

[MGS1600GY]:https://www.roboteq.com/index.php/roboteq-products-and-services/magnetic-guide-sensors/320/mgs1600cgy-magnetic-sensor-with-gyroscope-detail
[OTS1600]: https://www.roboteq.com/index.php/roboteq-products-and-services/magnetic-guide-sensors/426/ots1600-sensor-detail

<!-- END Email Footer -->
