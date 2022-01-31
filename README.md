ros2
=========

![](https://img.shields.io/travis/com/laura7089/ros2-ansible?style=flat-square)
![](https://img.shields.io/ansible/role/57736?style=flat-square)
![](https://img.shields.io/github/license/laura7089/ros2-ansible?style=flat-square)

Installs [ROS2](https://docs.ros.org/en/galactic/index.html) from released binaries on an [Ubuntu](https://ubuntu.com/) (focal) host.
[Available](https://galaxy.ansible.com/laura7089/ros2) on Ansible Galaxy.

Role Variables
--------------

- `ros2_install_location`: the fully-qualified path to extract the ros2 files to.
  Defaults to `~/ros2`.
- `ros2_source`: `remote` (default) or `local`.
- `ros2_release`: used for the `remote` source, this should be the release string as found on the [ROS2 Releases page](https://github.com/ros2/ros2/releases).
  Defaults to `galactic-20210523`.
- `ros2_local_archive`: used for the `local` source, the archive containing the ROS2 install **on the ansible controller**.
  Defaults to `./ros2.tar.bz2`.
- `ros2_shell_startup`: bool specifying whether or not to modify `~/.profile` to source the ROS2 environment on startup.
  Defaults to `yes`.
- `rosdep_init_update`: bool specifying whether or not to run `rosdep init` and `rosdep update`.
  Defaults to `yes`.
- `rosdep_install`: bool specifying whether or not to run `rosdep install ...` with the `rosdep_packages` variable.
  Defaults to `yes`.
- `rosdep_packages`: list of package names to install with `rosdep`. Defaults to:

```yaml
rosdep_packages:
  - cyclonedds
  - fastcdr
  - fastrtps
  - rti-connext-dds-5.3.1
  - urdfdom_headers
```

Example Playbook
----------------

```yaml
- hosts: servers
  roles:
     - { role: laura7089.ros2, ros2_release: "foxy-20211007" }
```

License
-------

AGPL3
