## Adding the gazebo_ros_control plugin

**Function:** Parse the transmission tags and loads the appropriate hardward interfaces and controller manager.

```
<!-- ros_control plugin -->
<gazebo>
  <plugin name="gazebo_ros_control" filename="libgazebo_ros_control.so">
    <robotNamespace>/rrbot</robotNamespace>
    <robotSimType>gazebo_ros_control/DefaultRobotHWSim</robotSimType>
  </plugin>
</gazebo>

```

`<plugin>` specifies the plguin name to be loaded, which is libgazebo_ros_control.so.(Default).
`<robotNamespace>` the ROS namespace to be used for this instance of th plugin, defaults to robot name in URDF/SDF.
`<controlPeriod>` specifies the controller update rate.
`<robotSimType>` specifies the type of robot hardward interfaces, defaults to "DefaultRobotHWSim", you can find the source code in the package "gazebo_ros_control".

**WHSY:**
```
<!--load the gazebo rosz-control plug in-->
<gazebo>
  <plugin name="balance_controller" filename="librobot_state_gazebo_ros_control_plugin.so">
    <robotNamespace>$(arg robot_namespace)</robotNamespace>
    <robotSimType>balance_controller/SimRobotStateHardwareInterface</robotSimType>
  </plugin>
</gazebo>

```
**ATTENTION:** He created his own custom robot hardward interface <SimRobotStateHardwareInterface> and gazebo_ros_control plugin <librobot_state_gazebo_ros_control_plugin>
