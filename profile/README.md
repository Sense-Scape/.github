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

Get the most recent releases of the software components. Software releases may be found here: 

- [Windows Simulator](https://github.com/Sense-Scape/Windows_Sensor_Sim/) and its [releases](https://github.com/Sense-Scape/Windows_Sensor_Sim/releases)
- [Processing Server](https://github.com/Sense-Scape/Windows_Proc_Serv/) and its [releases](https://github.com/Sense-Scape/Windows_Proc_Serv/releases)
- [TCPPWebSocketAdapter](https://github.com/Sense-Scape/Go_TCP_Websocket_Adapter/) and its [releases](https://github.com/Sense-Scape/Go_TCP_Websocket_Adapter/releases)
- [Svelte UI](https://github.com/Sense-Scape/Svelte-Website/) and its [releases](https://github.com/Sense-Scape/Svelte-Website/releases)

Some come with config files and will require one to configure IP addresses and ports - The aim is that this shall come preconfigured but this is not complete at this point.

If you are really feeling fancy you can take a look at [these](https://github.com/Sense-Scape/Python_Simulations/blob/main/PropogationModelling.ipynb) simulations to see how this system should be able to detect boats from quite far away (If one chooses to submerge their micrphones). The simulations are a work in progress and may be altered at any point. Testing procedures and results shall be stored in [this](https://github.com/Sense-Scape/Testing_Docs/tree/main) repository with the raw WAV data from these tests stored in [this](https://mega.nz/folder/QqlXnC4D#bC72lV5hunTv-RFYAa51Kg) MEGA folder.

## Feature Development Timeline

``` mermaid

timeline
    Milestone 1 : Simulator (Done) : Processing Server (Done) : Live Storage (Done) : Live UI (Done) : Hardware Prototype (Done) : Data Collection (Done)
    Milestone 2 : Full Linux Support (Done) : Fixed Installation (In Progress) : Produce Mic Array (In Progress) : Playback (Done) : GPS (time, pos) : Handle Multiple HW : Data Collection
    Milestone 3 : Mechanicals (Housing, BMS) : SOAK Testing : Live GIS : Live Tracking

```

## Organisation Summaries
- Our [repositories](https://github.com/orgs/Sense-Scape/repositories)
- Our [documentation](https://github.com/Sense-Scape/.github) root directory
- Our [System Outline](https://github.com/Sense-Scape/.github/blob/main/profile/System%20Outline.md) displays granular description of software interaction

## Developer Docs
- How we use  [Sub Modules](https://github.com/Sense-Scape/.github/blob/main/manuals/Sub%20Module%20Usage.md)
- How we [transmit and receive](https://github.com/Sense-Scape/.github/blob/main/manuals/Chunk%20Tx%20Rx.md) Chunks between different processes
