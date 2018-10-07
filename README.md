# CozmoCommander
Use the Anki Cozmo robot with a GUI. Uses Python with TkInter.

I am new to Cozmo, new to GUI programming and still new to Python. 
So this project is definitely not programmed in the most efficient or most elegant way. 
At the beginning I only wanted to find out how the world coordinate system works. 
By and by, the program got bigger and it is still growing. The "todo" grows faster that the "done" list. 

What it does:
*************
CozmoCommander opens a Graphical User Interface (GUI) with optional viewers provided by the Cozmo SDK. 
You can control the Cozmo robot and its interaction with lightcubes and other objects. 
You can open a 2D map where the position of the robot is tracked and other objects are shown. 

Acknowledgements, license and liability:
****************************************
I thank Anki for providing the Cozmo, the SDK and the very useful tutorials. 
I thank Grinning Hermit for providing the Cozmo Explorer Tool which was a great source of inspiration. 
I thank all who provide great tutorials on Python and TkInter

Licensed under the Apache License, Version 2.0 (the "License");
you may not use this file except in compliance with the License.
You may obtain a copy of the License in the file LICENSE.txt or at

    http://www.apache.org/licenses/LICENSE-2.0

Unless required by applicable law or agreed to in writing, software
distributed under the License is distributed on an "AS IS" BASIS,
WITHOUT WARRANTIES OR CONDITIONS OF ANY KIND, either express or implied.
See the License for the specific language governing permissions and
limitations under the License.

This applies especially but not limited to damages of the robot 
and damages or injuries caused by the robot. 

Prerequisites:
**************
* You need a Cozmo robot, 
* an Android (or IOS?) device connected to the computer via USB.
* the Cozmo App,
* a computer running Linux (Ubuntu) or Windows,
* Python3,
* Cozmo SDK and other Python modules as requested,   
* Optionally: freeglut to use the 3D viewer.

Refer to the SDK documentation for setting up your device
https://developer.anki.com/blog/learn/tutorial/getting-started-with-the-cozmo-sdk/

How to start CozmoCommander:
****************************
* Connect your device to the Cozmo via WiFi and to the computer via USB cable. 
* On the device, start the Cozmo App, connect to Cozmo and enter SDK mode. 
* Place Cozmo on the charger (again). 

From the command line (Linux and Windows), enter 
python3 [path to CozmoCommander]CozmoCommander.py [--arguments]
or under Linux 
./CozmoCommander.py [--arguments]

Arguments: 
--help  ... A short description 
--viewer=xx ... xx=0 = no viewer (default), 1 = Camera, 2 = 3D, 3 = Camera+3D

CozmoCommander should start without sending error messages to the console, 
the GUI should appear 
and Cozmo should move a few millimeters forward. 

How to use CozmoCommander:
**************************
The GUI is divided into three frames called "Motion", "Cubes" and "Faces". 
Below these frames there is the bottom section and a status line. 

The Motion Frame:
First you will notice four buttons called "Forward", "Backward", "Left" and "Right". 
"Forward" and "Backward" move Cozmo in a straight line, "Left" and "Right" make him turn in place. 

The distance and angle by which Cozmo is moved can be entered in the entry fields above. 

Below the motion buttons there are sliders to control the head and the lift. 
Adjust the sliders and click the buttons above the sliders to move head or lift. 

Below the sliders there are three buttons: 
* "Map"  ... opens the 2d map, see below. 
* "Stop" ... Stop all motions
* "Play" ... Start or stop freeplay behaviors 

The Cube Frame: 
The lightcubes show red or green LEDs indicating whether they are visible to the robot (green) or not (red). 
Lightcube 1 shows 1 LED, lightcube 2 shows 2 LEDs and lightcube 3 shows 3 LEDs. 

On the Cube frame there are three buttons, indicating the three cubes. 
Note that the Id's of the cubes are not necessarily consecuteve. 
The buttons turn red or green to indicate whether a cube is visible to the robot. 
Click one of these buttons to select a cube for the following actions. 
You may select a cube which is not visible. 

Buttons for actions are:
* "Go To" ... Go near the selected cube, the distance can be adjusted with the slider right of the button. 
* "Dock"  ... Dock to the selected cube, the angle can be adjusted with the slider right of the button.
* "Lift"  ... dock and lift up the selected cube.
* "put on top" ... puts a previously lifted cube on top of the selected one. 
* "roll" ... roll the selected cube. 

On the bottom of the Cube frame, the coordinates of the selected cube are displayed. 

The Faces frame: 
is not yet implemented. 

The bottom area:
A menu lets you choose an animation which is played immediately after selecting it. 
The adjacent button "repeat" will play the previously selected animation again. 

A text element lets you enter a text which Cozmo will say when you click the "say" button. 

The status line is not yet implemented. 

The 2D map:
When you click the "map" button in the "motion" frame, a separate window is opened. 
The map shows coordinate axes with ticks every 100 mm. 
Cozmo's location is shown as a black dot. When Cozmo moves, the dot moves and its motion is traced with a line. 

A double-click on the map sends Cozmo to the spot where you clicked. 

The cubes are shown as little squares (they are not rotated to reflect the rotation angle of the cubes). 
The selected cube has a wider border, and the cubes are filled red or green according whether tey are visible or not. 

Clicking and dragging creates a "custom object" which is shaped like a wall and which Cozmo will avoid when calculating paths. 





