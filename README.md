# RiftDrone_Convert

Background Summary and Introduction:

   The “Virtual Reality Drone Control” is aimed to provide a new, modern method of system
control to drones, UAVs, and any other device. This system will be using the HTC Vive virtual
reality platform that contains a virtual reality headset, two handheld controller devices, and two
infrared “light house” tracking devices. These controllers are tracked by the infrared light houses
and the orientation data can be received to the PC by accessing the device’s API. By doing so,
this will enable the ability to attain the full coordinates of the devices for implementation into the
drone control.

Unity3D Game Engine Software:

   The Unity3D Game Engine will be the main source of streaming the video feed from the
drone to the PC workstation. To use the AR.Drone 2.0 with the Unity3D software, the original
AR.Drone software development kit from Parrot had to be reconfigured to be usable in a
C#/.NET and Monobehavior environment. This was originally accomplished by github user
Ruslan-B who was able to develop working controlling libraries for the AR.Drone 2.0. The
libraries used in this package were still not enough for the purposes of the VR Drone Control
project, as many of the functions that are called in these libraries required actions from .dll files
that were incompatible with Unity3D, as Ruslan-B’s build targeted use in .NET 4.0 builds
whereas Unity3D can only handle .NET 3.5 functionality. These complications were further
refined by github user scopus777 with his modifications to Ruslan-B’s AR.Drone C# Framework
as well as where to find the Task Parallel Libraries necessary for getting the Unity3D software to
function for .NET 3.5. This project was tested in Windows 10 64-bit OS using Unity3D 5.5.5.

   While the user is wearing the HTC Vive head mounted device, the downward "nod" head gesture will cause the 
AR.Drone 2.0 to enter autopilot and hover at a height of 1m. To turn the drone to the left (negative yaw input)
the pilot must turn their head to the left. To turn the drone to the right (positive yaw input)
the pilot must turn their head to the right. Initiating the downward "nod" gesture while the drone is midflight 
will prompt the drone to land.

Video demonstration available at: https://youtu.be/tMW3fa1locU

Requirements:
Ar.Drone 2.0
HTC Vive
Unity 3D (Version: 5.5.5 32-bit)


Used libraries:

Ruslan-B/AR.Drone C# Framework --

A C# Framework to control the AR.Drone. Originally this framework was made for .NET 4.0. Thanks to the work of scopus777 changes were made to make it possible to run the framework with .NET 3.5, because Unity only supports .NET up to the version 3.5. All needed files are contained in the script folder.

Task Parallel Library for .NET 3.5 --

The AR.Drone framework uses some threading class which are not available in .NET 3.5. That’s why this library is necessary.

Ruslan-B/FFmpeg.AutoGen --

A C# Wrapper for FFmpeg. This is needed to decode the video packets of the AR.Drone. You will need to place these .dll files into the unity editor directory if you want to test the game in the editor. After building the project, you have to put the .dll's in the directory of the produced .exe to work correctly. You can find the FFmpeg DLLs in "Assets\Plugins\x86\FFmpeg".

SteamVR Plugin for Unity --

This Plugin is needed to integrate the HTC Vive. Download the plugin directly from the Asset store within the Unity3D game engine software.

Cockpit of the FA-38 3D-Model --

Digital asset created and provided by ysup12

License:

GNU Lesser General Public License (LGPL) version 3 or later.
http://www.gnu.org/licenses/lgpl.html
