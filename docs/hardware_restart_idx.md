---
id: fresponze_hardware_restart_idx
title: IAudioHardware::Restart()
---

The `Restart()` method 

## Syntax 
```cpp
bool Restart(fr_i32 DeviceType, fr_f32 DelayTime, fr_i32 DeviceId);
```

## Parameters
* DeviceType - see `ETypeEndpoint` enum for more information
* DelayTime - buffer frame size in milliseconds
* DeviceId - Index of device to choose

## Return
* false - function failed.
* true - function succeded

## Remarks
The 'Restart' method 
