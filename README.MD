# ReactNativeFixes
## Common Fixes for Common Problems

Common React-Native problems and fixes I'm documenting for other souls to find and not pull their hair too much trying to fix them. Plus if they happen to me again I have them documented.

# Problems & Fixes

## **fatal error: 'config.h' file not found #include "config.h"**


### Problem

React native won't build and is throwing this error. Fear not it can be fixed.

### Fix

* In the Terminal, navigate to the ```/react-native/third-party/glog``` folder inside node_modules (for me, this was cd node_modules/react-native/third-party/glog-0.3.4)
* Once actively in this folder, run ```../../scripts/ios-configure-glog.sh```
* Glog is configured and the required config.h header file is created for Xcode to find

After running the above you should be able to build the app.