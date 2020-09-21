---
id: fresponze_hardware_open_idx
title: IAudioHardware::Open()
---

The `Open()` method 

## Syntax 
```cpp
bool Open(fr_i32 DeviceType, fr_f32 DelayTime, fr_i32 DeviceId);
```

## Parameters
* DeviceType - see `ETypeEndpoint` enum for more information
* DelayTime - buffer frame size in milliseconds
* DeviceId - Index of device to choose

## Return
* false - function failed.
* true - function succeded

## Remarks
The 'Open' method 
