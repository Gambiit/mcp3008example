# A mcp3008 node-red flow on a raspberry pi board

It's an example of how to use the node-red mcp3008 node.

## The electronic hack

A simple loadcell with a INA125 amplifier and the mcp3008, some resistances and capacitors.  
  
[kicad](./images/loadcell.svg)
  

## node configuration

set the node : CEO or CE1 mcp3008 slave, 0..8 single channel or 0..4 diff channel, intervall of polling in ms, ...ready to use!  
  
[nodered](./images/flownode-red.png)
  

## Websocket to export data and send command from and to the web

msg.payload=start | stop to start | stop the flow. Data are exported by the websocket. Commands could send by the same way.  
Specifies the IP address of raspberry pi in the *index.html*.  
```html
...  

var server = 'nodejsonraspgps'; // the FQDN or IP adress of your rapsberry
var topics = {};
var wsUriC = "ws://"+server+":1880/admin/ws/example";
var ws;

function wsConnectC() {
...  
```
  
Open the *index.html* page in your favorite browser  
  
[graph1](./images/acquisitionloadcell.png)
  

## Noise reduction

The signal is filtered by three examples of numeric filter.  
  
[graph2](./images/acquisitionfront.png)
  



