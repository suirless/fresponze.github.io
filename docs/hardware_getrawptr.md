---
id: fresponze_hardware_getrawptr
title: IAudioHardware::GetRawPtr()
---

The `GetRawPtr()` method 

## Syntax 
```cpp
void GetRawPtr(fr_i32 DeviceType, void*& OutPtr);
```

## Parameters
* DeviceType - see `ETypeEndpoint` enum for more information
* OutPtr - raw pointer to device (depended on hardware type)

## Return
No return value.

## Remarks
The 'GetRawPtr' method 
