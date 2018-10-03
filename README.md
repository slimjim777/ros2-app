# ROS2 Application Demo Snap

This snap demonstrates creating a simple ROS2 application as a snap using the
ROS core libraries in an Ubuntu 18.04 base snap.

The application is a simple talker/listener does not need the ROS2 core libraries
within the snap.


## Building

### Build and install the base snap
The snap is dependant on the [core18-ros2-james](https://github.com/slimjim777/core18/tree/ros-base) snap.

```bash
# Fetch the base snap
git clone https://github.com/slimjim777/core18-ros2.git
cd core18-ros2

# Build the snap
sudo snapcraft
sudo snapcraft clean

# Install the snap
sudo snap install --dangerous --jailmode core18-ros2-james_18_amd64.snap
```

### Build and install the application snap

```bash
# Fetch the base snap
git clone https://github.com/slimjim777/ros2-app.git
cd ros2-app

# Build the snap
snapcraft

# Install the application snap
sudo snap install --dangerous --devmode ros2-app-james_1.0_amd64.snap
```

Note that the application snap currently needs to be installed in `devmode`.

## Running the application

```bash
$ ros2-app-james.listener &
$ ros2-app-james.talker

[INFO] [talker]: Publishing: "Hello World: 0"
[INFO] [listener]: I heard: [Hello World: 0]
[INFO] [talker]: Publishing: "Hello World: 1"
[INFO] [listener]: I heard: [Hello World: 1]
[INFO] [talker]: Publishing: "Hello World: 2"
[INFO] [listener]: I heard: [Hello World: 2]
[INFO] [talker]: Publishing: "Hello World: 3"
[INFO] [listener]: I heard: [Hello World: 3]
[INFO] [talker]: Publishing: "Hello World: 4"
[INFO] [listener]: I heard: [Hello World: 4]
[INFO] [talker]: Publishing: "Hello World: 5"
[INFO] [listener]: I heard: [Hello World: 5]
...
```
