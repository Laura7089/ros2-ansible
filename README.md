ros2
=========

![](https://img.shields.io/travis/com/laura7089/ros2-ansible?style=flat-square)
![](https://img.shields.io/ansible/role/57736?style=flat-square)
![](https://img.shields.io/github/license/laura7089/ros2-ansible?style=flat-square)

Installs [ROS2](https://docs.ros.org/en/galactic/index.html) from released binaries on an [Ubuntu](https://ubuntu.com/) (focal) host.

Role Variables
--------------

A description of the settable variables for this role should go here, including any variables that are in defaults/main.yml, vars/main.yml, and any variables that can/should be set via parameters to the role. Any variables that are read from other roles and/or the global scope (ie. hostvars, group vars, etc.) should be mentioned here as well.

- `ros2_install_location`: the fully-qualified path to extract the ros2 files to.
  Defaults to `~/ros2`.
- `ros2_release`: the release string as found on the [ROS2 Releases page](https://github.com/ros2/ros2/releases).
  Defaults to `galactic-20210523`.
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
