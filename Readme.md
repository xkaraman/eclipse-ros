# How to import ROS-Projects into ECLIPSE IDE 2019
## Using catking_tools

Switch to your catking workspace (assuming ~/catkin_ws)
```
cd ~/catkin_ws
```

I find the following command to be needed in order to correctly import in ECLIPSE IDE:

#### I would advice NOT to skip it
```
catkin build {pkg_name}
```

Next build .project and .cproject required for ECLIPSE IDE in import phase:

```
catkin build {pkg_name} --force-cmake -G"Eclipse CDT4 - Unix Makefiles"
``` 

Now, open ECLIPSE IDE.
Import project:
```
File -> Import... -> Existing Projects into Workspace
```

Select root directory:
~/catkin\_ws/build/{pkg_name}
Do NOT select any of the options and finish.

In order to add C++11 syntax or greater support:
```
Project Explorer -> Right-click on project -> Properties -> C/C++ Include Paths and Includes -> Add Preprocessor Symbol
```
For C++11 support: __cplusplus=20113L

For C++14/17: 201402L/201703L accordingly

See [here](http://gcc.gnu.org/onlinedocs/cpp/Standard-Predefined-Macros.html) for more __cplusplus options.

Then rebuild your index
```
Project Explorer -> Right-click on project -> Index -> Rebuild
```
