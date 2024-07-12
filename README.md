# LuSNAR Dataset

## Introduction

This repository contains a lunar segmentation, navigation and reconstruction dataset **LuSNAR** based on multi-sensor (**Stereo Camera**, **LiDAR**, **IMU**) for autonomous exploration.
The **LuSNAR** is a multi-task, multi-scene, and multi-label lunar dataset, it includes **9** lunar simulation scenes based on Unreal Engine and each scene is divided according to topographic relief and the density of objects.

## Scene Diagram
![Scene Diagram](1.png)


## Data Diagram
The LuSNAR dataset includes:
- High-resolution stereo image pairs
- Panoramic semantic labels
- Dense depth maps
- LiDAR point clouds
- IMU data
- Rover pose data
![Data Diagram](2.png)

### Use Cases
The dataset can be used for comprehensive evaluation of autonomous perception and navigation systems:
- 2D/3D Semantic Segmentation
- Visual/LiDAR SLAM
- 3D Reconstruction

### Availability
The LuSNAR dataset is available for download from CSTCloud.
[LuSNAR Dataset Download](https://pan.cstcloud.cn/s/2Ie7D5PSLU)
Password:fjZt

## Dataset Structure
The LuSNAR dataset has a total size of **108GB**, containing:
- **42GB** of stereo image pairs
- **50GB** of depth maps
- **356MB** of semantic segmentation labels
- **14GB** of single-frame point cloud data with semantic information
```plaintext
├── image1
│   ├── RGB
│   │   ├── timestamp1.png
│   │   ├── timestamp2.png
│   │   └── ...
│   ├── Depth
│   │   ├── timestamp1.png
│   │   ├── timestamp2.png
│   │   └── ...
│   └── Label
│       ├── timestamp1.png
│       ├── timestamp2.png
│       └── ...
├── image2
│   ├── RGB
│   │   ├── timestamp1.png
│   │   ├── timestamp2.png
│   │   └── ...
│   ├── Depth
│   │   ├── timestamp1.png
│   │   ├── timestamp2.png
│   │   └── ...
│   └── Label
│       ├── timestamp1.png
│       ├── timestamp2.png
│       └── ...
├── LiDAR
│       ├── timestamp1.txt
│       ├── timestamp2.txt
│       └── ...
├── Rover_pose.txt
└── IMU.txt
```
The correspondence between the colors in semantic images and category numbers is as follows:

| Category Number | Category       | Color   |
|-----------------|----------------|---------|
| 0               | Lunar regolith | ![#BB469C](https://via.placeholder.com/15/BB469C/000000?text=+) #BB469C |
| 1               | Impact crater  | ![#7800C8](https://via.placeholder.com/15/7800C8/000000?text=+) #7800C8 |
| 2               | Rock           | ![#E8FA50](https://via.placeholder.com/15/E8FA50/000000?text=+) #E8FA50 |
| 3               | Mountain       | ![#AD451F](https://via.placeholder.com/15/AD451F/000000?text=+) #AD451F |
| 4               | Sky            | ![#22C9F8](https://via.placeholder.com/15/22C9F8/000000?text=+) #22C9F8 |

The correspondence between category numbers and their respective categories in the LiDAR point cloud data is as follows:

| Category Number | Category       |
|-----------------|----------------|
| -1              | Lunar regolith |
| 0               | Impact crater  |
| 174             | Rock           |

## File Format
### LiDAR/timestamp.txt
```plaintext
| x [m] | y [m] | z [m] | category number |
```
### Rover_pose.txt
```plaintext
| timestamp [ns] | p_RS_R_x [m] | p_RS_R_y [m] | p_RS_R_z [m] | q_RS_w [] | q_RS_x [] | q_RS_y [] | q_RS_z [] | v_RS_R_x [m s^-1] | v_RS_R_y [m s^-1] | v_RS_R_z [m s^-1] | b_w_RS_S_x [rad s^-1] | b_w_RS_S_y [rad s^-1] | b_w_RS_S_z [rad s^-1] | b_a_RS_S_x [m s^-2] | b_a_RS_S_y [m s^-2] | b_a_RS_S_z [m s^-2] |
```
### IMU.txt
```plaintext
| timestamp [ns] | w_RS_S_x [rad s^-1] | w_RS_S_y [rad s^-1] | w_RS_S_z [rad s^-1] | a_RS_S_x [m s^-2] | a_RS_S_y [m s^-2] | a_RS_S_z [m s^-2] |
```


