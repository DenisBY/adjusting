# Adjusting

## Adjustment 1

To print the numbers from 1 to 10 in random order to the terminal the following command can be used:   
```
for i in {1..10}; do echo "$i "; done | shuf
```
It works on both Linux and macOS

## Adjustment 2

Usually I configure a monitoring of a new service or application starting from users point of view. Therefore I would start to configure the monitoring of provided example in the following order split by two layers, Application and Host.

**Application:**
1. Response Time - how fast http server responds
2. HTTP status code - if there any 5xx codes and how many

**Host:**
1. System interruptions - how many system resources are used for networking
2. Bandwith usage - to see how much of network connection is used
2. CPU usage - to see CPU usage
3. Processes running - to see if some processes are stuck 
4. The rest. Like Memory, Disk, etc.

#### Chalenges:

Monitoring of 'HTTP status code' could be triky becaus of high amount requests per second. I see several options:
1. Write to the separate log file only status code and monitor that file
2. Send status codes directly from HTTP server to the monitoring system
3. Have some script or app to filter and send only 5xx errors to the monitoring system
