# IoThingsLab

## Table of contents
* [General info](#general-info)
* [Technologies](#technologies)
* [Required software and hardware](#required-software-and-hardware)
* [IoT VR Platform package](#iot-vr-platform-package)
* [Setup](#setup)
* [Known issues](#known-issues)
* [Contributing to the platform](#contributing-to-the-platform)

## General info

<img align="left" width="200" src="/Readme/Files/20201030_173803.jpg">
<img align="left" width="200" src="/Readme/Files/20201030_175023.jpg">

By using VRSimulator platform researchers can connect real and virtual IoT devices, test new IoT devices inside VR environment (and don't even need to buy them!)

[:VRSimulator Webpage:](https://vrsimulator.github.io/)
	
## Technologies
Same features are supported on VR IoT Platform as on Mixed Reality Toolkit (https://github.com/microsoft/MixedRealityToolkit-Unity#feature-areas), such as hand tracking and interaction techniques. In addition to that, some extra interaction methods were added into IoT VR Platform.

<img align="right" width="200" src="/Readme/Files/20201030_175856.jpg">
<img align="right" width="200" src="/Readme/Files/20201030_180612.jpg">

Connection to real-world IoT devices is performed by REST API calls to [openHAB](https://www.openhab.org/download/) server, which runs either locally on user machine, or remotely on [myopenhab server](http://myopenhab.org/).
## Required software and hardware:
1. Unity Version 2019.4.13+
### Additional software & hardware:
1. Oculus Quest 1 or 2
2. OpenHAB (running on local or remote server)
3. IoT devices

## IoT VR Platform package
Available items (the list is frequently updated):

| [![Lamp](/Readme/Files/Lamp.png)]() [Light Item](Documentation/Things/Lamp.md) | [![Door](/Readme/Files/Door.png)]() [Door](Documentation/Things/Door.md) | [![WeightScaler](/Readme/Files/WeightScaler.png)]() [Weight Scaler](Documentation/Things/WeightScaler.md) | 
|:--- | :--- | :--- |
| A lamp thing with Location and Light items attached | A door with a door close/open sensor item attached | Weight Scaler item triggers according to the weight scaled on it |
| [![Camera](/Readme/Files/Camera.png)]() [Camera](Documentation/Things/Camera.md) | [![TV](/Readme/Files/TV.png)]() [TV](Documentation/Things/TV.md) | [![Vacuum Cleaner](/Readme/Files/VacuumCleaner.png)]() [Vacuum Cleaner](Documentation/Things/VacuumCleaner.md) |
| A camera with a motion sensor connected | A TV translating an image from the camera | A vacuum cleaner thing, which can be docked/undocked and move around the scene |


<img align="left" width="200" src="/Readme/Files/20201030_181421.jpg">
<img align="left" width="200" src="/Readme/Files/20201030_182148.jpg">

### IoT VR Package Structure 
The main part of the package is Server, where classes for the items and things are defined.

Things are Gameobjects added into Unity project which represent either a digital twin of a real IoT device or a purely virtual IoT device. Things potentially provide many functionalities in one.

Items are the parts things consist of: for example, smart light in the room can consist of several lamps and a receiver – each of them as an item.
	
Other parts of IoT VR Platform are: resources, prefabs, Thirdparty and scenes.	
	
	
## Setup

### VR (Client) part
1.1 Clone the Repo;
![](/Readme/Files/Screenshot(21).png)

1.1 Open Unity Hub; select Add; choose IoThingsLab folder; 
![](/Readme/Files/Screenshot(23).jpg)

1.3 Select Unity version 2019.4.13+ and Platform = Android; open the project;
![](/Readme/Files/Screenshot(24).png)

2. Download the following .unitypackages from the [latest releases](https://github.com/VRSimulator/IoThingsLab/releases):
* IoThingsLab-Resources-V*.unitypackage
* IoThingsLab-Thirdparty-V*.unitypackage
* IoThingsLab-Scenes-V*.unitypackage
* IoThingsLab-Prefabs-V*.unitypackage

3.1 Inside Unity Editor, navigate to Assets->Import Package->Custom Package...;
![](/Readme/Files/Screenshot(26).png)

3.2 Import the listed packages one by one;
![](/Readme/Files/Screenshot(27).png)

3.3 Note that IoThingsLab-Thirdparty-V*.unitypackage importing may take several minutes;
![](/Readme/Files/Screenshot(28).png)

4. Inside the Project window, navigate to Assets/com.tsinghua.iotvrp/Scenes and click on Client.unity scene;
![](/Readme/Files/Screenshot(29).jpg)

5. On the top of Unity Editor, select Mixed Reality Toolkit -> Utilities -> Oculus -> Integrate Oculus Integration Unity Modules;
![](/Readme/Files/Screenshot(33).png)

6. Navigate to File-Build Settings. Inside Scenes in Build, select add open scenes, make sure that only Client scene is added, right click on the other scenes and delete them. Switch build platform to Android;

7.1 To run the platform on Oculus Quest, Build and Run the project;

7.2 To run the platform on PC (Unity editor) and use [VR input simulation](#input-simulation), Click play button;
![](/Readme/Files/Screenshot(34).jpg)

8. Have a look at the example items (Tsinghua.IoTVRP->IoTPlayground->Things inside Hierarchy window). Combine your own IoT thing from the items inside Unity Editor.

9. When adding a new thing, follow the [Design rules](https://www.bilibili.com/video/BV1mK4y1f7FL?from=search&seid=2714519419091722950)

### Input simulation
[Input simulation service Documentation](https://microsoft.github.io/MixedRealityToolkit-Unity/Documentation/InputSimulation/InputSimulationService.html)

### Tutorial on the IoT part and how to run the server on the local machine
1. Install [openHAB](https://www.openhab.org/download/) and run the server.;
2. Add [REST API](https://www.openhab.org/docs/configuration/restdocs.html) binding;
3. Follow the instructions for binding your IoT device;

## Known Issues
1. If when running the platform on PC (Unity Editor) you get the following error:
![](/Readme/Files/ErrorXRSDK.png)
Then you need to do step 5 of the setup process: On the top of Unity Editor, select Mixed Reality Toolkit -> Utilities -> Oculus -> Integrate Oculus Integration Unity Modules;
![](/Readme/Files/Screenshot(33).png)

## Contributing to the platform
请分享新想法, 谢谢！
You can copy the Client Scene and test your ideas before merging the changes:) Thank you!
