# Linux commands

## Kill Processes

`pkill [processname]`  
or  
`kill [signalValue] [pid]`

|Signal Name | Signal Value | Behaviour |
|SIGHUP| 1| Hangup|
|SIGKILL| 9| Kill Signal|
|SIGTERM| 15| Terminate|

## Get process pid  

`top | grep [processname]`