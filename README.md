# Bittle_URDF

![Screenshot from 2021-03-08 00-32-16](https://user-images.githubusercontent.com/32562299/110247158-c9636d80-7fa5-11eb-92ab-4f71c79b052b.png)

Repository for storing URDF (Universal Robot Description Format) file and meshes in .obj format for Petoi Bittle.

Meshes are downloaded from https://grabcad.com/library/petoi-bittle-evo-quadruped-robot-rev-engineering-1

The meshes are created by third-party designer, who reverse-engeneered the orginal design by Prof. Li Rongzhong. Consider supporting Prof. Li Rongzhong by buying the original Bittle at 

https://www.seeedstudio.com/CH-Bittle-p-4833.html     (fully assembled version)

or

https://www.indiegogo.com/projects/bittle-a-palm-sized-robot-dog-for-stem-and-fun     (kit for DIY assembly)

TO-DO:
- [x] Working URDF
- [x] Proper masses for every link, measurements taken by weighing each part with electronic scale
- [x] Example for running in [Nvidia Isaac Gym](https://developer.nvidia.com/isaac-gym)
- [ ] Add prismatic joints to emulate the springs in Bittle legs
- [x] Measure and tweak joint limits
- [x] Add IMU link and joint
- [x] Change collision objects from primitives to low-poly meshes
- [x] Upload two separate versions: one for BiBoard and one for NyBoard - no need for now, IMU is located at the same position
- [ ] Add material descriptions

## How to run, what to do?
I mainly created this to use for training RL algorithms in Isaac Gym - I have already tested it and the URDF file imports and can be used for training normally, although some tweaking of weights and adding prismatic joints for springs will be necessary for proper simulation. At some point I also want to add configration for importing it to Gazebo. Currently you can try Bittle in Isaac Gym by first downloading and installing it from here https://developer.nvidia.com/isaac-gym and then 
1) placing bittle.urdf to assets/urdf/
2) placing obj folder with meshes to assets/meshes 
3) replacing joint_monkey.py in python/examples with joint_monkey.py from this repository and running
4) python joint_monkey.py --asset_id 7
