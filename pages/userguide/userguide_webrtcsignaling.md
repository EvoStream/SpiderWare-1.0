---
title: WebRTC Signaling
keywords: webrtc
sidebar: userguide_sidebar
permalink: userguide_webrtcsignaling.html
folder: userguide
toc: true
---

------

One of the strengths of WebRTC is its use of the [Interactive Connectivity Establishment (ICE) Protocol](https://tools.ietf.org/html/rfc5245) for establishing connections between two peers, regardless of the peer's network setup. But before ICE can come into play, there has to be a way to provide peers that wishing to connect with the necessary parameters for each to kick off ICE.



## An Online Lobby Server



![](images/userguide/webrtc_signaling_part_1.png)

Think of the WebRTC Signaling server as a kind of online lobby server where each peer will log in and register. Once registered, the signaling server will keep a record of the peer's address. It will also send back a list of peers that are already registered.

![](images/userguide/webrtc_signaling_part_2.png)

When another peer connects, the WebRTC Signaling server record the new peer's info, and will send back a list of registered peers. This time, it will return two peers – itself and the camera.



## Initiating a Peer Session

![](images/userguide/webrtc_signaling_part_4.png)

A Peer session is initiated when one of the peers (in this case, the “Browser”) tells the Signaling Server that it wants to have a peer with another peer (in this case, the “IP Camera Home”).

![](images/userguide/webrtc_signaling_part_5.png)

Next, the Signaling Server sends both peers the information they need to initiate a peering session via ICE protocol.

![](images/userguide/webrtc_signaling_part_6.png)

Once both peers receive the connection information, they can now start establishing a peering session using ICE protocol.