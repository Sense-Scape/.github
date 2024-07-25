# Sense-Scape

## Summary

Primarily a central place to keep all my work relating to acoustics - software, hardware, modelling and system design.
It can also be described as an audio streaming platform which receives data from multiple audio sensors, stores the data and forwards it to a pretty Svelte UI which shows time and frequency domain data

## System Overview

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

## Getting Started

Contact me (Grant Norrie) on linkedin. I shall provide an RPi 3B + image. Flash this turn on the PI and it will automatically start recording all audio and provide a UI to see what is going on. Below is are examples of the UI:

### Live Data View
![UI1](https://github.com/user-attachments/assets/0a83447b-699a-43c2-ab00-200057ca070a)

### GPS Position View
![UI2](https://github.com/user-attachments/assets/f106de36-b73f-4936-8048-982f3a0e6ec4)

### Stored Audio Files
![UI3](https://github.com/user-attachments/assets/13481f1a-f830-4916-ad1b-252be7273274)

## Feature Development Timeline

``` mermaid

timeline
    Milestone 1 : Simulator (Done) : Processing Server (Done) : Live Storage (Done) : Live UI (Done) : Hardware Prototype (Done) : Data Collection (Done)
    Milestone 2 : Full Linux Support (Done) : Playback (Done) : Fixed Installation (Done) : Produce Mic Array (Done)  : GPS (time, pos) (Done) : Handle Multiple HW (Done): Data Collection
    Milestone 3 : Mechanicals (Housing, BMS) : SOAK Testing : Live GIS : Live Tracking

```
