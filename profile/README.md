# Sense-Scape

An audio streaming platform which recieves data from multiple remote sensors, stores the data and forwareds it to a pretty Svelte UI

## System Overview

``` mermaid
graph TD; 

Sensor1 --TCP--> ProcessingServer
Sensor2 --TCP--> ProcessingServer
Sensor3 --TCP--> ProcessingServer

ProcessingServer --TCP-->GoTCPWebSocketAdapter
ProcessingServer --> AudioStorage
GoTCPWebSocketAdapter --WebSocket-->SvelteKitUI

```

## Organisation Summaries
- Our [repositories](https://github.com/orgs/Sense-Scape/repositories)
- Our [documentation](https://github.com/Sense-Scape/.github) root directory
- Our [System Outline](https://github.com/Sense-Scape/.github/blob/main/profile/System%20Outline.md) displays granular description of software interaction

## Developer Docs
- How we use  [Sub Modules](https://github.com/Sense-Scape/.github/blob/main/manuals/Sub%20Module%20Usage.md)
- How we [transmit and receive](https://github.com/Sense-Scape/.github/blob/main/manuals/Chunk%20Tx%20Rx.md) Chunks between different processes
