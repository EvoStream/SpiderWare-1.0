---
title: ExM Installation
keywords: exm installation
sidebar: exm_sidebar
permalink: exm_installation.html
folder: exm
toc: true
---

# Installation via NPM

Installing ExM via our private NPM registry is the recommended method. Furthermore, it guarantees that you have the latest file at the time of installation. You just need to issue an npm install command for exm from the repository at **https://webrtc.evostream.com:9000**.

To perform the setup, just follow the following steps:

```
mkdir exm
cd exm
npm i exm --registry https://webrtc.evostream.com:9000
```

**Where to Find the Configuration File**

If you installed ExM via NPM, the configuration can be found at **./node_modules/exm/config/default.json**. The details for editing the configuration file is covered in later in this page.



# Installation via Tarball Method

**Unpacking the ExM Tarball**

By now, you should have acquired the ExM tarball package from one of our support or sales engineers.

Unpack the package in the folder where you wish to have the ExM server reside in.

```
mkdir spiderware
cd spiderware
tar -xvf exm.tar.gz
```

**Note:** If you are installing on Windows, you should use the corresponding tool(s) required for unpacking the tarball.



**Getting the NodeJS Dependencies**

After you unpack the repo, go to the EXM directory, then issue the npm command to download the dependencies.

```
cd exm
npm i
```



**Where to Find the Configuration File**

The configuration file is stored under the file, **./config/default.json**. Before you start ExM, you edit the configuration file to suit your environment setup.

​


