---
layout: post
title: The Hardest Problem in Self Driving
excerpt: "Presentation at GPU Tech Conference by Tim Daly, Chief Architect at Plus.ai"
categories: industry
tags: industry
comments: no
---

**Observation #1**

Human crash for human reasons
- Inattention/not looking: 41%
- Too fast for conditions: 8.4%
- Too fast for curve: 4.9%
- Illegal maneuver: 3.8%
- Actually asleep: 3.2%
- Following too closely: 1.5%
- Aggressive driving: 1.5%

Autonomous vehicle accidents will be different
- Software Bug
- Design/Specification Bug
- Sensor Failure
- Actuator Failure
- Computer or Network Failure

**Observation #2**

Coherence can amplify problems! The entire autonomous vehicle fleet runs the same hardware and software.

**Observation #3**

Testing by accumulation of miles is not enough and sufficient
- Need 1 billion miles to prove safety
- Cannot use human accidents as patterns for testing
- Cannot fully trust simulation
- Repeated testings is needed for each new version

**Solution**

Need to formally verify the design and use testing to confirm that the system matches its specification.
- Ultra reliable components
- Tolerate sensor and actuator failures
- Tolerate software bugs
- Designed to fail safe

Hardware detailed strategies:
- Fast enough ASIL D computer
- Redundant steering, brake and power
- Sensor washing
- Sensor fusion of diverse sensors can be robust to an individual sensor fault
- Sensor redundancy: it's better to have identical extras to detect "soft" failures because they can act as beackups, as well as define a prior distribution for each other.
    - Out of focus
    - Loss of one color
    - Delayed output
- Analytical redundancy: it's better to generate compatible residuals from multiple sensors to detect a fault
    - Visual odometry
    - LiDAR odometry
    - Wheel odometry
- Fault Detection and Isolation (FDI) to catch a fault at the lowest level possible, and hide it from the rest of the system.


Software detailed strategies:
- To make the system redundant to software bugs, a different version of the software that will have independent failures. Can we just try to build multiple versions of the same program?
- Forward recovery
    - Secondary controller based on control laws – simple, reliable, well-understood.
    - The high-performance controller is constrained to within the stability envelope of the simpler controller.

**Safe Landing System**

The Safe Landing System is simple and reliable, which has reduced control authority
- Stop in place
- Pull over and stop

It ensures safety but not liveness. In the event of a system failure or software bug in the main software, main objectives may not be completed but crashing is prevented.

The Safe Landing System uses different components from the main Driving Agent:
- Instruction Set Architecture and CPU Vendor
- Software Development Toolchain
- Operating System (no Linux kernel, no leap-second bug!)
- Development Team



[The Hardest Problem in Self Driving by Tim Daly](http://on-demand.gputechconf.com/gtc-cn/2018/pdf/CH8702.pdf)