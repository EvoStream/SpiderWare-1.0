---
title: High Level Overview
keywords: spiderware
sidebar: userguide_sidebar
permalink: userguide_overview.html
folder: userguide
toc: true
---

------

### Basic Use Case

![](images/userguide/spiderware_basic_use_case_-_device.png)

The figure above shows the setup for a minimal system based on SpiderWare.

| Component                     | Description                                                  |
| ----------------------------- | ------------------------------------------------------------ |
| ExM Signaling Server          | As in every WebRTC based system, a signaling server is required to facilitate the establishment of peer sessions. The ExM Signaling server performs the role of the WebRTC signaling server, and much more! |
| **Peer No. 1** - An IP Camera | In this setup, the role of the first peer will be played by an IP Camera. The IP Camera. The IP Camera will be running an embedded version of SpiderWare. |
| **Peer No. 2** - A browser    | In this setup, the role of the second peer will be the browser running a Web application that uses the SpiderWare JavaScript Player library. |

### Basic Workflow

1. The IP Camera powers on. After completing its boot process, SpiderWare will connect to the ExM Signaling Server. After a successful connection, the ExM will maintain the 'presence' of the IP Camera, as long as the connection is active.
2. The user launches the browser and loads the SpiderWare empowered web application. The web application connects to the ExM Signaling server.
3. After a successful connection, the web application receives and displays a list of the other peers that are currently connected to it. In this use case, there is only one other peer – the IP Camera.
4. The user selects the IP Camera.
5. Web application, via the SpiderWare JavaScript player library, tells the ExM that it desires to establish a peer session with the IP Camera.
6. The ExM forwards the request to the IP Camera.
7. The ExM then sends the Web client the necessary information required for it to establish a direct connection to the IP Camera. Likewise, it sends the IP Camera the necessary information for it to establish a direct connection with the browser.
8. Both IP Camera and Browser establish a direct connection with each other.
9. At this point, the IP Camera now start sending video and audio streams to the browser.
10. If the IP Camera is equipped with a speaker, the user may send audio feedback to the camera. This will be played back on the IP Camera speaker.
11. If the IP Camera has PTZ functionality, the user may use the peer session to send PTZ commands back to the camera.



### Modular Design Approach

![](images/userguide/spiderwarepluggable.png)

The diagram above illustrates the modular design strategy used to build SpiderWare. This approach gives SpiderWare a very flexible and powerful ability to be deployed as a super lightweight bare-bones WebRTC module (e.g. in IoT) or as a traditional fully loaded media server.