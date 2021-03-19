---
title: A quick introduction to WebRTC
keywords: webrtc
sidebar: userguide_sidebar
permalink: userguide_webrtc.html
folder: userguide
toc: false
---

------



## What is WebRTC?

The following explanation was quoted from the [WebRTC home page](https://webrtc.org/):

```
WebRTC is an open framework for the web that enables Real Time Communications in the browser. It includes the fundamental building blocks for high-quality communications on the web, such as network, audio and video components used in voice and video chat applications.
These components, when implemented in a browser, can be accessed through a JavaScript API, enabling developers to easily implement their own RTC web app.
The WebRTC effort is being standardized on an API level at the W3C and at the protocol level at the IETF.
```

The above quote gives a good summary of WebRTC. From that, you can draw important points which can be itemized as follows:

- **WebRTC is a Framework** - By “framework”, it means that it is comprised of different modules and protocols that work together to achieve the desired functionality.
- **Real Time Communications in the Browser** - This is the default distribution of WebRTC. Most popular browsers such as Chrome and FireFox already come with a WebRTC stack built-in. All that’s needed is to run the corresponding WebRTC web application to get started.
- **Open** - It is open source, and it is licensed under BSD. By being open source developers can build the framework on different systems and devices. Hence, while out-of-the-box deployment of WebRTC is on browsers, we are not limited to this. This means that given the right circumstances, any device can be empowered with WebRTC.
- **Standardized at the W3C and IETF** - The API is standardized at the W3C. This means that one can develop applications against the API, rest assured that it will behave consistently across all supported platforms. Likewise, the protocols used by WebRTC (SRTP, SCTP, ICE, etc.) are standardized at the IETF. All-in-all, this means that as long as the application uses the APIs and protocols correctly, then the application should be able to communicate flawlessly with other applications that use WebRTC.



## Components of a WebRTC System

![](images/userguide/webrtccomponents.png)

The diagram above shows the basic, albeit simplified setup of the components that comprise WebRTC. If this has piqued your interest, you are encouraged to check the [WebRTC Architecture](https://webrtc.github.io/webrtc-org/architecture/).

The components are:

- **WebRTC Endpoint** - A WebRTC Endpoint is an entity that has a WebRTC stack running on it. As such, an endpoint can be anything. It can be a Web application running on a browser that supports webrtc. It can also be a standard application built on top of the WebRTC stack and deployed on a desktop or embedded on a device. (NOTE: Throughout this document, the term “WebRTC Endpoint” and “endpoint” shall be used interchangeably.)
- **Signaling Server** - The Signaling Server acts as a virtual lobby where endpoints can find other WebRTC Endpoints to connect to. It goes without saying that the Signaling Server has to be deployed in a location that is directly accessible to all endpoints. As such, the Signaling Server is usually deployed in the cloud with a public IP.
- **TURN (Traversal Using Relays around NAT) Server** - One of the biggest strengths of WebRTC is its utilization of ICE (Interactive Connectivity Establishment) Protocols to allow an endpoint to initiate a peering session with another endpoint regardless of the network setup. If both endpoints have public IP addresses, then a direct peering session can be established, as indicated in the diagram by Endpoint 1 and Endpoint 2. Likewise, if one or both endpoints are located behind a NAT (common setup for endpoints connected via ISP), a direct peering session may still be possible using STUN protocol. Lastly, there are cases where a session via STUN cannot be established. In this situation, the TURN server steps in. Under a TURN based connection, both endpoints connect to the TURN server. The TURN server relays the data between two endpoints. In the diagram above, this is the session between Endpoint 2 and Endpoint 3.
- **WebRTC Peering Session** - A Peering Session between two endpoints is actually comprised of one or more streams. Voice, Video and Data are sent on separate streams. Please note that this document won’t go into detail on how the underlying interplay between the Endpoints and the Signaling Server in establishing Peering Sessions.