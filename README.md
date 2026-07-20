Various libraries for TwinCAT using OOP style. For example on usage see tests in the ```TESTS``` folder of the library project. Report any possible bugs.
There are many project to choose from, but they all, for the most part, reference ```Core``` library - this is a library with core functionalities and interfaces.

Further documentation with examples can be found [here](Examples/Documentation/Documentation.md).

Every project and object can and should have tests for them written. TcUnit framework is used for writting tests For more info see https://tcunit.org/#/ . The tests should serve as a guidline how to use the functionality of the library. Every library has same project structure, created from a template:

![image](https://github.com/user-attachments/assets/f9c60dcf-0ec2-45c2-91bf-91beabd425dd)

Inside the "TEST" folder, there are test suites for  every ```FUNCTION_BLOCK```,```PROGRAM```,```FUNCTION```, etc...

**NOTE**

>In order to avoid having `TcUnit` downloaded to the production machine, make sure that your environment machine does not have TcUnit installed. If that is the case, when you donwload the code, anything related to TcUnit will be excluded - if you do have `TcUnit` installed you will get `GVL_TcUnit` list, which will have 1000 test suites by default, which will end up taking around 100MB~ of space. You can look at the issues when downloading TcUnit to devices which have limited RAM [here](https://github.com/tcunit/TcUnit/issues/148). Here are the steps you should take before downloading the code including any of the libraries to a machine:
![ExampleRemoveLibrary](https://raw.githubusercontent.com/ZigaJavornik/ZigaLibs/refs/heads/master/RemoveTcUnitLibrary.gif)
A good aproach to develop libraries would be, to have the development on a virtual machine, while having your actual PC/laptop (used for loading to the machines) have no reference to the `TcUnit` library, that way it will always be excluded when downloading the code. Inside the projects, `TcUnit` will have the option to not trigger errors if it is not installed on the sistem, so that no misleading errors are displayed:
![image](https://github.com/user-attachments/assets/4869b1a3-e009-40e2-b90f-062e098f85e5)


TwinCAT version: 4024.66 (06/02/2026)
