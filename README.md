Instituto Superior Técnico, Universidade de Lisboa

**Ambient Intelligence**

# Project Topics

## 1. Smart home

In the Smart Home there are already emblematic products, like the Nest thermostat from Google, that provide a glimpse of what can be achieved when things are connected between them and to cloud services.
There are also open devices and development kits, like the Arduino and Raspberry Pi, that can be used to develop new ideas in this domain.
The Smart Home hub is a central component in a Smart Home system.
It provides internal connectivity to the sensors, using specific network protocols; and external connectivity to the worldwide Internet, using IP.
The gateway can also play an active role: it can filter data to reduce data volumes and to safeguard the _privacy_ of the people that live in the home; it can also provide a management and monitoring console.
In this scenario, you should management and security features to allow distinct local and remote capabilities for controlling a (simulated) Smart Home.

**Suggested references:**

- <https://www.openhab.org/>
- <https://www.home-assistant.io/>

----

## 2. Smart car

Current automobiles comprise different types of systems, ranging from infotainment and climatization systems to the braking and throttle control systems.
Moreover, they support remote access to perform operations such as monitoring the levels of gas and tire pressure.
However, it is critical that systems such as the braking and throttle control systems cannot be accessed remotely.

In this topic, the car system to develop must include, at least:

- In the car:
  - A Control Unit server that manages all the car's systems and external communications;
  - Pedal peripherals, directly connected to the TEE by a dedicated bus, that may trigger the accelerate and brake operations;
  - Engine controller connected to the Control Unit that validates accelerate operations and regulates the throttle;
  - Brake controller connected to the Control Unit that validates brake operations and brakes the wheels.
- In the manufacturer:
  - A service that allows users to connect to their cars (with their phone or computer), to open doors, regulate the AC, and monitor tire pressure and fuel levels.

You may simulate each part of the system with a VM or a client application and use sockets to simulate the connections.  

**Suggested references:**

- [Survey of the Connected Vehicles](https://ieeexplore.ieee.org/abstract/document/8058008)

----

## 3. Lost-and-found smart tags

In this scenario, consider the problem of tagged objects localization in outdoor and indoor spaces.
Develop a solution that enables the user to look for its lost objects.
Since the objects can convey private information about its owner, the information should be stored and communicated with security and privacy, so that only the legitimate owner can query the system and s/he can avoid being tracked.

**Suggested references:**

- [Apple AirTags](https://www.macrumors.com/guide/airtags/)
- [Tile tags](https://www.thetileapp.com/en-us/how-it-works)

----

## 4. Assisted living

Supporting living and aging in the home, particularly for the elder or people with disabilities or specific diseases
Control medication taking;
Notify of dangerous events (oven is on for too long, streetdoor was left open);
Control people activity (Normal? Not moving for too long? Pressed emergency button? Not reacting to an event?)

----

## 5. Automating smart behaviors

Smart Classroom that adapts its lights and temperature accordingly to the number and location of students; supports different types of classes (interactive, video-projection, …)
Smart lighting for a street, park or a city block
Access control system based on RFID (or…)
Multi-sensor and actuator board (detects presence, temperature, light intensity, ..., and controls on/off outputs, LED lighting, etc)
Simulator of a home (allow users to define a profile with their preferences/requirements; perform actions accordingly with whom is in a specific room; deal with conflicts when different people is in the same room)

----

## 6. DomoBus related projects

Definition of a DomoBus system (generates the XML specification)
Web / Mobile user-interface (monitor and interact with any DomoBus system)
Offer an IoT solution for DomoBus (MQTT based)
Specification of automation rules for a home (define how the home behaves)
Gateway DomoBus↔X10

----

## 7. Energy management

Reduce electricity bill, shift loads to hours when electricity is cheaper, control loads to reduce peak consumption
Measure and balance energy production (from a solar panel) with energy consumption; manage loads using a new model: loads request to turn on and wait for an autorization.

----

[AmI Faculty](mailto:meic-ami@disciplinas.tecnico.ulisboa.pt)
