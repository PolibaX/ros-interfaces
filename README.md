# Custom ROS2 Interfaces

This repository contains custom ROS2 interfaces including messages, services, and actions for use in ROS2-based applications.

## Table of Contents

- [Overview](#overview)
- [Custom Interfaces](#custom-interfaces)
- [Installation](#installation)
- [Building and Using the Custom Interfaces](#building-and-using-the-custom-interfaces)
- [Docker Integration](#docker-integration)
  - [Modifying the Dockerfile](#modifying-the-dockerfile)


## Overview

This repository provides custom ROS2 interfaces (messages, services, and actions) that can be used across your ROS2 projects. These interfaces are defined in `.msg`, `.srv`, and `.action` files, which can be built and used in your ROS2 workspace.

## Custom Interfaces

- **Messages**: Custom message types for exchanging data between ROS2 nodes.
- **Services**: Custom service types for implementing request-response communication.
- **Actions**: Custom action types for goal-based task execution.

The interfaces are located in the `msg/`, `srv/`, and `action/` directories, respectively.

## Installation

### Prerequisites

Ensure you have the following installed:

- ROS2 (Foxy, Galactic, Humble, etc.)
- `colcon` build tool
- `rosdep` for dependency management

### Building and Using the Custom Interfaces

1. Clone the repository into your ROS2 workspace:
    ```bash
    cd ~/ros2_ws/src
    git clone https://github.com/yourusername/custom_ros2_interfaces.git
    ```

2. Install any dependencies (if required):
    ```bash
    cd ~/ros2_ws
    rosdep install --from-paths src --ignore-src -r -y
    ```

3. Build your workspace:
    ```bash
    colcon build
    ```

4. Source the workspace:
    ```bash
    source ~/ros2_ws/install/setup.bash
    ```

5. The custom interfaces are now available for use in your ROS2 nodes.

## Docker Integration

To use these custom interfaces within a Docker container, you need to modify the Dockerfile to include the installation of the custom interfaces.

### Modifying the Dockerfile

1. **Copy the custom interfaces into the Docker image.**
2. **Build the custom interfaces inside the Docker container.**
3. **Source the workspace to make the interfaces available.**
