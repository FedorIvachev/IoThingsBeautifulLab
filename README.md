# IoThingsLab

## Table of contents
* [General info](#general-info)
* [Technologies](#technologies)
* [Setup](#setup)
* [Contributing to the platform](#contributing-to-the-platform)

## General info
By using VRSimulator platform researchers can connect real and virtual IoT devices, test new IoT devices inside VR environment (and don't even need to buy them!)

[:VRSimulator Webpage:](https://vrsimulator.github.io/)
	
## Technologies
In the current state of development, IoT VR Platform is used as an extension to [Mixed Reality Toolkit - Quest](https://github.com/provencher/MRTK-Quest) project. 
Same features are supported on VR IoT Platform as on Mixed Reality Toolkit (https://github.com/microsoft/MixedRealityToolkit-Unity#feature-areas), such as hand tracking and interaction techniques. In addition to that, some extra interaction methods are added inside IoT VR Platform.

Available items (the list is frequently updated):

| [![Lamp](/Readme/Files/Lamp.png)]() [Light Item](Documentation/Things/Lamp.md) | [![Door](/Readme/Files/Door.png)]() [Door](Documentation/Things/Door.md) | [![WeightScaler](/Readme/Files/WeightScaler.png)]() [Weight Scaler](Documentation/Things/WeightScaler.md) | 
|:--- | :--- | :--- |
| A lamp thing with Location and Light items attached | A door with a door close/open sensor item attached | Weight Scaler item triggers according to the weight scaled on it |
| [![Camera](/Readme/Files/Camera.png)]() [Camera](Documentation/Things/Camera.md) | [![TV](/Readme/Files/TV.png)]() [TV](Documentation/Things/TV.md) | [![Vacuum Cleaner](/Readme/Files/VacuumCleaner.png)]() [Vacuum Cleaner](Documentation/Things/VacuumCleaner.md) |
| A camera with a motion sensor connected | A TV translating an image from the camera | A vacuum cleaner thing, which can be docked/undocked and move around the scene |

Connection to real-world IoT devices is performed by REST API calls to [openHAB](https://www.openhab.org/download/) server, which runs either locally on user machine, or remotely on [myopenhab server](http://myopenhab.org/).

	
## Setup

### VR (Client) part
1. Open Unity Hub; select Add; choose IoThingsLab folder; select Unity version 2019.4.13+ and Platform = Android; open the project;
2. Download the following .unitypackages from the [latest releases](https://github.com/VRSimulator/IoThingsLab/releases):
    * IoThingsLab-Resources-V*.unitypackage
    * IoThingsLab-Thirdparty-V*.unitypackage
    * IoThingsLab-Scenes-V*.unitypackage
    * IoThingsLab-Prefabs-V*.unitypackage
3. Inside Unity Editor, navigate to Assets->Import Package->Custom Package..., then import the listed packages one by one. Check if Assets/iotvrp/ folder contains the added folders;
4. Inside the Project window, navigate to Assets/com.tsinghua.iotvrp/Scenes and click on Client.unity scene;
6. Navigate to File-Build Settings. Inside Scenes in Build, select add open scenes, make sure that only Client scene is added, right click on the other scenes and delete them;
7. To run the platform on Oculus Quest, change Input Profile to Oculus MixedRealityInputSystemProfile inside MixedRealityToolkit - Input, Build and Run the project;
8. To run the platform on PC and use [VR input simulation](#input-simulation), change the Input Profile to DefaultMixedRealityInputSystemProfile, Click play button;
9. Have a look at the example items. Combine your own IoT thing from the items inside Unity Editor.
10. When adding a new thing, follow the [Design rules](https://www.bilibili.com/video/BV1mK4y1f7FL?from=search&seid=2714519419091722950)

### Input simulation
[Input simulation service Documentation](https://microsoft.github.io/MixedRealityToolkit-Unity/Documentation/InputSimulation/InputSimulationService.html)

### Tutorial on the IoT part and how to run the server on the local machine
1. Install [openHAB](https://www.openhab.org/download/) and run the server.;
2. Add [REST API](https://www.openhab.org/docs/configuration/restdocs.html) binding;
3. Follow the instructions for binding your IoT device;

## Contributing to the platform
请分享新想法, 谢谢！
You can copy the Client Scene and test your ideas before merging the changes:) Thank you!
