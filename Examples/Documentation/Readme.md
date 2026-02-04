**DOCUMENTATION**
===

`ZigaLibs` libraries overview, examples and overall documentation. This document servers as a user guide how to use these libraries, what references (other libraries) are required when using the libraries and any warnings that might be required when using certain functionalities.

---

The libraries and their underlying objects:

* `ZigaLibs.Core` ![](Folder.png)
  * **Array** ![](Folder.png)
    * [`ArrayHelper`](#arrayhelper) - **Program** ![alt](Program.png)
    * `ST_ArrayProperties` - **Structure** ![](Structure.png)
    * `T_ArrayIndexer` - **Alias** ![](Enum.png)
  * **Beckhoff** ![](Folder.png)
    * **Ads** ![](Folder.png)
      * `AdsHelper `- **Program** ![alt](Program.png)
      * `FB_HasAmsAddressFromProcessImage `- **Function Block** ![alt](Program.png)
      * `I_HasAmsAddress `- **Interface** ![alt](Interface.png)
    * **EtherCAT** ![](Folder.png)
      * **CoE** ![](Folder.png)
        * `ST_CoeEntry `- **Structure** ![](Structure.png)
        * `ST_CoeEntry_DINT` - **Structure** ![](Structure.png)
        * `ST_CoeEntry_SINT` - **Structure** ![](Structure.png)
        * `ST_CoeEntry_String128` - **Structure** ![](Structure.png)
        * `ST_CoeEntry_UDINT` - **Structure** ![](Structure.png)
        * `ST_CoeEntry_INT` - **Structure** ![](Structure.png)
        * `ST_CoeEntry_REAL` - **Structure** ![](Structure.png)
        * `ST_CoeEntry_String255` - **Structure** ![](Structure.png)
        * `ST_CoeEntry_String30` - **Structure** ![](Structure.png)
        * `ST_CoeEntry_UINT` - **Structure** ![](Structure.png)
        * `ST_CoeEntry_USINT` - **Structure** ![](Structure.png)
        * `T_CoEIndex` - **Alias**
        * `T_CoESubIndex` - **Alias**
        * `FB_CoeReadWrite` - **Function Block** ![alt](Program.png)
        * `I_ReadsCoE` - **Interface**
        * `EthercatHelper` - **Program** ![alt](Program.png)
        * `FB_ReadBoxName` - **Function Block** ![alt](Program.png)
  * *Errors*![](Folder.png)
    * `ST_AdsError` - **Structure** ![](Structure.png)
    * `ST_Error` - **Structure** ![](Structure.png)
    * `ST_GenericError ` - **Structure** ![](Structure.png)
    * `FB_ErrorSource` - **Function Block** ![alt](Program.png)
    * `I_ErrorSource` - **Interface** ![alt](Interface.png)
    * `I_HasAdsError` - **Interface** ![alt](Interface.png)
    * `I_HasError` - **Interface** ![alt](Interface.png)
    * `I_HasGenericError` - **Interface** ![alt](Interface.png)
  * *General*![](Folder.png)
    * `FB_Collection` - **Function Block** ![alt](Program.png)
    * `I_Collection` - **Interface** ![alt](Interface.png)
  * *Memory*![](Folder.png)
    * `E_MemCmpResults` - **Enum** ![](Enum.png)
    * `FB_Malloc` - **Function Block** ![alt](Program.png)
    * `MemoryHelper` - **Program**
    * `ST_AllocatedMemoryProperties` - **Structure** ![](Structure.png)
  * *Variable extensions*![](Folder.png)
    * `BoolEx` - **Function Block** ![alt](Program.png)
  * *Variable information*![](Folder.png)
    * `FB_BooleanObserver` - **Function Block** ![alt](Program.png)
    * `FB_HasInstanceNameAndPath` - **Function Block** ![alt](Program.png)
    * `FB_HasTaskInfo` - **Function Block** ![alt](Program.png)
    * `FB_Watchdog` - **Function Block** ![alt](Program.png)
    * `InstanceNameHelper` - **Program** ![alt](Program.png)
    * `ST_Value` - **Structure** ![](Structure.png)
  * *String*![](Folder.png)
    * *String Builder*![](Folder.png)
      * `FB_StringBuilder` - **Function Block** ![alt](Program.png)
      * `I_StringBuilder` - **Interface** ![alt](Interface.png)
    * `StringConstants` - **Program** ![alt](Program.png)
    * `T_Char` - **Alias**
  * *Time*![](Folder.png)
    * `E_TimeFormat` - **Enum** ![](Enum.png)
    * `ST_CurrentSystemTimeInfo` - **Structure** ![](Structure.png)
    * `FB_DateTimeToStringConverter` - **Function Block** ![alt](Program.png)
    * `FB_LocalSystemTimeProvider` - **Function Block** ![alt](Program.png)
    * `I_DateTimeToStringConverter` - **Interface** ![alt](Interface.png)
    * `I_LocalSystemTimeProvider` - **Interface** ![alt](Interface.png)
    * 

# ArrayHelper ![](Program.png)

Provides array helper methods for easier work with arrays accross programming.

## Methods ![alt](MethodIcon.png)

- [`Clear`](#clear)

---

### *`Clear()`*
```
METHOD PUBLIC Clear : BOOL
VAR_INPUT
	arr			: ANY;	// Array to be cleared
END_VAR
```
*Clears the entire array. Returns `TRUE` if operation was sucessfull.*

**Inputs** ![](MethodInputs.png)  
|Name|Type|Description|
|---|---|---|
|**arr**|`ANY`|array to be cleared|

**Returns** ![](MethodOutputs.png)  
|Type|Description|
|---|---|
|`BOOL`|Returns `TRUE` *if the operation was sucessfull.*|


**Example**

```
VAR
	arr	: ARRAY[0..20] OF BOOL;
	idx : T_ArrayIndexer;
END_VAR
```
```
FOR idx := 0 TO 20 BY 1 DO
	arrModified[idx] := TRUE;
END_FOR

// At this point, all the array elements are TRUE

ArrayHelper.Clear(arr);

// Every element in the array is FALSE
```
