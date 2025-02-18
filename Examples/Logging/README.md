**ZigaLibs_Logging Example project**

In this example, you can see a simple project displaying how logging can be used with `ZigaLibs_Logging.FB_Logger` and `ZigaLibs_Core.ILoggerEx` interface that it implements. You can download and run the source code on a TwinCAT3 runtime. The things you should adjust are located in `VAR_CONSTANT` inside the `MAIN` POU:

```Ruby
VAR CONSTANT
	MY_TARGET_DEVICE_NET_ID 	: Tc2_System.T_AmsNetIdArr := [192,168,56,1,1,1]; // Empty = local
	MY_LOGGER_EXAMPLE_FILE_LOCATION	: Tc2_System.T_MaxString := 'C:\';
	MY_LOGGER_EXAMPLE_FILE_NAME	: Tc2_System.T_MaxString := 'ExampleLog';
END_VAR
```

Adjust these to wherever your path to the file is, NetID runtime and, optionally, adjust file name. When done, you can download and run the applicaiton. 

**Some objects to take note of:**
-----------------------------------------------------------------------------------------------------------------------------------
```Ruby
// Instantiating the function block with logger via dependency injection.
	fbPositionObserver_WithLogger : 
		FB_PositionObserver_LoggerWithDependencyInjection(logger := GVL.Logger);
```
This is a function block that requires logger provided. If you do not provide an object that implements `I_LoggerEx` a compile error is issued. You can also provide `GVL.ILogger` as it is the interface it-self, and is assigned at the GVL variable list decleration.

-----------------------------------------------------------------------------------------------------------------------------------
```Ruby
	// Instantiating the function block with provided optional logger via dependency injection.
	// For this to work, we need to provide the interface (pointer), instead of the instantiating function block.	
	fbPositionObserver_OptionalLogger_WithLogger :
		FB_PositionObserver_OptionalLoggerWithDependencyInjection(logger := GVL.ILogger);
```
This is a function block that dooes **NOT** require logger provided. You can opt to provide logger, but it only accepts interface `I_LoggerEx` since inside the constructor, there is a `REFERENCE TO I_LoggerEx`.

-----------------------------------------------------------------------------------------------------------------------------------
```Ruby		
	// Instantiating the function block without logger via dependency injection.	
	fbPositionObserver_OptionalLogger_WithoutLogger : 
		FB_PositionObserver_OptionalLoggerWithDependencyInjection(logger := 0);
```
This is the same function block as above, the only difference is, you provide an invalid reference by setting the logger to `0`. This is a way of providing "optional" constructor parameters. If you do use this approach, make sure to check for reference/pointer validity when working with the object passed inside. Here is an example where the `_logger` is defined as `_logger : I_LoggerEx`, another option would be to use `_logger : REFERENCE TO I_LoggerEx`, in that case you would check by using `__ISVALIDREF(_logger)`, which returns `TRUE` if the reference is valid or not - comes down to personal preference on what to use.

```Ruby
// Since the interface might not be assigned, we need to check for validity of the pointer.
IF _logger <> 0 THEN
	IF _bottoPositionObserver.HasRisingEdge THEN
		_logger.LogInfo(_sb.Reset()
			.AddString('Source: ')
			.AddWithDblQuotationMarks(THIS^.InstanceName)
			.AddString(' Bottom position reached.')
			.Create());
	END_IF
```
-----------------------------------------------------------------------------------------------------------------------------------
The logger and interface provided can be found in `GVL` list
```Ruby
{attribute 'qualified_only'}
VAR_GLOBAL
	Logger	: ZigaLibs_Logging.FB_Logger;
	ILogger	: ZigaLibs_Core.I_LoggerEx := Logger;
END_VAR 
```
Here is an example of running it and looking at the generated log file:

![ExapleSimulation](https://raw.githubusercontent.com/ZigaJavornik/ZigaLibs/refs/heads/master/Examples/Logging/Gifs/ExapleSimulation.gif)
