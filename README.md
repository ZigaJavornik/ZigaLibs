Various libraries for TwinCAT using OOP style. For example on usage see tests in the TESTS folder of the library project. Report any possible bugs :) 
There are many project to choose from, but they all, for the most part, reference Core library - this is a library with core functionalities and interfaces.
Current libraries include:

![image](https://github.com/user-attachments/assets/240a38a1-b08b-4952-b3ad-711e162df883)


As a side note, the libraries contain "helper classes", which are programs that do not hold any body logic, thus they do not require being called. These "classes" have only methods and constants. As an example, this is a helper class for Ams:

![image](https://github.com/user-attachments/assets/75aac691-a353-4d93-a660-af2455a43738)

And here is an exaple of calling it:

```
sNetId := ZigasLibs_Core.AmsHelper.NetIdToString(_amsAddress.netId)
```

Every project and object can and should have tests for them written. TcUnit framework is used for writting tests For more info see https://tcunit.org/#/ . The tests should serve as a guidline how to use the functionality of the library. Every library has same project structure, created from a template:

![image](https://github.com/user-attachments/assets/f9c60dcf-0ec2-45c2-91bf-91beabd425dd)

Inside the "TEST" folder, there are test suites for  every ```FUNCTION_BLOCK```,```PROGRAM```,```FUNCTION```, etc... Example of how to create different logs with the logger tests:

```
IF fbLogger.Ready AND fbLocalSystemTime.CurrentTime.IsValid THEN
  fbLogger.LogError('Error text....');
  fbFileHandler.FileProperties.FileLocation := FOLDER_PATH;
...
```


With every release, the TcUnit is excluded via the "Compiler defines" due to compatibility issues with ARM devices (low RAM, which causes issues if including TcUnit, see https://github.com/tcunit/TcUnit/issues/148)

TwinCAT version: 4024.60 (08/09/2024)
