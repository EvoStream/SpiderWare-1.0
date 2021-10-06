---
title: Installation on Linux OS
sidebar: userguide_sidebar
permalink: userguide_installlinuxos.html
folder: userguide
toc: true
---



## VMS APP

The VMS APP is the ...



### Installation Procedure

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



## Distribution Content

**A. VMS APP**

```
├── etc
│   └── evostreamms
│       ├── blacklist.txt
│       ├── config.lua
│       ├── server.cert
│       ├── server.key
│       ├── users.lua
│       ├── webconfig.lua
│       └── whitelist.txt
```

**B. VMS API**

```
├── usr
│   ├── bin
│   │   ├── evo-avconv
│   │   ├── evo-mp4writer
│   │   ├── evo-node
│   │   ├── evostreamms
│   │   ├── node-ews
│   │   ├── node-webservices
│   │   ├── node-webui
```

**B.1. VMS OVS**

```
├── usr
│   ├── bin
│   │   ├── node-ews
│   │   |   ├── evo-phpengine
│   │   |   ├── ews.node
│   │   |   ├── fileRotateSize.js
│   │   |   ├── helper.js
│   │   |   ├── node-ews.js
│   │   |   ├── node_modules
│   │   │   |   ├── basic-auth
│   │   │   |   ├── connect
│   │   │   |   └── winston
│   │   |   └── req_handlers     
│   │   │   |   ├── authproxy.js
│   │   │   |   ├── default.js
│   │   │   |   ├── httpstream.js
│   │   │   |   ├── php.js
│   │   │   |   └── resphdrs.js  
```

**B.2. Node-Webservices Files**

```
├── usr
│   ├── bin
│   │   ├── node-webservices
│   │   |   ├── app.js
│   │   |   ├── base_plugins
│   │   │   |   ├── basehdsplugin.js
│   │   │   |   ├── basehlsplugin.js
│   │   │   |   └── baseplugin.js    
│   │   |   ├── bin
│   │   │   |   └── www       
│   │   |   ├── config
│   │   │   |   ├── logging.json
│   │   │   |   └── plugins.json    
│   │   |   ├── core_modules
│   │   │   |   └── ems-api-core.js      
│   │   |   ├── LICENSE
│   │   |   ├── logs
│   │   │   |   └── evowebservices.log          
│   │   |   ├── node_modules
│   │   │   |   ├── body-parser
│   │   │   |   ├── comment-json
│   │   │   |   ├── concat-stream
│   │   │   |   ├── debug
│   │   │   |   ├── express
│   │   │   |   ├── morgan
│   │   │   |   ├── request-enhanced
│   │   │   |   ├── s3
│   │   │   |   └── winston
│   │   |   ├── package.json
│   │   |   ├── plugins
│   │   │   |   ├── amazondashupload.js
│   │   │   |   ├── amazonhdsupload.js
│   │   │   |   ├── amazonhlsupload.js
│   │   │   |   ├── streamautorouter.js
│   │   │   |   ├── streamloadbalancer.js
│   │   │   |   └── streamrecorder.js   
│   │   |   ├── README.md
│   │   |   ├── README.txt
│   │   |   ├── routes
│   │   │   |   ├── evowebservices.js
│   │   │   |   └── index.js      
│   │   |   ├── services
│   │   │   |   └── plugin-service.js
│   │   |   ├── views
│   │   │   |   ├── error.hbs
│   │   │   |   ├── index.hbs
│   │   │   └── └── layout.hbs
```

**B.3. Node-WebUI Files**

```
├── usr
│   ├── bin
│   │   ├── node-webui
│   │   |   ├── app.js
│   │   |   ├── auth
│   │   │   │   ├── passport-config.js
│   │   │   │   └── restrict.js
│   │   |   ├── bin
│   │   │   │   └── webui_activate
│   │   |   ├── config
│   │   │   │   ├── dir-config.js
│   │   │   │   ├── logging.json
│   │   │   │   └── social-auth-config.js
│   │   |   ├── core_modules
│   │   │   │   ├── ems-api-core.js
│   │   │   │   ├── ems-api-proxy.js 
│   │   │   │   ├── ems-config-core.js
│   │   │   │   └──  socket-io-api.js
│   │   |   ├── data
│   │   │   │   ├── help.json
│   │   │   │   └──  user.json   
│   │   |   ├── logs
│   │   │   │   ├── webui.log 
│   │   |   ├── models
│   │   │   │   ├── list-config.js
│   │   │   │   ├── list-streams.js
│   │   │   │   └──  user.js
│   │   |   ├── node_modules
│   │   │   │   └──  [168 node_module files]
│   │   |   ├── public
│   │   │   │   ├── css
│   │   │   │   ├── fonts
│   │   │   │   ├── images
│   │   │   │   ├── js
│   │   │   │   └──  media
│   │   |   ├── routes
│   │   │   │   ├── api-explorer.js   
│   │   │   │   ├── dashboard.js
│   │   │   │   ├── ems.js
│   │   │   │   ├── index.js
│   │   │   │   ├── tream.js
│   │   │   │   └── users.js
│   │   |   ├── services 
│   │   │   │   └──  stream-service.js
│   │   |   ├── views
│   │   │   │   ├── admin
│   │   │   │   ├── index
│   │   │   │   ├── error.hbs
│   │   │   └── └──  index.hbs  
```

**4. XML Files**

```
└── var
    ├── evostreamms
    │   ├── media
    │   └── xml
    │       ├── auth.xml
    │       ├── bandwidthlimits.xml
    │       ├── connlimits.xml
    │       ├── ingestpoints.xml
    │       └── pushPullSetup.xml
```

**5. Evo-Webroot Files**

```
└── var
    ├── evo-webroot
    │   ├── demo
    │   │   ├── css
    │   │   ├── evoplayers.html
    │   │   ├── evo.png
    │   │   ├── evowsabrvideo.html
    │   │   ├── js
    │   │   │   └── evohtml5player-latest.bundle.js 
    │   │   ├── jsonMetaTest.html
    │   │   ├── jsonMetaWriteTest.html
    │   │   └── loading.gif
    │   ├── clientaccesspolicy.xml
    │   └── crossdomain.xml    
```

**6. Log Files**

```
└── var
    ├── log
    │   └── evostreamms
```

**7. Executable Files**

```
└── var
    └── run
        └── evostreamms
```





### Linux Archive

```
./EvoStream Archive
  ├── bin
  │   ├── node-evowebservices
  │   │   ├── base_plugins
  │   │   │	  ├── basehdsplugin.js
  │   │   │	  ├── basehlsplugin.js
  │   │   │	  └── baseplugin.js    
  │   │   ├── bin
  │   │   │   └── www       
  │   │   ├── config
  │   │   │	  ├── logging.json
  │   │   │	  └── plugins.json    
  │   │   ├── core_modules
  │   │   │	  └── ems-api-core.js       
  │   │   ├── logs
  │   │   │	  └── evowebservices.log          
  │   │   ├── node_modules
  │   │   │	  ├── body-parser
  │   │   │	  ├── comment-json
  │   │   │	  ├── concat-stream
  │   │   │	  ├── debug
  │   │   │   ├── express
  │   │   │   ├── morgan
  │   │   │	  ├── request-enhanced
  │   │   │	  ├── s3
  │   │   │	  └── winston
  │   │   ├── plugins
  │   │   │	  ├── amazondashupload.js
  │   │   │	  ├── amazonhdsupload.js
  │   │   │	  ├── amazonhlsupload.js
  │   │   │	  ├── streamautorouter.js
  │   │   │	  ├── streamloadbalancer.js
  │   │   │	  └── streamrecorder.js   
  │   │   ├── routes
  │   │   │	  ├── evowebservices.js
  │   │   │	  └── index.js      
  │   │   ├── services
  │   │   │	  └── plugin-service.js
  │   │   ├── views
  │   │   │   ├── error.hbs
  │   │   │	  ├── index.hbs
  │   │   │	  └── layout.hbs
  │   │   ├── app.js
  │   │   ├── LICENSE
  │   │   ├── package.json
  │   │   ├── README.md
  │   ├── └── README.txt  
  │   ├── node-ews
  │   │   ├── node_modules
  │   │   │   ├── basic-auth
  │   │   │   ├── connect
  │   │   │   └── winston 
  │   │   ├── req_handlers
  │   │   │   ├── authproxy.js
  │   │   │   ├── default.js
  │   │   │   ├── httpstream.js
  │   │   │   ├── php.js
  │   │   │   └── resphdrs.js  
  │   │   ├── evo-phpengine.exe
  │   │   ├── ews.node
  │   │   ├── fileRotateSize.js
  │   │   ├── helper.js
  │   │   └── node-ews.js
  │   ├── node-webui
  │   │   ├── auth
  │   │   │   ├── passport-config.js
  │   │   │   └── restrict.js
  │   │   ├── bin
  │   │   │   └── webui_activate
  │   │   ├── config
  │   │   │   ├── dir-config.js
  │   │   │   ├── logging.json
  │   │   │   └── social-auth-config.js
  │   │   ├── core_modules
  │   │   │   ├── ems-api-core.js
  │   │   │   ├── ems-api-proxy.js 
  │   │   │   ├── ems-config-core.js
  │   │   │   └── socket-io-api.js
  │   │   ├── data
  │   │   │   ├── help.json
  │   │   │   └── user.json   
  │   │   ├── logs
  │   │   │   └── webui.log 
  │   │   ├── models
  │   │   │   ├── list-config.js
  │   │   │   ├── list-streams.js
  │   │   │   └── user.js
  │   │   ├── node_modules
  │   │   │   └── [168 node_module files]
  │   │   ├── public
  │   │   │   ├── css
  │   │   │   ├── fonts
  │   │   │   ├── images
  │   │   │   ├── js
  │   │   │   └── media
  │   │   ├── routes
  │   │   │   ├── api-explorer.js   
  │   │   │   ├── dashboard.js
  │   │   │   ├── ems.js
  │   │   │   ├── index.js
  │   │   │   ├── stream.js
  │   │   │   └── users.js
  │   │   ├── services 
  │   │   │   └── stream-service.js
  │   │   ├── views
  │   │   │   ├── admin
  │   │   │   ├── index
  │   │   │   ├── error.hbs
  │   │   │   └── index.hbs  
  │   │   ├── app.js
  │   │   ├── LICENSE
  │   │   └── package.json     
  │   ├── emsTranscoder.sh
  │   ├── evo-avconv
  │   ├── evo-mp4writer
  │   ├── evostreamms
  │   ├── platformTests
  │   ├── run_console_ems.sh
  │   ├── run_console_webui.sh
  │   ├── run_daemon_ems.sh
  │   ├── run_daemon_webui.sh  
  │   └── run_stop_webui.sh
  ├── config
  │   ├── auth.xml
  │   ├── bandwidthlimits.xml
  │   ├── blacklist.txt
  │   ├── config.lua
  │   ├── connlimits.xml
  │   ├── ingestpoints.cml
  │   ├── pushPullSetup.xml
  │   ├── server.cert
  │   ├── server.key
  │   ├── users.lua
  │   ├── webconfig.json
  │   └── whitelist.txt
  ├── evo-avconv-presets
  │   └── [30 transcode preset files]
  ├── evo-webroot
  │   ├── demo
  │   │   ├── css
  │   │   │   ├── common.css
  │   │   │	  └── common.css.orig  
  │   │   ├── js
  │   │   │	  └── evohtml5player-latest.bundle.js 
  │   │   ├── evo.png
  │   │   ├── evoplayers.html
  │   │   ├── evowsabrvideo.html
  │   │   ├── jsonMetaTest.html
  │   │   ├── jsonMetaWriteTest.html
  │   │   └── loading.gif
  │   ├── clientaccesspolicy.xml
  │   └── crossdomain.xml
  ├── logs
  ├── media
  ├── BUILD_DATE
  ├── Evostream Media Server EULA v2.pdf
  └── README.txt
```



