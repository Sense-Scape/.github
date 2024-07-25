# Sense-Scape

## Summary

Primarily a central place to keep all my work relating to acoustics - software, hardware, modelling and system design.
It can also be described as an audio streaming platform which receives data from multiple audio sensors, stores the data and forwards it to a pretty Svelte UI which shows time and frequency domain data

## System Overview

Note: press `ctrl` + `click` to open repositories

``` mermaid
graph LR; 

AudioSensor1 ---> ProcessingServer
AudioSensor2 ---> ProcessingServer
AudioSimulator1 ---> ProcessingServer

ProcessingServer --->GoTCPWebSocketAdapter
ProcessingServer --> AudioStorage

GoTCPWebSocketAdapter --->SvelteKitUI

click AudioSensor1 "https://github.com/Sense-Scape/RPi_Sensor" "Go to";
click AudioSensor2 "https://github.com/Sense-Scape/RPi_Sensor" "Go to";
click AudioSimulator1 "https://github.com/Sense-Scape/Windows_Sensor_Sim" "Go to";
click ProcessingServer "https://github.com/Sense-Scape/Windows_Proc_Serv" "Go to";
click GoTCPWebSocketAdapter "https://github.com/Sense-Scape/Go_TCP_Websocket_Adapter" "Go to";
click SvelteKitUI "https://github.com/Sense-Scape/Svelte-Website/" "Go to";

```

- AudioSensor - RasperryPi with Respeaker array which transmits multiple channels of audio data
- AudioSimulator - Windows simullator which can generate multiple channels with a specific tone and phase offset
- ProcessingServer - Server which hanfles multiple TCP connections from sensors, write their audio data as WAV and forwards it to the websocket converter
- GoTCPWebSocketAdapter - Forwards data from server to web front end
- SvelteKitUI - UI that displays sensor data

## Getting Started

Contact me on linkedin and I can provide a preconfigured Raspberry Pi 3B + image and instructions on how to assemble the hardware. Once powered on it will launch the UI and start recording immediately 

## Feature Development Timeline

``` mermaid

timeline
    Milestone 1 : Simulator (Done) : Processing Server (Done) : Live Storage (Done) : Live UI (Done) : Hardware Prototype (Done) : Data Collection (Done)
    Milestone 2 : Full Linux Support (Done) : Playback (Done) : Fixed Installation (In Progress) : Produce Mic Array (In Progress)  : GPS (time, pos) (Done) : Handle Multiple HW (Done): Data Collection
    Milestone 3 : Mechanicals (Housing, BMS) : SOAK Testing : Live GIS : Live Tracking

```

