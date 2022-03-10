Instituto Superior Técnico, Universidade de Lisboa

**Ambient Intelligence**

# Project Topics

There are four topic areas: (1) smart buildings, (2) industry & supply chain, (3) smart cities, and (4) assisted living.  
For each topic area, we present project examples.

The concept of a Ambient Intelligence project should start with a specific *user* need and a statement of the *value* proposition.

For the implementation, there are open devices and development kits -- like the ESP32, the Arduino, Arduino-based cars, the Raspberry Pi -- that can be used to prototype new ideas in these domains.
However, note that the design of embedded system interfaces – interfaces between controllers and sensors or actuators - requires some background on electric circuits.

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
- <https://github.com/inesc-id/STAKE>

### Mobile Home Control

A board like the ESP32 has sensors and actuators that can work to support many services in a smart home.
More interesting, these services can be controlled by the home owner - and family members, and some special guests - from a mobile phone interface.
The ESP32 boards also have Wi-Fi and Bluetooth radios and, using them, can communicate with smartphones.

Different users can have different profiles and preferences/requirements, so it is necessary to perform actions accordingly with whom is in a specific room; and also, deal with conflicts when different people are in the same room.

**References:**

- <https://thingsboard.io/>
- <https://developer.android.com/studio>
- <https://flutter.dev/>

### DomoBus

The DomoBus system can represent a smart home installation, and can be configured from a specification in XML format.

The DomoBus system can be made accessible by a web or mobile user-interface.
With this control infrastructure in place, it is possible to specify *automation rules* for a home that define behaviors.

<!--
A DomoBus to X10 gateway or an MQTT-based Internet of Things  can also be integrated.
-->

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

- [Oliot -- Open Language for Internet of Things](http://gs1oliot.github.io/oliot/) -- GS1/EPCglobal based ID-centric IoT Platform
- [An Overview of the EPCglobal network](https://ieeexplore.ieee.org/document/6601749)

----

## 3. Smart Cities

### Smart Museum

Proximity-based applications engage users while they are in the proximity of points of interest and these apps are becoming popular among the users of mobile devices.
The apps are triggered when the user is at specific geographic coordinates or when tagged objects are detected to be nearby, using several technologies, like Bluetooth Low Energy (BLE) beacons.

A smart museum can allow anyone with a mobile device capable of detecting tags to access proximity-based services, such as information about museum exhibits, practical information, and access to more engaging user experiences.
These services have to be viable in terms of energy consumption with results that show acceptable battery consumption.

**References:**

- [DS2OS – the Distributed Smart Space Orchestration System](https://s2labs.org/?site=projects/__DS2OS)
- [Bluetooth beacons](https://www.zebra.com/us/en/products/location-technologies/bluetooth-beacons.html)

### Smart Restaurant

A smart restaurant can detect the presence of costumers and present them with menu and other useful information.
For regular costumers, it can track the usual times of presence and the preferences.
This data can be analyzed and used to make recommendations.

**References:**

- [Estimote](https://estimote.com/)

### Smart Cars

Current automobiles comprise different types of systems, ranging from infotainment and climatization systems to the braking and throttle control systems.
Moreover, they support remote access to perform operations such as monitoring the levels of gas and tire pressure.
However, it is critical that systems such as the braking and throttle control systems cannot be accessed remotely.

You can simulate an individual car or a road environment with multiple cars.

**References:**

- [Survey of the Connected Vehicles](https://ieeexplore.ieee.org/abstract/document/8058008)
  - [SUMO](https://www.eclipse.org/sumo/) -- Simulation of Urban MObility
  - [CARLA](https://carla.org/) -- Open-source simulator for autonomous driving research.
  - [Veins](https://veins.car2x.org/features/) -- The open source vehicular network simulation framework.
  - [OMNeT++](https://omnetpp.org/) -- Discrete Event Simulator

----

### Energy management

The energy management of a system allows it to reduce the electricity bill, to shift loads to hours when electricity is cheaper, control loads to reduce peak consumption.
A system can measure and balance energy production (from a solar panel) with energy consumption; manage loads using a new model: loads request to turn on and wait for an autorization.

### Intelligent public lighting

The goal of this project is the implementation of a modular and scalable system to control public lights, saving energy but preserving adequate levels of comfort and security.
The overall system has some degree of fault tolerance and fail safe behavior.

Public lights can  be replaced by LEDs, otherwise the system to be implemented
exhibits realistic behavior.
All public lights have their own controllers which are interconnected via an I2C bus.

Each set of two lights has its own controller which senses the following events or environmental parameters:

- Detects movements in its area;
- Measures ambient light.

According to the measured conditions the controller adjusts he brightness of the lamp to generate an appropriate level of luminosity.
The cell formed by a controller and a lamp is identified by its coordinates in a (x, y) plane.

Based on this configuration it is possible to implement intelligent management policies to save energy but preserve an appropriate level of comfort and security:

- maintain appropriate levels of light during day (may be with cloudy weather) and night;
- turn lights fully ON if something (a person, a car) is moving in the cell;
- turn lights ON to a median level around the cell in which movement was detected;
- turn lights ahead following the movement of something (possibly not with full intensity).

The functionalities of each controller must be implemented according to a specified interface protocol so that different implementations of a cell are able to interoperate harmoniously.
The overall status of the system must be presented on a management cockpit.

<!--
(The lamp cells implemented by a group of students must be interoperable with lamp cells implemented by any other group.)
-->

## 4. Assisted Living

### Aging at home

Supporting living and aging in the home, particularly for the elder or people with disabilities or specific diseases.
Control medication taking;
Notify of dangerous events (oven is on for too long, streetdoor was left open);
Control people activity (Normal? Not moving for too long? Pressed emergency button? Not reacting to an event?)

**References:**

- [Ageing Well in the Digital World](http://www.aal-europe.eu/)
  - [AAL Catalogue of Project (2008 – 2013)](http://www.aal-europe.eu/wp-content/uploads/2015/09/15-1805_AAL_Catalogue_2015_ONLINE.pdf)

### Smart lost-and-found

Consider the problem of tagged objects localization in outdoor and indoor spaces.
Develop a solution that enables the user to look for its lost objects.
Since the objects can convey private information about its owner, the information should be stored and communicated with security and privacy, so that only the legitimate owner can query the system and s/he can avoid being tracked.

**References:**

- [Apple AirTags](https://www.macrumors.com/guide/airtags/)
- [Tile tags](https://www.thetileapp.com/en-us/how-it-works)

### Secure child locator

Consider the problem of child localization in outdoor or indoor spaces.
Develop a solution for smartphone or smartwatch users that enables the tracking of children only by their authorized legal guardians and not by anyone else.
The solution could operate outdoors, using GPS (e.g. A-GPS), but could also operate indoors, where GPS does not work.
Indoor location can rely on Wi-Fi fingerprinting (e.g. Google Indoors Maps), Bluetooth beacons, Li-Fi, or other techniques.

The solution should consider the secure tracking of the children inside defined virtual fences and there should be an alert (SOS) functionality.
Both the children and the responsible adult should be regarded as users of the system, and all stored and communicated data should consider user consent and their privacy.
If a remote server is used, it should not be fully trusted. For example, the solution may assume the server to be honest-but-curious, i.e., it follows application protocols but tries to collect as much data as possible about the users.

**References**:

- [My Ki system](https://myki.watch/en/)
- EASYmaxx [Smartwatch](https://www.amazon.de/EASYmaxx-Smartwatch-Armbanduhr-Sprachnachrichten-Standortlokalisierung-blau/dp/B07BZ292D9) and [iOS app](https://apps.apple.com/us/app/easymaxx-smartwatch/id1375209119)
- <https://www.google.com/maps/about/partners/indoormaps/>

----

### Scale for the blind

This project proposes a weight scale for the blind.
The scale can "speak" the results of the measurement.

Due to the increasing developments in the field of Ambient Intelligent as well as the increasing possibilities of solutions to support impaired persons, there is a growing interest in this kind of system.
In particular, a higher level of independence and increased quality of life can be generated by various products.
For example, develop a solution that makes it easier for blind people to pour and combine different drinks into a vessel according to their own preferences.
With the help of *voice recognition* and *voice commands*, an interaction with the scale can be established so that the blind person can tell the scale exactly how much of which liquid he or she wants to have in his or her glass.
The scale can also *speak* back, to state how much liquid/solid is being weighted.

**References:**

- <https://www.maxiaids.com/talking-scales>

----

[AmI Faculty](mailto:meic-ami@disciplinas.tecnico.ulisboa.pt)
