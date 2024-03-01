# EIKF-VIO-LIO

(Currently, only the necessary steps for using the code are observable. Full open access will be enabled after the review.)

<!-- TABLE OF CONTENTS -->
<details open="open" style='padding: 10px; border-radius:5px 30px 30px 5px; border-style: solid; border-width: 1px;'>
  <summary>Table of Contents</summary>
  <ol>
    <li>
      <a href="#prerequisites">Prerequisites</a>
    </li>
    <li>
      <a href="#installation">Installation</a>
    </li>
    <li>
      <a href="#run">Run on datasets</a>
    </li>
    <li>
      <a href="#evaluation">Evaluation</a>
    </li>
    <li>
      <a href="#acknowledgement">Acknowledgement</a>
    </li>
    <li>
      <a href="#citation">Citation</a>
    </li>
  </ol>
</details>

## Prerequisites

1. Livox_ros_driver

   follow https://github.com/Livox-SDK/livox_ros_driver

## Installation

1. Create ROS workspace

   ```markdown
   mkdir -p ~/EIKF_LIO_VIO/src
   cd EIKF_LIO_VIO/src
   ```

2. Clone the repository and build

   ```markdown
   git clone git@github.com:LIAS-CUHKSZ/EIKF-VIO-LIO.git
   cd ..
   catkin_make
   ```

   

## Run

We have tested the following datasets, which config file can be directly used. We only support the dataset type: rosbag containing lidar, IMU and camera measurements.

| Datasets        | Dataset link                                            | Launch file       | data preprocess | evaluation script                                            |
| --------------- | ------------------------------------------------------- | ----------------- | --------------- | ------------------------------------------------------------ |
| URCA            | https://advdataset2019.wixsite.com/urbanloco/california | URCA.launch       |                 | UR_evaluation.sh                                             |
| URHK            | https://advdataset2019.wixsite.com/urbanloco/hong-kong  | urbanloco.launch  |                 | UR_evaluation.sh                                             |
| NTU Viral       | https://ntu-aris.github.io/ntu_viral_dataset/           | NTU_VIRAL.launch  |                 | https://ntu-aris.github.io/ntu_viral_dataset/evaluation_tutorial.html |
| NTU MCD         | https://mcdviral.github.io/                             | NTU_Viral2.launch |                 | evaluate_ntu2.sh                                             |
| private dataset | Our hand-held device                                    | ilive_mid.launch  |                 | lab_evaluation.sh                                            |
|                 |                                                         |                   |                 |                                                              |



1.1 Download datasets and remember its path <Your BagPath>and the name of rosbag <Your BagName>. 

1.2 Modify the corresponding launch file.

```
<!-- what ros bag to play -->
<arg name="dataset"   default="<Your BagName>" /> 
<arg name="bag_path"   default="<Your BagPath>" />  
<!-- where to save the recorded poses -->
<arg name="path_save"   default="<Your SavePath>" /> 

```

1.3 Run the code

```
source devel/setup.bash
roslaunch ilive <Your launch file>
```

## Evaluation

If you want to get evaluation result, please run the corresponding evaluation script.



## Acknowledgement
We thank the authors of the following repositories for their open-source code:

OpenVINS:
https://docs.openvins.com/

Fast-LIO:
https://github.com/hku-mars/FAST_LIO

R3live:
https://github.com/hku-mars/r3live
## Citation

```
@misc{li2024efficient,
      title={Efficient Invariant Kalman Filter for Inertial-based Odometry with Large-sample Environmental Measurements}, 
      author={Xinghan Li and Haoying Li and Guangyang Zeng and Qingcheng Zeng and Xiaoqiang Ren and Chao Yang and Junfeng Wu},
      year={2024},
      eprint={2402.05003},
      archivePrefix={arXiv},
      primaryClass={cs.RO}
}
```
