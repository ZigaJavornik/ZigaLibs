Various libraries for TwinCAT using OOP style. For example on usage see tests in the TESTS folder of the library project. Report any possible bugs :) 
There are 2 projects and library categories to take from:
- Core: This is a library with core functionalities and interfaces.
- Libraries: Here more non-generic implementations are located. Where applicable, objects from core library are used.
![image](https://github.com/user-attachments/assets/8d3668d3-6c6d-4851-b0f1-351591798987)

As a side note, the libraries contain "helper classes", which are programs that do not hold any body logic, thus they do not require being called. These "classes" have only methods and constants. As an example, this is a helper class for Ams:

![image](https://github.com/user-attachments/assets/75aac691-a353-4d93-a660-af2455a43738)

And here is an exaple of calling it:

```
sNetId := ZigasLibs_Core.AmsHelper.NetIdToString(_amsAddress.netId)
```

Every project and object can and should have tests for them written. TcUnit framework is used for writting tests For more info see https://tcunit.org/#/ 

TwinCAT version: 4024.60 (08/09/2024)
