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
It can also be described as an audio streaming platform which receives data from multiple audio sensors, stores the data and forwards it to a pretty Svelte UI which shows time and frequency domain data

## System Overview <a id='system-overview'></a>

``` mermaid
graph LR; 

AudioSensor1 ---> ProcessingServer
AudioSensor2 ---> ProcessingServer
AudioSimulator1 ---> ProcessingServer

ProcessingServer --->GoTCPWebSocketAdapter
ProcessingServer --> AudioStorage

GoTCPWebSocketAdapter --->SvelteKitUI
```

- AudioSensor - RasperryPi with Respeaker array which transmits multiple channels of audio data
- AudioSimulator - Windows simullator which can generate multiple channels with a specific tone and phase offset
- ProcessingServer - Server which hanfles multiple TCP connections from sensors, write their audio data as WAV and forwards it to the websocket converter
- GoTCPWebSocketAdapter - Forwards data from server to web front end
- SvelteKitUI - UI that displays sensor data

## Getting Started <a id='getting-started'></a>

Contact me (Grant Norrie) on linkedin. I shall provide an RPi 3B + image. Flash this turn on the PI and it will automatically start recording all audio and provide a UI to see what is going on. Below is are examples of the UI:

### Live Data View
![UI1](https://github.com/user-attachments/assets/0a83447b-699a-43c2-ab00-200057ca070a)

View multiple live or simulated data streams from multiple devices. System information is also propogated to the UI.

### GPS Position View
![UI2](https://github.com/user-attachments/assets/f106de36-b73f-4936-8048-982f3a0e6ec4)

Multiple Sensor positions (set statically or using a live GPS position) may be sent to and displayed on a map.

### Stored Audio Files
![UI3](https://github.com/user-attachments/assets/13481f1a-f830-4916-ad1b-252be7273274)

Audio files will be generated and written to a user specified location. In this case an external drive.

## Feature Development Timeline <a id='feature-development-timeline'></a>

``` mermaid

timeline
    Milestone 1 : Simulator (Done) : Processing Server (Done) : Live Storage (Done) : Live UI (Done) : Hardware Prototype (Done) : Data Collection (Done)
    Milestone 2 : Full Linux Support (Done) : Playback (Done) : Fixed Installation (Done) : Produce Mic Array (Done)  : GPS (time, pos) (Done) : Handle Multiple HW (Done)
    Milestone 3 : Mechanicals (Housing, BMS) (Done) : Soak Testing (Done) : Data Collection (Done) : BOM Generation (Done)
    Milestone 4 : TDOA (In Progress) : Direction Finding : Multi Sensor Deployment (In Progress) : Live GIS : Remote Deployment (In Progress)

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

Summary: ooooh, ahhhh, so fancy (but not really)

![4e0ccd7e-6c5c-412c-84ba-0f0250fa754c](https://github.com/user-attachments/assets/4c8143ef-6a3e-480b-8d98-dbaa7b118c18)


