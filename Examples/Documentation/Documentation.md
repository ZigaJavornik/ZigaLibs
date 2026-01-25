`ZigaLibs` libraries overview, examples and overall documentation. This document servers as a user guide how to use these libraries, what references (other libraries) are required when using the libraries and any warnings that might be required when using certain functionalities.

The libraries and their underlying objects:

* `ZigaLibs.Core`
  * *Array*
    * `ArrayHelper` - **Program**
    * `ST_ArrayProperties` - **Structure**
    * `T_ArrayIndexer` - **Alias**
  * *Beckhoff*
    * *Ads*
      * `AdsHelper `- **Program**
      * `FB_HasAmsAddressFromProcessImage `- **Function Block**
      * `I_HasAmsAddress `- **Interface**
    * *EtherCAT*
      * *CoE*
        * `ST_CoeEntry `- **Structure**
        * `ST_CoeEntry_DINT` - **Structure**
        * `ST_CoeEntry_SINT` - **Structure**
        * `ST_CoeEntry_String128` - **Structure**
        * `ST_CoeEntry_UDINT` - **Structure**
        * `ST_CoeEntry_INT` - **Structure**
        * `ST_CoeEntry_REAL` - **Structure**
        * `ST_CoeEntry_String255` - **Structure**
        * `ST_CoeEntry_String30` - **Structure**
        * `ST_CoeEntry_UINT` - **Structure**
        * `ST_CoeEntry_USINT` - **Structure**
        * `T_CoEIndex` - **Alias**
        * `T_CoESubIndex` - **Alias**
        * `FB_CoeReadWrite` - **Function Block**
        * `I_ReadsCoE` - **Interface**
        * `EthercatHelper` - **Program**
        * `FB_ReadBoxName` - **Function Block**
  * *Errors*
    * `ST_AdsError` - **Structure**
    * `ST_Error` - **Structure**
    * `ST_GenericError ` - **Structure**
    * `FB_ErrorSource` - **Function Block**
    * `I_ErrorSource` - **Interface**
    * `I_HasAdsError` - **Interface**
    * `I_HasError` - **Interface**
    * `I_HasGenericError` - **Interface**
  * *General*
    * `FB_Collection` - **Function Block**
    * `I_Collection` - **Interface**
  * *Memory*
    * `E_MemCmpResults` - **Enum**
    * `FB_Malloc` - **Function Block**
    * `MemoryHelper` - **Program**
    * `ST_AllocatedMemoryProperties` - **Structure**
  * *Variable extensions*
    * `BoolEx` - **Function Block**
  * *Variable information*
    * `FB_BooleanObserver` - **Function Block**
    * `FB_HasInstanceNameAndPath` - **Function Block**
    * `FB_HasTaskInfo` - **Function Block**
    * `FB_Watchdog` - **Function Block**
    * `InstanceNameHelper` - **Program**
    * `ST_Value` - **Structure**
  * *String*
    * *String Builder*
      * `FB_StringBuilder` - **Function Block**
      * `I_StringBuilder` - **Interface**
    * `StringConstants` - **Program**
    * `T_Char` - **Alias**
  * *Time*
    * `E_TimeFormat` - **Enum**
    * `ST_CurrentSystemTimeInfo` - **Structure**
    * `FB_DateTimeToStringConverter` - **Function Block**
    * `FB_LocalSystemTimeProvider` - **Function Block**
    * `I_DateTimeToStringConverter` - **Interface**
    * `I_LocalSystemTimeProvider` - **Interface**
    * 

# ArrayHelper
Provides array helper methods for easier work with arrays accross programming.

## Methods

```iecst
METHOD PUBLIC Clear : BOOL
VAR_INPUT
	arr			: ANY;	// Array to be cleared
END_VAR
```
Clears the entire array. Returns TRUE if operation was sucessfull.

|**Inputs**|
|-|
|**arr** `ANY`|
|*Array to be cleared.*|

|**Returns**|
|-|
|`BOOL`|
|`TRUE` *if the operation was sucessfull.*|


**Example**
```iecst
VAR
	arr	: ARRAY[0..20] OF BOOL;
	idx : T_ArrayIndexer;
END_VAR
```

```st
FOR idx := 0 TO 20 BY 1 DO
	arrModified[idx] := TRUE;
END_FOR

// At this point, all the array elements are TRUE

ArrayHelper.Clear(arr);

// Every element in the array is FALSE
