---
title: Sending Multiple Video Streams on a Single Peer Connection
keywords: usecase
sidebar: userguide_sidebar
permalink: userguide_advancedusecases.html
folder: userguide
toc: true
---

------

Summary:

A surveillance with NVR solution comprised of SpiderWare embedded IP Cameras connected to a central SpiderWare hub. The central SpiderWare hub ingests the camera streams via RTSP. When a client establishes a Peer with the SpiderWare hub, each ingested RTSP stream is sent as a separate video channel stream.

The system supports a wide array of clients:

● Web Browsers
● IOS Devices
● Android Devices



In detail:

Video surveillance systems typically involve the main user interface screen having at least 4 or more simultaneous active videos playing. This would require the client application to have 1 active stream session per active video panel. Likewise, the application developer would have to set aside resources and code to be able to manage the different concurrent stream sessions. (e.g. each stream would have its own handlers for errors, starting, stopping, events, etc.)

With SpiderWare, it is possible to build a surveillance system where multiple video streams are contained in a single WebRTC peer session!



## Traditional Setup: 1 Video Stream Session per Camera

![](images/userguide/traditionalsurveillance.png)

The diagram above shows a typical setup for a Web Browser-based Surveillance + NVR system.

### Workflow

The setup involves ingest of multiple streams, from different cameras through RTSP, to an NVR. The live streams are then published / played back using browser players through Media Source Extension (MSE) and/or iOS/android devices. Each video stream corresponds to a new connection to/from the player for it to be rendered simultaneously.

### Limitations

- There are cases where playback freezes due to the browsers’ MSE interfaces, when experiencing dropped packets on slow networks.
- The cameras being deployed need to be manually added to the NVR.
- All traffic when doing the playback, goes through the NVR.
- Individual connections for each active stream being viewed.



## SpiderWare Implementation: Multiple video streams per Peer Session

![](images/userguide/spiderwaresurveillance.png)

### Setup

| Item                                    | Description                                                  |
| --------------------------------------- | ------------------------------------------------------------ |
| Camera                                  | SpiderWare will be embedded on the camera.                   |
| Network Video Recorder (NVR)            | Spiderware will be installed on the NVR.                     |
| SpiderWare Exchange Module Server (ExM) | This will be the WebRTC signaling server.                    |
| STUN/TURN Server                        | Components used by WebRTC for establishing peer sessions via ICE protocol. |
| Stream Player (Browser/iOS/Android)     | Will be used to view the streams directly from the camera or from the NVR device. |

### Benefits

- Reduced playback load on NVR due to direct camera peering support
- Reduced camera configuration through camera auto-detection when running embedded SpiderWare
- Stability of playback through SRTP



### Features

- Single WebRTC peer connection for the active streams being viewed simultaneously
- Fallback support to RTSP for legacy or third party cameras
- Reliable and robust SRTP playback with minimal latency
- Updated logging mechanism for ease of parsing, reporting, and archiving
- Up to date WebRTC features and enhancements
- Metadata delivery
- On & Go (auto connect and minimal configuration capability)
- Recording capabilities and a companion video management system