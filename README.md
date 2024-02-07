# EIKF-VIO-LIO
# Usage

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

1. Run on public datasets

   We have tested the following datasets, which config file can be directly used. We only support the dataset type: rosbag containing lidar, IMU and camera measurements.

   | Datasets        | Dataset link                                            | Launch file | config file | data preprocess | evaluation script |
   | --------------- | ------------------------------------------------------- | ----------- | ----------- | --------------- | ----------------- |
   | UrCA            | https://advdataset2019.wixsite.com/urbanloco/california |             |             |                 |                   |
   | UrHK            | https://advdataset2019.wixsite.com/urbanloco/hong-kong  |             |             |                 |                   |
   | newer college   | https://ori-drs.github.io/newer-college-dataset/        |             |             |                 |                   |
   | NTU Viral       | https://ntu-aris.github.io/ntu_viral_dataset/           |             |             |                 |                   |
   | NTU MCD         | https://mcdviral.github.io/                             |             |             |                 |                   |
   | private dataset | Our hand-held device                                    |             |             |                 |                   |
   |                 |                                                         |             |             |                 |                   |

   

   1.1 Download datasets and remember its path <BagPath>and the name of rosbag <BagName>.

   1.2 Modify the corresponding launch file.

