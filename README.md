![language](https://img.shields.io/badge/Language-c%2B%2B-green.svg) 
![dependencies](https://img.shields.io/badge/Dependecies-3dRudderSDK-green.svg)
![Visual Studio 2015](https://img.shields.io/badge/Visual%20Studio-2015-brightgreen.svg)
![Firmware 3dRudder](https://img.shields.io/badge/Firmware%203dRudder-%3E%20v1.3.4.0-brightgreen.svg)

This is source code for a VR mod for Half-Life. You may use or reuse this code with giving credit.

No warranties whatsoever.

# Setup

Extract the archived files into the root directory of Half-life.
 
You will need to set the acl of opengl32.dll to disallow file deletion. (The latest version of half-life prevents a modified opengl32.dll and will actively remove it if the acl is not changed to disallow file deletion.)
 
Use start.bat to launch the vr mod or add following code to steam game launch options:
 * hl.exe -game vr -dev -env -console -insecure -nomouse -nojoy +sv_lan 1 
 
If you try to play Half-life multiplayer with opengl32.dll in the root directory you CAN be VAC (Valve Anti-Cheat) banned.
