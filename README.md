![language](https://img.shields.io/badge/Language-c%2B%2B-green.svg) 
![dependencies](https://img.shields.io/badge/Dependecies-3dRudderSDK-green.svg)
![Visual Studio 2015](https://img.shields.io/badge/Visual%20Studio-2015-brightgreen.svg)
![Firmware 3dRudder](https://img.shields.io/badge/Firmware%203dRudder-%3E%20v1.3.4.0-brightgreen.svg)

This is source code for a VR mod for Half-Life made by Max Vollmer. You may use or reuse this code with giving credit to the original author.

No warranties whatsoever.

with modifications by 

![logo](3dR_Logo.png)

# 3dRudder Integration

* Download [3dRudderSDK](https://github.com/3DRudder/3dRudderSDK/archive/master.zip) and extract in ```cl_dll``` folder
* In Visual studio on cl_dll : Right Click -> Properties -> Linker -> Additional Dependecies
```3dRudderSDK/Lib/Win32/Static/3DRudderSDK.lib```
* Include in .h or .cpp 
```
#define _3DRUDDER_SDK_STATIC 
#include "3dRudderSDK\Include\3dRudderSDK.h"
```
* Get SDK
```
pSdk = ns3dRudder::GetSDK();
pSdk->Init();
```
* Call function in loop
```
ns3dRudder::Status status = pSdk->GetStatus(0);
ns3dRudder::ErrorCode res = pSdk->GetAxis(0, ns3dRudder::ValueWithCurveNonSymmetricalPitch, &axis, &curves);
float pitch = axis.GetXAxis();
...
```
* Close SDK
```
if (pSdk != nullptr)
 ns3dRudder::EndSDK();
pSdk = nullptr;
 ```
* More details on [Wiki](https://github.com/3DRudder/Half-Life-VR/wiki)
# Setup

Extract the archived files into the root directory of Half-life.
 
You will need to set the acl of opengl32.dll to disallow file deletion. (The latest version of half-life prevents a modified opengl32.dll and will actively remove it if the acl is not changed to disallow file deletion.)
 
Use start.bat to launch the vr mod or add following code to steam game launch options:
 * hl.exe -game vr -dev -env -console -insecure -nomouse -nojoy +sv_lan 1 
 
If you try to play Half-life multiplayer with opengl32.dll in the root directory you CAN be VAC (Valve Anti-Cheat) banned.

You can change the speed of translation and rotation in the ```config.cfg``` in ```vr``` folder
 * cl_backspeed "200" -> backward
 * cl_forwardspeed "200" -> forward
 * cl_yawspeed "100" -> rotation left/right
 * cl_sidespeed "100" -> strafe left/right
