---
layout: "FAQ"
title: "Using Run Tab to Debug Data"
date: "2018-11-07 13:56"
---

#Q: How do I Debug Data from a RoboteQ device?

All of RoboteQs control utilities come with powerful tools to debug and log data from the devices operation. These tools can often be accessed from the run tab of the configuration utility. For example, here is the run tab from a Roborun+ instance connected to an MDC2460:

![](assets/markdown-img-paste-Run-Tab-20181107141633438.png "Run Tab of Roborun+")

From the run tab you can use the capture section to display multiple different kinds of [runtime values](#capture-value-reference).

###Capture Value Reference

| Capture Section Value | Description                                                    | Corresponding Runtime Query |
| --------------------- | -------------------------------------------------------------- | --------------------------- |
| Battery Volts         | Voltage Available On VMOT                                      | `?V`                        |
| Motor Command (1,2)   | -1000 to 1000 value command to motor channel output            | `?M`                        |
| Motor Power   (1,2)   | PWM duty cycle of motor channel output                         | `?P`                        |
| Motor Amps    (1,2)   | Peak Current draw on motor channel output                      | `?A`                        |
| Battery Amps          | Current draw from Powersource over VMOT                        | `?BA`                       |
| Speed (1,2) %         | Encoder measured Speed as a percentage of the Maximum Speed    | `?SR`                       |
| Speed (1,2) RPM       | Encoder measured Speed as an RPM value                         | `?S`                        |
| Counter (1,2)         | Internal Encoder Counter value                                 | `?C`                        |
| Feedback (1,2)        | Position Feedback Signal value for Closed Loop Mode            | `?F`                        |
| Loop Error (1,2)      | Control Loop Error in Closed Loop Mode                         | `?E`                        |
| Track (1,2)           | Expected value of motor position in Closed Loop Position Modes | `?TR`                       |
| 5V Output             | Current voltage on the 5V output rail                          | ``                            |
