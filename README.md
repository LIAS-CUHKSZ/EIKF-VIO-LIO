# EIKF-VIO-LIO

(Currently, only the necessary steps for using the code are observable. Full open access will be enabled after the review.)

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

   

## Run on datasets

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
## Acknowledgement


## Citation



## Evaluation

If you want to get evaluation result, please run the corresponding evaluation script.

