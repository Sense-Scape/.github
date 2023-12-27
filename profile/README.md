# Sense-Scape

## Summary

An audio streaming platform which receives data from multiple audio sensors, stores the data and forwards it to a pretty Svelte UI

## System Overview

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
click AudioSimulator "https://github.com/Sense-Scape/Windows_Sensor_Sim/" "Go to";
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

## Organisation Summaries
- Our [repositories](https://github.com/orgs/Sense-Scape/repositories)
- Our [documentation](https://github.com/Sense-Scape/.github) root directory
- Our [System Outline](https://github.com/Sense-Scape/.github/blob/main/profile/System%20Outline.md) displays granular description of software interaction

## Developer Docs
- How we use  [Sub Modules](https://github.com/Sense-Scape/.github/blob/main/manuals/Sub%20Module%20Usage.md)
- How we [transmit and receive](https://github.com/Sense-Scape/.github/blob/main/manuals/Chunk%20Tx%20Rx.md) Chunks between different processes
