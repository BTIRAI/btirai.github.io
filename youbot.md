# Tutorial for Youbot Example
Here you will find the instructions to run the Youboy example of [Chapter 2](). You will be able to design the AI of the robot designing your own Behavior Tree (BT) via a Graphical User Interface (GUI).

![scenario_youbot](https://user-images.githubusercontent.com/8132627/42953697-49d08736-8b7b-11e8-81e4-6bdb39328743.png)

Below you can find the instructions according to your operating system.

## Installation in Windows
------------
1) Install Dependencies:

- Download and install [Cmake for Windows](https://cmake.org/download/) <br/>
- Download and install [QT5 for Windows](https://www.qt.io/download-qt-for-application-development) (the open source version is free)  <br/>
- Download and install [python3 for Windows](http://docs.python-guide.org/en/latest/starting/install3/win/)<br/>
- Download [vrep **preferably version 3.2.3**](http://www.coppeliarobotics.com/previousversions.html)

2) Download the repository:

`git clone https://github.com/btirai/youbot.git`

3) Build the Software:

Run CMake, set the project (youbot) root folder and the desired build folder (your choice). Configure and generate project solution for your favorite IDE (e.g. Visual Studio 13). Then open the solution from your IDE and build the project.


## Run in Windows
------------

- Open the folder where you downloaded V-REP and open vrep.exe
- Open the folder where you builded the code of the repository amd open youbot_behavior_tree_editor.exe.


## Installation in Unix
------------
1) Install Dependencies:

- Type in a terminal `sudo apt-get install build-essential libgl1-mesa-dev python3-tk qtdeclarative5-dev`
- Download and extract [vrep **version 3.2.3**](http://www.coppeliarobotics.com/previousversions.html)


2) Download the repository:

`git clone https://github.com/btirai/youbot.git`

3) Build the Software:

Run in a terminal the following commands:

`cd youbot` <br/>
`mkdir build` <br/>
`cd build` <br/>
`cmake ..` <br/>
`make`

## Run in Unix
------------

- Open a terminal, go to the vrep directory extracted. Run the following command

`sh vrep.sh`


- Open another terminal, go to the build folder of youbot and run the following command.

`./youbot_behavior_tree_editor`



## Verify your installation
------------
- In V-REP: File->Open Scene <br/>
- Select the file youbot_simple_example.ttt  <br/>
- A scene should appear, as in the picture below:  <br/>

![vrepyoubot](https://user-images.githubusercontent.com/8132627/43214064-7f252b96-9038-11e8-957e-4d7c80be3f75.png)

- In the BT editor: File->Load  <br/>
-  Browse in the folder youbot (the one you retrieved in step 2)  <br/>
-vSelect the file youbot_simple_exampleBT.xml  <br/>
- A BT should appear in the editor, as in the picture below: <br/>

![editorbtexample](https://user-images.githubusercontent.com/8132627/43214063-7f01a3a6-9038-11e8-9dd1-a01efe98f74e.png)

- Press the Play <img src="https://user-images.githubusercontent.com/8132627/38174387-df1de3a6-35cc-11e8-9a4f-c3ff40bffe83.png" width="15" height="15"> icon. <br/>
- Enjoy


## Create your own Behavior Tree
------------

Right Click in the editor to add a node. 

Leaf nodes have a text field to fill. You can fill in either an object's name or a location name.
The nodes have the following meanings:

|Name| Type|Description|
|---|---|---|
|IsRobotCloseTo (Object)|Condition| Returns Success if the robot is close to the object defined in the text field is close to the robot (closer than 0.2 m).
|IsObjectGrasped (Object) |Condition| Returns Success if the object defined in the text field is grasped.
|IsObjectAt (Object, Location)|Condition| Returns Success if the object is at location (e.g. **IsObjectAt (greenCube, goalLocation)**).
|IsPathToObjectCollisionFree (Object)|Condition| Returns Success if the robot is close to the object defined in the text field.
|MoveCloseTo (Object/location)|Action| Moves the robot close to the object/location defined in the text field.
|GraspObject (Object)|Action| Grasps the object defined in the text field.
|PutInFront(Object)|Action| Drops the currently grasped object.
|PutAside(Object)|Action| Place on the side the currently grasped object.

Example of available objects are:
* greenCube
* yellowCube
* blueCube

Example of available locations are:
* goalLocation
* location1
* location2
* location3

You can add new objects in the scene in VREP, make sure you put in the text field in the BT the name as it appears in the VREP's Scene Hierarchy (on the left)

- Press the Play <img src="https://user-images.githubusercontent.com/8132627/38174387-df1de3a6-35cc-11e8-9a4f-c3ff40bffe83.png" width="15" height="15"> icon. <br/>
- Enjoy
NOTE: A BT must have the root node. It cannot have loose nodes (non-connected nodes).
