## Section Summary

[Summary](#summary)

[System Overview](#system-overview)

[Getting Started](getting-started)

[System Overview](#system-overview)

[Feature Development Timeline](#feature-development-timeline)

[Soak Testing](#soak-testing)

[Analysis Tool](#analysis-tool)

[Simulation Tool](#simulation-tool)

[The Sensor](#the-Sensor)

## Summary <a id='summary'></a>

Primarily a central place to keep all my work relating to acoustics - software, hardware, modelling and system design.
It can also be described as an audio streaming platform which receives data from multiple audio sensors, stores the data and forwards it to a pretty UI where one may see system information and live data

## System Overview <a id='system-overview'></a>

``` mermaid
graph LR; 

AudioSensor1 ---> ProcessingServer
AudioSensor2 ---> ProcessingServer
AudioSimulator1 ---> ProcessingServer
ProcessingServer ---> UI
ProcessingServer ---> Storage
Storage ---> AnalysisTools
```

- AudioSensor - RasperryPi with Respeaker array which transmits multiple channels of audio data
- AudioSimulator - Windows simullator which can generate multiple channels with a specific tone and phase offset
- ProcessingServer - Server which hanfles multiple TCP connections from sensors, write their audio data as WAV and forwards it to the websocket converter
- UI - Used to monitor system states, live audio streams and sensor positions
- Storage - There will be data, lots of it
- AnalysisTools - Modelling, simulation and spectral analysis

## Getting Started <a id='getting-started'></a>

Contact me (Grant Norrie) on linkedin if you want to chat.

### Live Data View
![UI1](https://github.com/user-attachments/assets/349da6b3-53e2-4414-a929-9734ddffc4ff)

View multiple live or simulated data streams from multiple devices. System information is also propogated to the UI.

### GPS Position View

![UI2]![viewer3](https://github.com/user-attachments/assets/077cb4e3-76e9-475f-8945-7a2634b33076)

Multiple Sensor positions (set statically or using a live GPS position) may be sent to and displayed on a map.

### Reporting Functionality

![UI2_0](https://github.com/user-attachments/assets/e4802f94-ccd8-4b64-808c-44f7b5901438)

Remote monitoring at the sensor network level - but the sensors will never fail so nothing to worry about :)

### TDOA (In Developement)

![UI2_1](https://github.com/user-attachments/assets/2619c5a6-5453-475e-9cc8-33ea07954e7a)

Example of TDOA alogorithm operating on simulated data. Intersection of the red line is the position of the transmitter.
Green dots are the position of the receivers. TDOA of live data is currently being worked on.

### Stored Audio Files
![UI3](https://github.com/user-attachments/assets/13481f1a-f830-4916-ad1b-252be7273274)

Audio files will be generated and written to a user specified location. In this case an external drive.

## Feature Development Timeline <a id='feature-development-timeline'></a>

``` mermaid

timeline
    Milestone 1 : Simulator (Done) : Processing Server (Done) : Live Storage (Done) : Live UI (Done) : Hardware Prototype (Done) : Data Collection (Done)
    Milestone 2 : Full Linux Support (Done) : Playback (Done) : Fixed Installation (Done) : Produce Mic Array (Done)  : GPS (time, pos) (Done) : Handle Multiple HW (Done)
    Milestone 3 : Mechanicals (Housing, BMS) (Done) : Soak Testing (Done) : Data Collection (Done) : BOM Generation (Done)
    Milestone 4 : TDOA (In Progress) : Direction Finding : Multi Sensor Deployment (Done) : Live GIS (Done) : Remote Deployment Configuration (Done)
    Milestone 5 : Land Based Housing : Multi Sensor Soak Testing : Remote Comms Support : Land Based Power Supply

```

## SOAK Testing Results <a id='soak-testing'></a>

Thanks @wolffshots for running this test - Almost 10 days then the power supply got knocked :)

![state](https://github.com/user-attachments/assets/4fd4cf89-c9ec-4f02-9d80-2687dc0bb9fe)

## Analysis Tool <a id='analysis-tool'></a>

Summary: Pretty Pictures

![image](https://github.com/user-attachments/assets/a291fa32-e309-4f22-92dc-7a0a0517091d)

## Simulation Tool <a id='simulation-tool'></a>

Summary: Math

![image](https://github.com/user-attachments/assets/a60f390f-bf28-405d-b4df-99b001e7ba51)

## The Sensor <a id='the-sensor'></a>

### Submersible

Summary: ooooh, ahhhh, so fancy (but not really)

![4e0ccd7e-6c5c-412c-84ba-0f0250fa754c](https://github.com/user-attachments/assets/4c8143ef-6a3e-480b-8d98-dbaa7b118c18)

### The one who is scared of water

Coming soon...


