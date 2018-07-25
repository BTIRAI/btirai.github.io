
<style>
.tablelines table, .tablelines td, .tablelines th {
        border: 1px solid black;
        }
</style>

# Tutorial for Pac-Man Example
Here you will find the instructions to run the Pac-Man example of [Chapter 2](https://www.researchgate.net/publication/319463746_Behavior_Trees_in_Robotics_and_AI_An_Introduction). You will be able to design the AI of the Pac-Man game designing your own Behavior Tree (BT) via a Graphical User Interface (GUI).

![scenario_pacman](https://user-images.githubusercontent.com/8132627/38174301-537686d8-35cb-11e8-8e6d-4b82c8901376.png)

Below you can find the instructions according to your operating system.

## Installation in Windows
------------
1) Install Dependencies:

- Download and install [Cmake for Windows](https://cmake.org/download/) <br/>
- Download and install [QT5 for Windows](https://www.qt.io/download-qt-for-application-development) (the open source version is free)  <br/>
- Download and install [python3 for Windows](http://docs.python-guide.org/en/latest/starting/install3/win/)<br/>
2) Download the repository:

`git clone https://github.com/miccol/pacmanBT.git`

3) Build the Software:

Run Cmake, set the project (pacman) root folder and the desired build folder (your choice). Configure and generate project solution for your favorite IDE (e.g. Visual Studio 13). Then open the solution from your IDE and build the project.


## Run in Windows
------------

In a terminal, go to the build directory of the project and then run the following commands:

`./behavior_tree_editor.exe`

Alternatively, run the executable pacman_behavior_tree_editor.exe from File Explorer



## Installation in Unix
------------
1) Install Dependencies:

`sudo apt-get install build-essential libgl1-mesa-dev python3-tk qtdeclarative5-dev`

2) Download the repository:

`git clone https://github.com/btirai/pacman.git`

3) Build the Software:

Run in a terminal the following commands:

`cd pacmanBT` <br/>
`mkdir build` <br/>
`cd build` <br/>
`cmake ..` <br/>
`make`

## Run in Unix
------------

Run in a terminal the following commands:

`cd bt_editor`

`./behavior_tree_editor`







## Verify your installation
------------
- In the BT editor: File->Load  <br/>
- Browse in the folder pacmanBT (the one you retrieved in step 2)  <br/>
- Select the file pacmantree.xml  <br/>
- A BT should appear in the editor, as in the picture below: <br/>

![screenwindows](https://user-images.githubusercontent.com/8132627/38174356-7277665a-35cc-11e8-8fd3-99feb36598e1.jpg)




- Press the Play <img src="https://user-images.githubusercontent.com/8132627/38174387-df1de3a6-35cc-11e8-9a4f-c3ff40bffe83.png" width="15" height="15"> icon. <br/>
- Enjoy



# Create your own Behavior Tree
------------

Right Click in the editor to add a node. 
The nodes have the following meanings:

|Name| Type|Description|
|---|---|---|
|IsGhostClose|Condition| Returns Success if the a ghost is close. Failure otherwise.
|IsClosestGhostScared|Condition| Returns Success if the the closes ghost is scared. Failure otherwise.
|Greedy|Action| Moves to the next position that has a pill.
|ClosestDotSearch|Action| Moves in the direction of the closest pill.
|Chase|Action| Moves in the direction of the closest ghost.
|KeepDistance|Action| Moves to a position that maximize the distance with the ghosts.
|Escape|Action| Moves to a position that maximize the distance with the closest ghost.


- Press Play to run the BT
- Enjoy

**NOTE: A BT must have the root node. It cannot have loose nodes (non-connected nodes).**



