# RVIZ PLUGIN SARA SHIELD
This plugin can be used to visualize the sara-shield status in RVIZ and send sara shield commands
![image](https://github.com/TUM-CONCERT/rviz_plugin_sara_shield/assets/120781514/d3cfffd5-17ce-4ef0-b243-c4a2aa5d8e1d)

The current joint values are shown in the first row. 
The goal joint pos has 6 input fields to enable setting the desired position of the robot. After `Send Goal Pos` is pressed, the numbers from the input fields are sent as a ros message. 
It also enables sending 4 different flags:
* The flag "No Human in Scene" tells sara-shield that it can forget about the last human measurement. Otherwise sara-shield could assume that there is a human still in the scene, just not observable at the moment, so the uncertainty grows over time
* `Force safe` and `Force unsafe` puts sara shield into the safe or unsafe mode, respectively.
* `Send Dummy Human` sends human measurements of a static human, for debugging purposes.   

## Dependencies:
- CONCERT: None
- Other: Qt

## Installation
Install this project just like any other ros packages
1. Clone it into `catkin_ws/src` using `https://github.com/TUM-CONCERT/rviz_plugin_sara_shield.git`
2. Build the environment using `catkin build`
3. Source the environment using `source devel/setup.bash`

## Usage
* within RVIZ, in the top menu, go to ```Panels``` then ```Add New Panel``` and select ```SaraShieldPanel```
![image](https://github.com/TUM-CONCERT/rviz_plugin_sara_shield/assets/120781514/3fdf1359-65d3-4b3b-b661-99818a9d3ddf)


## Future Improvements
* make the topics changable in the left panel
* let the number of joints adapt to the incoming message (e.g. usefull when using 7 joints)
