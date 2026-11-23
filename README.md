# yaskawa_acu_bringup

Bringup for a Yaskawa robot that is connected through a NEXT ACU controller and b»controlled box.

| Package | Content |
|---|---|
| `yaskawa_acu_bringup` | Robot description, controller configuration, MoveIt configuration, foreman profiles, and launch files |

Only the NHC12 robot is supported now.

## Installation

```bash
vcs import src < src/yaskawa_acu_bringup/yaskawa_acu_bringup.repos
rosdep install --from-paths src --ignore-src -y
```

## Hardware

The real hardware plugin `yaskawa_driver/YaskawaACUHardwareInterface` runs in the b»controlled box controller manager. This repository does not contain it. The mock launch file uses `mock_components/GenericSystem` and needs no robot.

## Startup

See `LAUNCH.md`.

## License

Apache-2.0. See `LICENSE`.
