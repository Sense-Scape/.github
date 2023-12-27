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

```

- AudioSensor - RasperryPi with Respeaker array which transmits multiple channels of audio data
- AudioSimulator - Windows simullator which can generate multiple channels with a specific tone and phase offset
- ProcessingServer - Server which hanfles multiple TCP connections from sensors, write their audio data as WAV and forwards it to the websocket converter
- GoTCPWebSocketAdapter - Forwards data from server to web front end
- SvelteKitUI - UI that displays sensor data

## Organisation Summaries
- Our [repositories](https://github.com/orgs/Sense-Scape/repositories)
- Our [documentation](https://github.com/Sense-Scape/.github) root directory
- Our [System Outline](https://github.com/Sense-Scape/.github/blob/main/profile/System%20Outline.md) displays granular description of software interaction

## Developer Docs
- How we use  [Sub Modules](https://github.com/Sense-Scape/.github/blob/main/manuals/Sub%20Module%20Usage.md)
- How we [transmit and receive](https://github.com/Sense-Scape/.github/blob/main/manuals/Chunk%20Tx%20Rx.md) Chunks between different processes
