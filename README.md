Instituto Superior Técnico, Universidade de Lisboa

**Ambient Intelligence**

# Project Topics

There are four topic areas: smart buildings, industry & supply chain, smart cities, and assisted living.

The concept of the project should start with a specific need, and the value proposition.

For the implementation, there are open devices and development kits -- like the ESP32, Arduino and Raspberry Pi -- that can be used to prototype new ideas in these domains.

## 1. Smart Buildings

### Smart home

In the Smart Home there are already emblematic products, like the Nest thermostat or Amazon Alexa, that provide a glimpse of what can be achieved when things are connected between them and to cloud services.

A Smart Home hub is a central component in a Smart Home system.
It provides internal connectivity to the sensors, using specific network protocols; and external connectivity to the worldwide Internet, using the Internet Protocol (IP).
The gateway can also play an active role: it can filter data to reduce data volumes and to safeguard the _privacy_ of the people that live in the home; it can also provide a management and monitoring console.

In this scenario, you should provide home management and security features to allow distinct local and remote capabilities for controlling a (simulated) Smart Home.

**References:**

- <https://www.openhab.org/>
- <https://www.home-assistant.io/>

### Mobile Home Control

A board like the ESP32 has sensors and actuators that can work to support many services in a smart home.
More interesting, these services can be controlled by the home owner - and family members, and some special guests -  from a mobile phone interface.
The ESP32 boards also have Wi-Fi and Bluetooth radios and, using them, can communicate with smartphones.

Different users can have different profiles and preferences/requirements, so it is necessary to perform actions accordingly with whom is in a specific room;  and also, deal with conflicts when different people are in the same room.

**References:**

- <https://thingsboard.io/>
- <https://developer.android.com/studio>
- <https://flutter.dev/>

### DomoBus

The DomoBus system can represent a smart home installation, and can be configured from a specification in XML format.
The system can have a web or mobile user-interface to monitor and interact with any DomoBus system.
With this control infrastructure in place, it is possible to specify automation rules for a home that define how the home behaves.

A gateway DomoBus to X10 or MQTT-based IoT solution can also be integrated.

- <http://domobus.net/>

### Smart Classroom

A smart classroom can adapt its lights and temperature accordingly to the number and location of students; can support different types of classes such as interactive sessions and others like video-projection.

A system like this can be supported by a multi-sensor and actuator board (detects presence, temperature, light intensity, ..., and controls on/off outputs, LED lighting, projector devices, etc.

----

## 2. Industry & Supply Chain

### Smart Warehouse

Consider a robotic warehouse with robots moving around, carrying objects.
Some parts of the warehouse may have access doors or deposit boxes, that have to opened when a robot is approaching or has arrived.

The present work can implement a robot control system and detection sensors, that can then open doors or boxes.
One of the challenges is to make sure the latency of detection and actuation is such that robots do not need to stop (and also, do not hit an obstacle).

Different architectures can be considered, with local components, components near-by (fog computing), or control software away (cloud computing).

### Track and Trace middleware

The EPCglobal framework specifies data formats for RFID tag data and also data processing systems, such as ALE (Application-level events), dealing with repetitions and occasional failures in RFID reads, and EPCIS (Information Services) that stores business events triggered by physical events detected by RFID.

In this work, you can deploy these software components and configure them to support scenarios such as unloading of shipping containers, goods transport and control.

**References:**

- <http://gs1oliot.github.io/oliot/>

----

## 3. Smart Cities

### Smart Museum

Proximity-based applications engage users while they are in the proximity of points of interest and these apps are becoming popular among the users of mobile devices. 
The apps are triggered when the user is at specific geographic coordinates or when tagged objects are detected to be nearby, using several technologies, like Bluetooth Low Energy (BLE) beacons.

A smart place app allow anyone with a mobile device capable of detecting tags to access proximity-based services.
These services have to be viable in terms of energy consumption with results that show acceptable battery consumption.

**References:**

- <https://s2labs.org/?site=projects/__DS2OS>


### Smart cars

Current automobiles comprise different types of systems, ranging from infotainment and climatization systems to the braking and throttle control systems.
Moreover, they support remote access to perform operations such as monitoring the levels of gas and tire pressure.
However, it is critical that systems such as the braking and throttle control systems cannot be accessed remotely.

You can simulate an individual car or a road environment with multiple cars.

**Suggested references:**

- [Survey of the Connected Vehicles](https://ieeexplore.ieee.org/abstract/document/8058008)
- SUMO -- Simulation of Urban MObility
- CARLA -- Open-source simulator for autonomous driving research.
- Veins -- The open source vehicular network simulation framework.
- OMNeT++ -- Discrete Event Simulator

----

### Energy management

Reduce electricity bill, shift loads to hours when electricity is cheaper, control loads to reduce peak consumption.
Measure and balance energy production (from a solar panel) with energy consumption; manage loads using a new model: loads request to turn on and wait for an autorization.

### Intelligent public lighting for smart cities

The goal of this project is the implementation of a modular and scalable system to control public lights, saving energy but preserving adequate levels of comfort and security. 
The overall system has some degree of fault tolerance and fail safe behavior.

Public lights can  be replaced by LEDs, otherwise the system to be implemented
exhibits realistic behavior. 
All public lights have their own controllers which are interconnected via an I2C bus.

Each set of two lights has its own controller which senses the following events or environmental parameters:
- Detects movements in its area
-  Measures ambient light

According to the measured conditions the controller adjusts he brightness of the lamp to generate an appropriate level of luminosity.
The cell formed by a controller and a lamp is identified by its coordinates in a (x, y) plane.

Based on this configuration it is possible to implement intelligent management policies to save energy but preserve an appropriate level of comfort and security:

- maintain appropriate levels of light during day (may be with cloudy weather) and night;
- turn lights fully ON if something (a person, a car) is moving in the cell;
- turn lights ON to a median level around the cell in which movement was detected;
- turn lights ahead following the movement of something (possibly not with full intensity).

The functionalities of each controller must be implemented according to a specified interface protocol so that different implementations of a cell are able to interoperate harmoniously.

<!--
(The lamp cells implemented by a group of students must be interoperable with lamp cells implemented by any other group.)
-->

## 4. Assisted Living

### Aging at home

Supporting living and aging in the home, particularly for the elder or people with disabilities or specific diseases.
Control medication taking;
Notify of dangerous events (oven is on for too long, streetdoor was left open);
Control people activity (Normal? Not moving for too long? Pressed emergency button? Not reacting to an event?)

### Smart lost-and-found

Consider the problem of tagged objects localization in outdoor and indoor spaces.
Develop a solution that enables the user to look for its lost objects.
Since the objects can convey private information about its owner, the information should be stored and communicated with security and privacy, so that only the legitimate owner can query the system and s/he can avoid being tracked.

**Suggested references:**

- [Apple AirTags](https://www.macrumors.com/guide/airtags/)
- [Tile tags](https://www.thetileapp.com/en-us/how-it-works)

### Secure child locator
Consider the problem of child localization in outdoor and indoor spaces. 
Develop a solution for smartphone or smartwatch users that enables the tracking of children only by their authorized legal guardians and not by anyone else. 
The solution could operate outdoors, using GPS (e.g. A-GPS), but could also operate indoors, where GPS does not work. 
Indoor location can rely on Wi-Fi fingerprinting (e.g. Google Indoors Maps), Bluetooth beacons, Li-Fi, or other techniques.

The solution should consider the secure tracking of the children inside defined fences and there should be an alert (SOS) functionality. 
Both the children and the responsible adult should be regarded as users of the system, and all stored and communicated data should consider user consent and their privacy. 
If a remote server is used, it should not be fully trusted. For example, the solution may assume the server to be honest-but-curious, i.e., it follows application protocols but tries to collect as much data as possible about the users.

**References**:

- Google Maps Indoors

----

### Scale for the blind

This project proposes a weight scale for the blind. 
Due to the increasing developments in the field of Ambient Intelligent as well as the increasing possibilities of solutions to support impaired persons, there is a growing interest in these. 
In particular, a higher level of independence and increased quality of life can be generated by various products. 
Develop a solution that makes it easier for blind people to pour and combine different drinks into a vessel according to their own preferences. 
With the help of voice recognition and voice commands, an interaction with the scale can be established so that the blind person can tell
the scale exactly how much of which liquid he or she wants to have in his or her
glass.

----

[AmI Faculty](mailto:meic-ami@disciplinas.tecnico.ulisboa.pt)
