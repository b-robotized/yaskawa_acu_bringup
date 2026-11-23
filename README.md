# yaskawa_acu_bringup

Bringup for a Yaskawa robot that is connected through a NEXT ACU controller and b»controlled box.

| Package | Content |
|---|---|
| `yaskawa_acu_bringup` | Robot description, controller configuration, MoveIt configuration, foreman profiles, and launch files |

Only the NHC12 robot is supported now.

## Use without b»controlled box commissioning

Clone these repositories into `src` of your workspace:

- [motoman_ros2_support_packages](https://github.com/b-robotized-forks/motoman_ros2_support_packages), branch `b-controlled-box/jazzy`
- [foreman](https://github.com/ros-controls/foreman), branch `master`
- [b_robotized_moveit_plugins](https://github.com/b-robotized/b_robotized_moveit_plugins), branch `master`

Install the dependencies and build:

```bash
rosdep install --from-paths src --ignore-src -y
colcon build
```

Test with mock hardware:

```bash
ros2 launch yaskawa_acu_bringup yaskawa_acu_bringup_mock.launch.xml
ros2 launch yaskawa_acu_bringup yaskawa_acu_moveit.launch.xml
```

## Hardware

The real hardware plugin `yaskawa_driver/YaskawaACUHardwareInterface` runs in the b»controlled box controller manager. This repository does not contain it. The mock launch file uses `mock_components/GenericSystem` and needs no robot.

## Startup

See the Yaskawa pages in [b_ctrldbox_commissioning](https://github.com/b-robotized/b_ctrldbox_commissioning):

- [Robot setup](https://github.com/b-robotized/b_ctrldbox_commissioning/blob/master/docs/supported_robots/YASKAWA.md)
- [Startup procedure](https://github.com/b-robotized/b_ctrldbox_commissioning/blob/master/workspaces/yaskawa/LAUNCH.md)

## License

Apache-2.0. See `LICENSE`.
