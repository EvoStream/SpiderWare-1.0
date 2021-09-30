---
title: Add a Camera
keyword: addcamera
sidebar: userguide_sidebar
permalink: userguide_cameraadd.html
folder: userguide
toc: false
---

There are two options to add a camera: 

**Manual** - adding a camera using camera's RTSP URL

**Scan** - adding a camera via ONVIF



## Manual

1. Go to Camera Management > CAMERAS

2. Click **ADD**

   ![](images/userguide/addcameraform.jpg)

3. Enter the camera details:

   **Camera URL** - the RTSP URL of the camera to be added

   **Camera Name** -  the name that will be assigned to the camera

   **Stream Name** - the name that will be assigned to the camera stream

   **Camera Username** - camera's assigned username

   **Camera Password** - camera's assigned password

   **Camera Group (s)** - the camera group(s) to be assigned

   


3. Click **SAVE**. The saved camera will be listed in the camera list.

   ![](images/userguide/disconnected.jpg)

4. Click **Connect** to start the camera stream.

   ![](images/userguide/connected.jpg)



**Notes:** 

- Stream names should be unique

- Camera Username and Camera Password should be correct

- Camera Group can be assigned after camera has been added

- Multiple camera groups can be selected.

  

  

## SCAN

1. Go to Camera Management > CAMERAS

2. Click **SCAN**

3. Select the scanning method:

   Discovery - will do the scan within the domain

   IP Range - will do the scan within the entered IP address and ports

   ![](images/userguide/scanmethod.jpg)

4. Click **SCAN**, this will search all the cameras using the selected scanning method

   ![](images/userguide/scannedcameras.jpg)

5. Click **Connect** to start the camera stream.

   

**Notes:**

- This will only scan cameras that supports ONVIF.

- The username and password for the cameras can be pre-configured in the VMSOVS server configuration.

  

