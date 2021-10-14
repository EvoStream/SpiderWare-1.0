---
title: Installation on Linux OS
sidebar: userguide_sidebar
permalink: userguide_installlinuxos.html
folder: userguide
toc: true
---



## Installation Procedure

### 1. Install VMS API

### 2. Install VMS APP

The VMS APP server functions to communicate between the sources and the VMS API.

#### Pre-requisites

1. Install MongoDB

   ```
   curl -fsSL https://www.mongodb.org/static/pgp/server-4.4.asc | sudo apt-key add -
   ```

2. Check that key is added successfully

   ```
   apt-key list
   ```

3. Create a file in the sources.list.d directory named mongodb-org-4.4.list

   ```
   echo “deb [ arch=amd64,arm64 ] https://repo.mongodb.org/apt/ubuntu bionic/mongodb-org/4.4 multiverse” | sudo tee /etc/apt/sources.list.d/mongodb-org-4.4.list
   ```

4. Update server local package index

   ```
   sudo apt update
   ```

5. Install MongoDB

   ```
   sudo apt install mongodb-org
   ```



#### MongoDB Service

1. Start the MongoDB service

   ```
   sudo systemctl start mongod.service
   ```

2. Check the status of the MongoDB service

   ```
   sudo systemctl status mongod
   ```

3. Enable the MongoDB service on startup

   ```
   sudo systemctl enable mongod
   ```



Follow the instructions here to setup access control to protect your MongoDB installation https://docs.mongodb.com/manual/tutorial/enable-authentication/.



#### Mounting SpiderWare recordings and recallings folders

1. Generate the key

   ```
   ssh-keygen -t rsa
   ```

2. Create .ssh folder where SpiderWare is installed

   ```
   ssh root@spiderware_host "mkdir -p .ssh"
   ```

3. Upload the generated public keys to the SpiderWare host

   ```
   cat ~/.ssh/id_rsa.pub | ssh root@spiderware_host "cat >> ~/.ssh/authorized_keys"
   ```

4. Set permissions in the SpiderWare host

   ```
   ssh root@spiderware_host "chmod 700 ~/.ssh; chmod 640 ~/.ssh/authorized_keys"
   ```

5. In the SpiderWare host,

   5.a. Create the `recordings` and `recallings` folders under the Spiderware directory. The `recordings` and `recallings` folders should be present; otherwise, the calls to sshfs to mount these folders fail. **See 7.**

   ```
   The Spiderware directory should have the following structure:
   
   ├── spiderware
   ├── config
   ├── recordings
   ├── recallings
   ```

6.  Create the recordings and recallings mount point folders under the VMS APP app directory. 

   **Note:** The mount point is relative to the `recordingsFolder` defined in the configuration file.

   See **config_app.md**. In the following example, the `recordingsFolder` is set to `public/recordings`.

   For recordings:

   ```
   Command: `mkdir <vms app folder>/public/recordings/<mount_point>`
   Example: `mkdir -p /home/xyz/vmsapp/public/recordings/swmp1`
   ```

   For recallings:

   ```
   Command: `mkdir <vms app folder>/public/recordings/recallings/<mount_point>`  
   Example: `mkdir -p /home/xyz/vmsapp/public/recordings/recallings/swmp1`
   ```

7. Mount recordings and recallings folders using sshfs

   ```
   Command: `sshfs <args> <user>@<host>:<folder> <mount_point>`
   Example: `sshfs -o allow_other,default_permissions,reconnect,ServerAliveInterval=15,ServerAliveCountMax=3 root@spiderware_host:/root/spiderware/recordings ./public/recordings/swmp1`
   (assuming current directory is /home/xyz/vmsapp)
   ```

8. To unmount the recordings and recalling folders, do:

   ```
   - `umount <mount_point>, e.g., umount ./public/recordings/swmp1`
   - `umount <mount_point>, e.g., umount ./public/recordings/recallings/swmp1`  
   ```

   

**Notes:**

- The steps described above are applicable to both Linux and MacOS. However, to work under MacOS, sshfs requires osxfuse.
    `brew install osxfuse sshfs`

- To mount folders under Windows, use https://github.com/billziss-gh/sshfs-win.  



### 3. Install VMS OVS



### 4. Install SpiderWare

To install SpiderWare, please refer to https://spiderdocs.evostream.com/index.html

Make sure to enter the correct VMS APP URL in the configuration file:

```
"events":
{
	"sinks": [
		{
			"type": "sio",
			"url": "https://vmsapp.evostream.com:3000/nsSpiderware"    >VMS APP URL
		}
	]
}
```



## Distribution Content

**A. VMS APP**

```
├── vmsp-app-linux
│   └── config
│       └── config.js
│   └── docs
│       ├── config_app.md
│       ├── mount_sw_rec_app.md
│       ├── prerequisites_app.md
│       └── README_app.md
│   └── logs (will be generated once the application run)
└   └── vma-app
```

**B. VMS API**

```
├── vmsp-api-linux
│   └── config
│       └── config.js
│   └── docs
│       ├── config_api.md
│       ├── prerequisites_api.md
│       └── README_api.md
│   └── logs (will be generated once the application run)
└   └── vms-api
```

**B.1. VMS OVS**

```
├── vmsp-ovs-linux
│   └── config
│       └── config.js
│   └── docs
│       ├── config_ovs.md
│       ├── prerequisites_ovs.md
│       └── README_ovs.md
│   └── logs (will be generated once the application run)
└   └── vms-ovs
```



### 



