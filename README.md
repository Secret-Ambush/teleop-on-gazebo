# `teleop_twist_keyboard.py` - ROS Teleoperation Script

The `teleop_twist_keyboard.py` script is a Python-based teleoperation node for controlling a robot's motion using keyboard input. It is typically used in ROS (Robot Operating System) environments to control mobile robots, such as TurtleBot3, in a Gazebo simulation or real-world application.

## Usage

The script allows you to control the robot's linear and angular velocities using the following keyboard commands:

- `i`: Move forward.
- `o`: Move forward and rotate counterclockwise.
- `j`: Rotate counterclockwise.
- `l`: Rotate clockwise.
- `u`: Move forward and rotate clockwise.
- `,`: Move backward.
- `.`: Move backward and rotate counterclockwise.
- `m`: Move backward and rotate clockwise.
- `O`: Move diagonally forward-right.
- `I`: Move forward-right.
- `J`: Move diagonally forward-left.
- `L`: Move diagonally forward-right.
- `U`: Move diagonally forward-right.
- `<`: Move diagonally backward-left.
- `>`: Move diagonally backward-right.
- `M`: Move diagonally backward-right.
- `t`: Move up (in the z-axis).
- `b`: Move down (in the z-axis).

Other keyboard commands allow you to adjust the robot's speed:

- `q`: Increase both linear and angular speeds by 10%.
- `z`: Decrease both linear and angular speeds by 10%.
- `w`: Increase only linear speed by 10%.
- `x`: Decrease only linear speed by 10%.
- `e`: Increase only angular speed by 10%.
- `c`: Decrease only angular speed by 10%.

Pressing any other key stops the robot.

## Parameters

The script accepts various parameters that can be configured for different robot setups:

- `speed`: Initial linear speed of the robot.
- `turn`: Initial angular speed of the robot.
- `speed_limit`: Maximum linear speed allowed.
- `turn_limit`: Maximum angular speed allowed.
- `repeat_rate`: Rate at which the teleoperation commands are repeated. Set to 0 for continuous control.
- `key_timeout`: Time limit for key presses.
- `stamped`: Determines whether the output messages use the `TwistStamped` message format. Set to `True` for stamped messages.
- `frame_id`: Frame ID for stamped messages.

## Example Launch File

To use this script with a TurtleBot3 robot in a Gazebo simulation, you can create a custom launch file. Here's an example launch file:

```xml
<launch>
  <!-- Launch the teleop_twist_keyboard node -->
  <node pkg="teleop_twist_keyboard" type="teleop_twist_keyboard.py" name="teleop_twist_keyboard" output="screen">
    <!-- Specify parameters here as needed -->
    <param name="speed" type="double" value="0.5" />
    <param name="turn" type="double" value="1.0" />
    <!-- Add other parameters as required -->
  </node>

  <!-- Add TurtleBot3 Gazebo simulation launch or bringup commands here -->
</launch>
```

## References

- ROS Wiki: [ROS Teleop Twist Keyboard](http://wiki.ros.org/teleop_twist_keyboard)
