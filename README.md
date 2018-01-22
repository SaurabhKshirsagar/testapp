
### **site-webdeploy** is a command line interface for running commands against bitpod site deployment. 
## Install
***
1. You can install with npm or yarn package manager. 
  ```plaintext 
  npm install --save -D @bitpod/site-webdeploy
  ``` 
  ```plaintext  
  yarn add -D @bitpod/site-webdeploy
  ``` 

2. Run **site-webdeploy version** to verify that the version you’ve installed is sufficiently up-to-date.

## Setup
***
1. Create **site-webdeploy.json** file in root directory of your project using following json.
 ```JSON download site-webdeploy.json
 {
    "token": "b93ad366b3403e1afa86eae2be649cb4aa87baea733aa8c728eb8fb0cf9d7b63",
    "appid": "builder",
    "instanceid": "rkux24G4M",
    "siteid": "Hyy1hBMEz",
    "bitpodapiURL": "/api",
    "deploypath": "/deploy",
    "routes": [
        {"key":"vendor","value":"/vendor-manifest.json"}
        {"key":"*","value":"/index.html"}
    ]
  }
  ```
  
  **Note :**  Don't forget to update token value, if you refresh token. **deploypath** is your build directory path.         

2. Create an entry for deploy in your package.json file under scripts node.
  ```JSON download package.json
  {
    "name": "MyApp",
    "version": "1.0.0",
    "main": "index.js",
    "scripts": {
      "build" : "webpack -p" ,
      "deploy": "site-webdeploy deploy "
    }
  }
  ```
