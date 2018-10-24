# okvis_cg

okvis ros wrapper and the core code is the modified version of **okvis-1.1.3**

> **OKVIS(Open Keyframe-based Visual-Inertial SLAM) tracks the motion of an assembly of an Inertial Measurement Unit (IMU) plus N cameras (tested: mono, stereo and four-camera setup) and reconstructs the scene sparsely.** This is the Author’s implementation of the [1] and [3] with more results in [2]. There is currently no loop-closure detection / optimisation included, but we are working on it.

**Code**
* [ethz-asl/okvis (Github)](https://github.com/ethz-asl/okvis)
* [ethz-asl/okvis_ros (Github)](https://github.com/ethz-asl/okvis_ros)

**Papers**
* [1] Stefan Leutenegger, Simon Lynen, Michael Bosse, Roland Siegwart and Paul Timothy Furgale. **Keyframe-based visual–inertial odometry using nonlinear optimization.** The International Journal of Robotics Research, 2015.
* [2] Stefan Leutenegger. **Unmanned Solar Airplanes: Design and Algorithms for Efficient and Robust Autonomous Operation.** Doctoral dissertation, 2014.
* [3] Stefan Leutenegger, Paul Timothy Furgale, Vincent Rabaud, Margarita Chli, Kurt Konolige, Roland Siegwart. **Keyframe-Based Visual-Inertial SLAM using Nonlinear Optimization.** In Proceedings of Robotics: Science and Systems, 2013.

-----

## Build & Run

### okvis

#### Build
```bash
cd okvis
mkdir build & cd build
cmake .. & make -j4
```
#### Run

* Dataset
  ```bash
  ./okvis_app_synchronous path/to/okvis/config/config_fpga_p2_euroc.yaml path/to/MH_01_easy/mav0/
  ```

### okvis_ros

#### Build
```bash
catkin_make
```
#### Run

* Dataset
  ```bash
  rosrun okvis_ros okvis_node_synchronous path/to/okvis_ros/okvis/config/config_fpga_p2_euroc.yaml path/to/MH_01_easy.bag
  ```
  or  
  ```bash
  roslaunch okvis_ros okvis_node_synchronous.launch [mono:=true]
  ```
