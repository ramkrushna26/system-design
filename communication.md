## Communication

### components of the system communicates with
* client-server
* client-client (P2P)
* inter-service communication
* intra-service communication
* inter-process communication
* intra-process communication

</br>

### usual communication
![image](https://github.com/ramkrushna26/system-design/assets/45620457/d68d50cd-4e14-47ab-abeb-ec26f1e37b95)

#### client
* channel is open
* optional timeout

#### server
* fulfills requests
* resources of server used

### Short Polling (bad idea)
* client keep bugging the data every seconds (periodic)
* lot of empty responces and waste of network IO
* ex: crickinfo -- score update --- repeatadly makes calls to server for any change

### Long Pulling 
* connection is open until there is responce
* no empty responce

### Web sockets
* server pro-actively sends responce to client
* bi-directional channel kept open --- much expensive than long polling

* use cases: live audiance chat, real time transfer, 












