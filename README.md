Various libraries for TwinCAT using OOP style. For example on usage see tests in the ```TESTS``` folder of the library project. Report any possible bugs :) 
There are many project to choose from, but they all, for the most part, reference ```Core``` library - this is a library with core functionalities and interfaces.
Current libraries include:

![image](https://github.com/user-attachments/assets/a412012d-70e0-4f8a-9ab3-066319f4da57)

As a side note, the libraries contain "helper classes", which are programs that do not hold any body logic, thus they do not require being called. These "classes" have only ```methods``` and ```constants```. As an example, this is a helper class for Ams:

![image](https://github.com/user-attachments/assets/75aac691-a353-4d93-a660-af2455a43738)

And here is an exaple of calling it:
```Ruby
sNetId := ZigasLibs_Core.AmsHelper.NetIdToString(_amsAddress.netId)
```

Every project and object can and should have tests for them written. TcUnit framework is used for writting tests For more info see https://tcunit.org/#/ . The tests should serve as a guidline how to use the functionality of the library. Every library has same project structure, created from a template:

![image](https://github.com/user-attachments/assets/f9c60dcf-0ec2-45c2-91bf-91beabd425dd)

Inside the "TEST" folder, there are test suites for  every ```FUNCTION_BLOCK```,```PROGRAM```,```FUNCTION```, etc... Example of how to create different logs with the logger tests:

```ruby
IF fbLogger.Ready AND fbLocalSystemTime.CurrentTime.IsValid THEN
  fbLogger.LogError('Error text....');
  fbFileHandler.FileProperties.FileLocation := FOLDER_PATH;
...
```


~~With every release, the ```TcUnit``` is excluded via the```Compiler defines``` due to compatibility issues with ARM devices (low RAM, which causes issues if including TcUnit, see https://github.com/tcunit/TcUnit/issues/148). Entering ```UnitTests``` to the ```compiler defines``` field will enable the ```TcUnit``` library, which is required for compilation and test running, but not for execution of any library files.~~


As it turns out, the upper solutio still does not solve the issue, as by default parameters are set to maximum and you can't exclude TcUnit. What is the best solution is, TcUnit is NOT excluded from build. Instead, the project that uses these libraries should have TcUnit as well, and then set these parameters to the highlighted values, this way you override the parameters from within the library, effectively setting the unit test count to 1:

![image](https://github.com/user-attachments/assets/31997d48-711f-4992-bb0f-0d20825c394e)


This results in next to no memory usage by TcUnit in your project while having TcUnit enabled and working properly for library development:
![image](https://github.com/user-attachments/assets/9e823942-b539-4dea-912b-58a2a228e053)




TwinCAT version: 4024.60 (08/09/2024)
