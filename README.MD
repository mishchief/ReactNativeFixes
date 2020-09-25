# ReactNativeFixes
## Common Fixes for Common Problems

Common React-Native problems and fixes I'm documenting for other souls to find and not pull their hair too much trying to fix them. Plus if they happen to me again I have them documented.

# Problems & Fixes

### **fatal error: 'config.h' file not found #include "config.h"**


#### Problem

React native won't build and is throwing this error. Fear not it can be fixed.

#### Fix

* In the Terminal, navigate to the ```/react-native/third-party/glog``` folder inside node_modules (for me, this was cd node_modules/react-native/third-party/glog-0.3.4)
* Once actively in this folder, run ```../../scripts/ios-configure-glog.sh```
* Glog is configured and the required config.h header file is created for Xcode to find

After running the above you should be able to build the app.

### **error while installing flipper-glog pod**

#### Problem 

While running `pod install` on MyProject/ios you see this:

```
/<user>/Library/Caches/CocoaPods/Pods/Release/Flipper-Glog/0.3.6-1dfd6/missing: Unknown `--is-lightweight' option
Try `/<user>/Library/Caches/CocoaPods/Pods/Release/Flipper-Glog/0.3.6-1dfd6/missing --help' for more information
configure: WARNING: 'missing' script is too old or missing
configure: error: in `/<user>/Library/Caches/CocoaPods/Pods/Release/Flipper-Glog/0.3.6-1dfd6':
configure: error: C compiler cannot create executables
See `config.log' for more details
```

#### Fix

**Solution 1:**
Run `sudo xcode-select --switch /Applications/Xcode.app`
And then `pod install`

**Solution 2:**
Run `git config --global core.autocrlf false`
And then `pod install`


