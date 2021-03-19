---
title: Glossary
keywords: spiderware
sidebar: userguide_sidebar
permalink: userguide_glossary.html
folder: userguide
toc: false
---

|       Term        | Definition                                                   |
| :---------------: | ------------------------------------------------------------ |
|        ExM        | SpiderWare Exchange Module                                   |
| ExM Signal Server | The ExM Signal Server provides the platform that allows SpiderWare apps and clients to detect and peer with each other. |
|      ExM API      | The ExM API provides functions for managing the Users and the Sessions defined in the ExM database. The API is used by the ExM Signal Server and the ExM FrontEnd. |
|   ExM FrontEnd    | This is a simple application that serves two purposes:<br />**(1)** It can be used as a quick test application to see if the ExM is installed and running properly. <br />**(2)** Its code can be used as an example to study and/or copy for developing your own JavaScript based ExM application. |
|  ROOM vs SESSION  | Unless specified otherwise, this document shall use the more proper term “**ROOM**” instead of the marketing word “**SESSION**”.Using the term “**SESSION**” to describe the role of “**ROOM**” is not only confusing, but is also disruptive.  The term “**SESSION**” is used in “**PEER SESSION**”, which describes the state when two peers have successfully established a SESSION with each other. |



## System Requirements

The ExM can either run alongside the SpiderWare or on a completely separate computer. The EMS Web Services can run on Linux operating system.

- At least 4GB in memory

- Ubuntu 18.04 x64 or Ubuntu 20.04 x64

- Mongo DB v3.6.8 and up (It is strongly recommended that you setup MongoDB to run as a service on your system!)

- NodeJS v10.9.0 and up

- NPM v6.14.5 and up

- OpenSSL 1.1.1 11 Sep 2018

- Internet access

  **Note:**  Since the ExM runs on top of NodeJS and MongoDB, it should, in theory run fine under any Operating System that has the same or higher versions of NodeJS and MongoDB (e.g. Windows). However, we only officially support Ubuntu 18.04/20.04 LTS as of this time.

