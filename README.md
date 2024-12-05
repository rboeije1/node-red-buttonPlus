# node-red-buttonPlus
The buttonPlus or Button+ or B+ is a user interface to a domotica system. The hardware is software independant, while the official firmware uses the MQTT protocol over wifi to communicate with the outer world.
The base configuration has a color display and two tactile buttons and can be extenden with 1 to three 'button bars', each having two buttons and a small color display.
So in total a maximum of 8 buttons can be configured.
The built-in firmware has a web interface to configure every element of the device, but that is quite cumbersome.
The code presented here is designed to be used by node-red driven systems, but even if you use any other environment, you can only use the initilasation part to quickly change the layout and upload to the B+. 

Initially Based on node-red flow of @balk77 (https://github.com/balk77/node-red-buttonplus-menu/tree/buttons-mqtt-update)

This code is a further development of the old/initial code that was based on the work of Balk77. That development has stopped, and this is a completely revised version. There are still some legacy elements that need work, but at least is is usable as a base for development of your own button plus configuration.

The basic idea is that you don't need to enter topics in the web interface of the buttonplus. You edit the initial config and upload it. The only thing you have to do before uploading is setting the wifi iconnection. (As that is saved after a factory reset, you only need to do that once.)

Most parts are prepared for multiple Button Plus devices, but some code is not (yet). 
It is important to read the comments in the source files to understand the logic.

The configuration is stored in the global storage on disk, so is saved across reboots. If you have more than one B+, you can just copy the 3 functions for every B+, however, not everything is ready to separate the logic, work in progress on this. (In fact I simplified something in a way that it breaks the independant logic. The configuration of the B+ itself is completely separated.)

In the example configuration it has 5 pages and 3 button bars, but you can easily change the page content and the number of button bars.

There is no thermostat built in this code, but there is a button that controls a thermostat in three states (On, Off and Auto) and two buttons in increase and decrease the temperature. It is up to you to take action on the changed variables.

![image](https://github.com/user-attachments/assets/e1be9b0d-88f7-4226-98e0-5b42efda567d)
