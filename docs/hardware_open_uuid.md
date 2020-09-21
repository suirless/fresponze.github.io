---
id: fresponze_hardware_open_uuid
title: IAudioHardware::Open()
---

The `Open()` method 

## Syntax 
```cpp
bool Open(fr_i32 DeviceType, fr_f32 DelayTime, char* pUUID);
```

## Parameters
* DeviceType - see `ETypeEndpoint` enum for more information
* DelayTime - buffer frame size in milliseconds
* pUUID - GUID of device

## Return
* false - function failed.
* true - function succeded

## Remarks
The 'Open' method 
