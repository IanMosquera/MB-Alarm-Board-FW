
###### Sensor Reading Flow Chart
the chart below describes the program flow chart that will be run by at a desired time interval(e.g. every 10 seconds). A
```mermaid
graph LR
A([start]) --> B{dubugMode}
B{dubugMode} --> |No|D[readSensor]
B{dubugMode} --> |Yes|C([end])
D[readSensor] --> E{val <= Threshold}
E{val <= Threshold} -->|Yes|F[alarmOn]
E{val <= Threshold} -->|No|G[alarmOff]
F[alarmOn] --> D[readSensor]
G[alarmOff] --> D[ReadSensor]
```
```c++
uint32_t readSensor(uint32_t debugMode){
    ...
}
```
At the start of the process, the function will check if the

```c++
...
if(!debugMode){
    //read values from sensor
}
return 0;
```