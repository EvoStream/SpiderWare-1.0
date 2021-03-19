---
title: ExM Configuration
keywords: exm
sidebar: exm_sidebar
permalink: exm_configuration.html
folder: exm
toc: true
---



**Warning!** Before you edit the configuration file please make a backup copy. If the configuration file is edited incorrectly, ExM will fail to start! We highly recommend that you use an editor that is capable of parsing JSON formatted text files. That way, the editor can quickly tell you if you broke the JSON format.

The following snippet shows how the **default.json** is structured.

```
{
    "api" : {
        "version" : "0.1",
        "port" : 4000,
        "auth" : {
            "rootemail"   : "admin@gmail.com",
            "rootpassword": "admin123secret",
            "tokensecret" : "mysecret",
            "tokenexpiry" : 3600
        },
        "mongodb" : {
            "uri" : "mongodb://127.0.0.1:27017/exmspider"
        }
    },
    "exm": {
        "port": 5555,
        "secure": true,
        "useauth": true
        }
    },
    "web": {
        "enabled": true,
        "port": 8080,
        "secure": true,
        "securePort": 8443,
        "webRoot": "./public"
    },
    "ssl": {
        "key": "/home/me/exm/cert/key.pem",
        "cert": "/home/me/exm/cert/cert.pem",
        "password": "mysecret",
        "ca": null,
        "selfsigned":     true
    },
    "log": {
        "enabled": true,
        "level": "info",
        "consoleEnabled": true,
        "fileName": "./log/exm-%DATE%.log",
        "datePattern": "YYYY-MM-DD",
        "maxFiles": "30d"
    },
    "stun": [
        {
            "urls": "stun:stun.l.google.com:19302"
        },
        {
            "urls": "stun:stun1.l.google.com:19302"
        }
    ],
    "turn": [
        {
            "urls": "turn:144.202.171.100:55555",
            "secret": "12345thisIsJustAtest12345",
            "expiry": 86400
        }
    ]
}
```


## Common Settings

|      Item      | Description                                                  |
| :------------: | ------------------------------------------------------------ |
|    ssl.key     | Set this to the SSL key file of the certificate that you will use. |
|    ssl.cert    | Set this to the SSL cert file of the certificate that you will use. |
|  ssl.password  | Set this to the passphrase of the certificate that you will use. |
| ssl.selfsigned | Set this to **true** if you're using a self-signed certificate. |

## ExM API

|    Item     | Description                                                  |
| :---------: | ------------------------------------------------------------ |
|  api.port   | This is the TCP Port that the ExM API shall bind to. It is currently set to 4000. Unless you absolutely need to, we recommend you keep this as-is |
| api.mongodb | Set this to the URL of your MongoDB database.                |

## ExM Signaling Server

|        Item        | Description                                                  |
| :----------------: | ------------------------------------------------------------ |
|      exm.port      | This is the TCP Port that the ExM API shall bind to. It is currently set to 4000. Unless you absolutely need to, we recommend you keep this as-is. |
| exm.api.selfsigned | If you are using a self-signed certificate in **api.https**, then you should set this to **true**. Otherwise, set this to **false**. |
|        stun        | Populate this array with the URLs of the STUN servers that you are using. The stun URL format is: **stun:<IP or Hostname>:Port** <br />example: stun:stun.l.google.com:19302 |
|        turn        | Populate this array with the URLs of the TURN servers that you are using. A turn entry has the following format: **{“urls” : turn:<IP or Hostname>:port,“secret” : <secret key for that turn server>“expiry” : <Expiry value for that turn server>}** |

## Configuring the ExM Frontend Demo Page

|      Item      | Description                                |
| :------------: | ------------------------------------------ |
|    web.port    | This is the non-secure (HTTP) port to use. |
| web.secureport | This is the secure (HTTPS) port to use.    |

