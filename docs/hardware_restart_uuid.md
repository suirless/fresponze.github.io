---
id: fresponze_hardware_restart_uuid
title: IAudioHardware::Restart()
---

The `Restart()` method 

## Syntax 
```cpp
bool Restart(fr_i32 DeviceType, fr_f32 DelayTime, char* pUUID);
```

## Parameters
* DeviceType - see `ETypeEndpoint` enum for more information
* DelayTime - buffer frame size in milliseconds
* pUUID - GUID of device

## Return
* false - function failed.
* true - function succeded

## Remarks
The 'Restart' method 
