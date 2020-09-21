---
id: fresponze_hardware_restart_default
title: IAudioHardware::Restart()
---

The `Restart()` method 

## Syntax 
```cpp
bool Restart(fr_i32 DeviceType, fr_f32 DelayTime);
```

## Parameters
* DeviceType - see `ETypeEndpoint` enum for more information
* DelayTime - buffer frame size in milliseconds

## Return
* false - function failed.
* true - function succeded

## Remarks
The 'Restart' method 
