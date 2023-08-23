---
title: "![image](/images/satellite64.png) Agile Satellite Project"
excerpt: "Study project of an agile satellite communication."
collection: portfolio
---

The project is based on a request made by Airbus to the students of ENSEEIHT. The main objective is to improve an existent project of an agile satellite. Besides, it is required to analyze the functional and non-functional aspects of the project. The object of study is an earth satellite intended for non-military use, like the environmental monitoring. It is in an inclined orbit, considered as polar, and it can make a revolution in 90 minutes.

First of all, the client indicates the desired coordinates for the mission stations. After, a planning is made to get the photos from the desired place. A control station observes the satellite and controls its states. The mission plan is sent to the satellite, as well as the remote control to fix its position. When the satellite gets the photos, they are sent to the mission stations.

A prototype was constructed using two Raspberry Pi: one for the primary functions (leader) and the other one as a backup (follower). An Arduino is used to monitor the two other calculators and it decides which one will be the leader. Two servomotors with cameras are attached to each Raspberry Pi, so the agile behavior can be mocked.

The software present in the prototype is partitioned in three: communication (responsible for the communication between the satellite and the ground), plan manager (reads the plan received by the communication), and controller (it receives instructions from the plan manager and executes it). The software interface is a simulation of ARINC-653, which schedules Unix processes (partitions) to emulate the real scheduler. 

I worked on the external and internal communication of the satellite, that is, the communication between the satellite and the ground and the ones between the three parts of the prototype. A cryptography protocol is used to transmit data between the satellite and the ground. Queuing ports channels from ARINC simulator were created to share messages between the control, the plan manager, and the communication ground manager. The group identified functional errors in the internal and external communication. An imminent crash of the communication ground manager was detected when communicating simultaneously with more than one part. To correct that, the group suggested a multi-treads architecture. Moreover, the lack of fault detection and tolerance mechanisms made the project more susceptible to errors. 
