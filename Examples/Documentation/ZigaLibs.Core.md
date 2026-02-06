`ZigaLibs.Core` objects can be found in this part of the documentation. This library contains core functionalities without targeting anything specific. Other libraries have a high chance of referencing this library so make sure to install it in order to be able to use them.

**EXTERNAL REFERENCES**
|Name|Effective/Newest|Namespace|Effective version|Required|
|---|---|---|---|---|
|BaseInterfaces|Newest|IBaseLibrary|3.5.2.0|YES|
|Tc2_EtherCAT|Newest|Tc2_EtherCAT|3.5.1.0|YES|
|Tc2_IoFunctions|Newest|Tc2_IoFunctions|3.4.5.0|YES|
|Tc2_Standard|Newest|Tc2_Standard|3.4.5.0|YES|
|Tc2_System|Newest|Tc2_System|3.6.4.0|YES|
|Tc2_Utilities|Newest|Tc2_Utilities|3.9.2.0|YES|
|Tc3_Module|Newest|Tc3_Module|3.4.5.0|YES|
|[TcError](https://github.com/Roald87/TcError/releases/tag/v0.2.2)|Effective|TcError|0.2.2.0|YES|
|[TcUnit](https://github.com/tcunit/TcUnit/releases/tag/1.3.0.0)|Effective|TcUnit|1.3.0.0|NO|

---

  * **Array** ![](Folder.png)
    * [`ArrayHelper`](#arrayhelper) - **Program** ![alt](Program.png)
    * [`ST_ArrayProperties`](#st_arrayproperties) - **Structure** ![](Structure.png)
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


---
 # ArrayHelper

A helper program (class) that provides array helper methods for easier work with arrays accross programming.

[test](NewMarkdownFile.md)

## Methods ![alt](MethodIcon.png)

  - [*`Clear()`*](#clear)
  - [*`DoesArrayContainItem()`*](#doesarraycontainitem)
  - [*`FindLastOccupiedItem()`*](#findlastoccupieditem)
  - [*`GetElementCount()`*](#getelementcount)
  - [*`GetMaxIndex()`*](#getmaxindex)
  - [*`InsertAtStart()`*](#insertatstart)
  - [*`SetAtFirstEmptySlot()`*](#setatfirstemptyslot)
  - [*`ShiftDown()`*](#shiftdown)
  - [*`ShiftUp()`*](#shiftup)

---

### *`Clear()`*
```
METHOD PUBLIC Clear : BOOL
VAR_INPUT
    arr			: ANY;	// Array to be cleared
END_VAR
```
>*Clears the entire array. Returns `TRUE` if operation was sucessfull.*

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

---

### *`DoesArrayContainItem()`*

```
METHOD DoesArrayContainItem : BOOL
VAR_INPUT
    arr		: ANY;	// Array to be checked
    item	: ANY;	// Item to be found in the array
END_VAR
```
*Looks trough the array and returns `TRUE` if any element equals to the one provided.*

**Inputs** ![](MethodInputs.png) 

|Name|Type|Description|
|---|---|---|
|**arr**|`ANY`|*Array to be checked*|
|**item**|`ANY`|*Item to be found in the array*|

**Returns** ![](MethodOutputs.png)  

|Type|Description|
|---|---|
|`BOOL`|*Returns `TRUE` if any element equals to the one provided*|


**Example**

```
VAR
    arr		: ARRAY[0..10] OF STRING;
    item	: STRING := 'mwah';
  item2 : STRING := 'I don't exist!'
  incorrectDataType : INT;
END_VAR
```
```
// Assign some values to the array
arr[0] := '';
arr[5] := item;

// Result of this call will be TRUE - item exists
ArrayHelper.DoesArrayContainItem(arr, item);

// Result of this call will be FALSE - item does not exist
ArrayHelper.DoesArrayContainItem(arr, item2);

// Result of this call will be FALSE - incorrect data type
ArrayHelper.DoesArrayContainItem(arr, incorrectDataType);
```

---
### *`FindLastOccupiedItem()`*

```
METHOD PUBLIC FindLastOccupiedItem	: BOOL
VAR_INPUT
    arr			: ANY;	// Array to look for the last element value
    dataType	: ANY;	// Data type of the array elements, can be used like this : datayType := arr[0]
    result		: ANY;	// Result variable, result be written to this variable
END_VAR
```
  >*Looks trough the array and return the last non-zero element to the result variable. Returns `TRUE` if an element was found and `FALSE` if no empty elementsare found. Note that this method uses memmory allocation. All occupied memory is released after method finishes.*

**Inputs** ![](MethodInputs.png)

|Name|Type|Description|
|---|---|---|
|**arr**|`ANY`|*Array to look for the last element value*|
|**dataType**|`ANY`|*Data type of the array elements*|
|**result**|`ANY`|*Result variable, result be written to this variable*|

**Returns** ![](MethodOutputs.png)

|Type|Description|
|---|---|
|`BOOL`|*Returns TRUE if an element was found and FALSE if no empty elements are found*|


**Example**

```
VAR
    arr	    : ARRAY[0..10] OF INT;
    result	: int;
END_VAR
```
```
arr[5] := 5;
ArrayHelper.FindLastOccupiedItem(arr, arr[0], result);
// result's value is 5
```

---

### *`GetElementCount()`*

```
METHOD PUBLIC GetElementCount : DINT
VAR_INPUT
    arr			: ANY;	// Array to be checked.
    dataType	: ANY;	// Data type of the array elements, can be used like this : datayType := arr[0]
END_VAR

```
>*Returns the number of elements in the array*

**Inputs** ![](MethodInputs.png)

|Name|Type|Description|
|---|---|---|
|**arr**|`ANY`|*Array to be checked.*|
|**dataType**|`ANY`|*Data type of the array elements*|

**Returns** ![](MethodOutputs.png)  
|Type|Description|
|---|---|
|`DINT`|*Returns the number of elements in the array.*|


**Example**

```
VAR
    arr		: ARRAY[0..99] OF REAL;
    arr2	: ARRAY[22..33] OF REAL;
END_VAR
```
```
// Returned value will be 100
ArrayHelper.GetElementCount(arr := arr, dataType := arr[0]);

// Returned value will be 12
ArrayHelper.GetElementCount(arr := arr2, dataType := arr2[0]);

```
---

### *`GetMaxIndex()`*

```
METHOD PUBLIC GetMaxIndex : DINT
VAR_INPUT
    arr			: ANY;	// Array to be checked.
    dataType	: ANY;	// Data type of the array elements, can be used like this : datayType := arr[0]
    startIndex	: T_ArrayIndexer;
END_VAR
```
*Gets the maximum array index that can be used for looping or index accessing*

**Inputs** ![](MethodInputs.png)
|Name|Type|Description|
|---|---|---|
|**arr**|`ANY`|*Array to be checked*|
|**dataType**|`ANY`|*Data type of the array elements*|
|**startIndex**|`T_ArrayIndexer`|*Starting index of the array that will determine the return value*|

**Returns** ![](MethodOutputs.png)
|Type|Description|
|---|---|
|`DINT`|*Maximum index that can be used to access the array's elements*|


**Example**

```
VAR
    arr		: ARRAY[0..99] OF REAL;
    arr2	: ARRAY[22..33] OF REAL;
END_VAR

```

```
// Returned value will be 99
ArrayHelper.GetMaxIndex(arr := arr, dataType := arr[0], startIndex := 0);

// Returned value will be 33
ArrayHelper.GetMaxIndex(arr := arr2, dataType := arr2[0], startIndex := 22);
```
---

### *`InsertAtStart()`*

```
METHOD InsertAtStart : BOOL
VAR_INPUT	
    arr		: ANY;	// Array to be checked.
    item	: ANY;	// Item to be inserted on start
 END_VAR

```
*>Inserts the item to the start of the array. Array contents are shifted by 1, last item is deleted.*

**Inputs** ![](MethodInputs.png)
|Name|Type|Description|
|---|---|---|
|**arr**|`ANY`|*Array to be checked*|
|**item**|`ANY`|*Item to be inserted on start*|

**Returns** ![](MethodOutputs.png)
|Type|Description|
|---|---|
|`BOOL`|*Returns `TRUE` if the operation was sucessfull. Possible fails - incorrect data type (must be a reference or an array), item's data type does not match the arr data type's base type.*|


**Example**

```
VAR
    i		: INT;
    value	: STRING := '9';
    arr		: ARRAY [0..10] OF STRING;
END_VAR
```
```
FOR i := 0 TO 10 BY 1 DO
    arr[i] := INT_TO_STRING(i);
END_FOR
//['0', '1', '2', '3', '4', '5', '6', '7', '8', '9', '10']

ArrayHelper.InsertAtStart(
    arr := arr,
    item := value);
//['9', '0', '1', '2', '3', '4', '5', '6', '7', '8', '9']

```
---

### *`SetAtFirstEmptySlot()`*

```
METHOD SetAtFirstEmptySlot
VAR_INPUT
    arr		: ANY;	// Array to be checked.
    item	: ANY;	// Item to set
END_VAR
```
*>Iterates the array and sets the value when first empty slot is found. Note that this method uses memmory allocation. All occupied memory is released after method finishes.*

**Inputs** ![](MethodInputs.png)
|Name|Type|Description|
|---|---|---|
|**arr**|`ANY`|*Array to be checked*|
|**item**|`ANY`|*Item to set*|

**Returns** ![](MethodOutputs.png)
|Type|Description|
|---|---|
|`BOOL`|*Returns `TRUE` if the operation was sucessfull. Possible fails - incorrect data type (must be a reference or an array), item's data type does not match the arr data type's base type.*|


**Example**

```
VAR
    arr		: ARRAY[0..69] OF T_ArrayIndexer;
    valueToSet	: T_ArrayIndexer := 9999;
    i	: T_ArrayIndexer;
END_VAR
```
```
FOR i := 0 TO 30 BY 1 DO
    arr[i] := i + 1;
END_FOR
// [0, 1, 2, 3, ... 30, 0, 0, (69th element) 0]

ArrayHelper.SetAtFirstEmptySlot(
    arr := arr,
    item := valueToSet);
// [0, 1, 2, 3, ... 30, 9999, 0, 0, (69th element) 0]
```
---

### *`ShiftDown()`*

```
METHOD ShiftDown
VAR_INPUT
    arr		: ANY;	// Array to be checked.
    dataType	: ANY;	// Data type of the array elements, can be used like this : datayType := arr[0]
END_VAR

```
*Shifts the array down, losing first element and clearing last element in the process*

**Inputs** ![](MethodInputs.png)
|Name|Type|Description|
|---|---|---|
|**arr**|`ANY`|*Array to be checked*|
|**dataType**|`ANY`|*Data type of the array elements*|

**Example**

```
VAR
    arr			: ARRAY[0..10] OF REAL;
END_VAR
```
```

arr[1] := 5.5;
// [0, 5.5, 0, 0, 0, 0, 0, 0, 0, 0, 0]

ArrayHelper.ShiftDown(arr, arr[0]);
// [5.5, 0, 0, 0, 0, 0, 0, 0, 0, 0, 0]

```

---

### *`ShiftUp()`*

```
METHOD ShiftUp
VAR_INPUT
    arr		: ANY;	// Array to be checked.
    dataType	: ANY;	// Data type of the array elements, can be used like this : datayType := arr[0]
END_VAR

```
*Shifts the array up, losing last element and clearing first element in the process*

**Inputs** ![](MethodInputs.png)
|Name|Type|Description|
|---|---|---|
|**arr**|`ANY`|*Array to be checked*|
|**dataType**|`ANY`|*Data type of the array elements*|

**Example**

```
VAR
    arr			: ARRAY[0..10] OF REAL;
END_VAR
```
```

arr[1] := 5.5;
// [0, 5.5, 0, 0, 0, 0, 0, 0, 0, 0, 0]

ArrayHelper.ShiftUp(arr, arr[0]);
// [0, 0, 5.5, 0, 0, 0, 0, 0, 0, 0, 0]

```

---

# **ST_ArrayProperties**

```
TYPE ST_ArrayProperties :
STRUCT
	Count		: DINT;
	StartIndex	: T_ArrayIndexer;
	EndIndex	: T_ArrayIndexer;
END_STRUCT
END_TYPE
```

>*The structure is used to return properties of an array required to work with array manipulation functions.*

|Name|Data Type|Description|
|---|---|---|
|Count|DINT|Number of elements in the array|
|StartIndex|T_ArrayIndexer|First index of the array|
|EndIndex|T_ArrayIndexer|Last index of the array|

**EXAMPLE**
```
arr : ARRAY[1..10] OF INT;
```
A function that would reference this array and uses the ST_ArrayProperties as a property should return the following:

`foo(arr).Count` = 10   
`foo(arr).StartIndex` = 1   
`foo(arr).EndIndex` = 10

---

# T_ArrayIndexer

```
TYPE T_ArrayIndexer : DINT; END_TYPE
```
>*The data type is used for accessing array index - array index should always be a DINT. The dimension is defined as such by [Beckhoff](https://infosys.beckhoff.com/english.php?content=../content/1033/tc3_plc_intro/8825253771.html&id=468140306937122500).*


**EXAMPLE**

```
VAR
    arr : ARRAY[0..10] OF BOOL;
    idx : T_ArrayIndexer;     
END_VAR
```
```
FOR idx := 0 TO 10 BY 1 DO
    // Do something like this, by accesing the index without compiler warnings
    arr[idx] := FALSE;
END_FOR
```