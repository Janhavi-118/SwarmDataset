# SwarmDataset

A custom-generated dataset for multi-robot swarm formation control and collision avoidance research.

## Overview

SwarmDataset contains trajectories, sensor data, and control commands collected from multi-robot simulations in Gazebo with ROS 2. This dataset is designed for training and evaluating transformer-based architectures and other machine learning models for swarm robotics applications.

## Dataset Contents

The dataset includes:

- **Trajectory Data**: Robot positions, orientations, and velocities over time
- **Sensor Data**: Lidar scans, odometry measurements
- **Control Commands**: Velocity commands sent to robots
- **Formation Goals**: Target formation configurations and goal positions
- **Collision Avoidance Events**: Instances where robots avoid obstacles and each other
- **Gossip Protocol Messages**: Inter-robot communication data (if applicable)

## Data Format

- Rosbag files (.bag) containing ROS 2 message topics
- CSV exports for trajectory analysis
- JSON metadata for experimental configurations

### Key Topics

- `/odom` - Odometry data (position, orientation, velocity)
- `/cmd_vel` - Velocity commands
- `/scan` - Lidar sensor data
- Formation and goal state information

## Usage

### Prerequisites

- ROS 2 (Humble or later)
- Python 3.8+
- PyTorch (for model training)
- Rosbag2 tools

### Using the Dataset

To use this dataset, please follow these steps:

1. **Download the dataset** from this repository.

2. **Run `make_dataset.py`** (found in the `src/swarm_data/src` folder of the [SwarmFormer repository](https://github.com/Janhavi-118/SwarmFormer)) to convert the raw rosbag files into pickle (`.pkl`) files.

3. **Run `convert_pkl2npz.py`** (also in the same folder of the [SwarmFormer repository](https://github.com/Janhavi-118/SwarmFormer)) to convert these pickle files into compressed numpy (`.npz`) format.

4. **Upload the processed `.npz` files** onto your drive or preferred storage, and use them for model training as demonstrated in the Jupyter notebooks available in the [SwarmFormer repository](https://github.com/Janhavi-118/SwarmFormer).

## Citation

If you use this dataset in your research, please cite:

@article{chaurasia2025swarmformer,
  title={SwarmFormer Transformer-Based Multi-Robot Formation Control with Risk-Aware Fusion},
  author={Janhavi Chaurasia and Saanvi Shetty and Sakshi Ahuja and Harini Sriraman},
  journal={arXiv preprint arXiv:2301.00000},
  year={2025},
  note={Paper Accepted at RCAE 2025}
}

## Related Work

This dataset was created for research on:
- Transformer-based multi-robot control
- Swarm formation control
- Collision avoidance in dense multi-agent scenarios
- Imitation learning for robot coordination

See the SwarmFormer repository for model implementations: [https://github.com/Janhavi-118/SwarmFormer]


## Acknowledgments

Dataset generated using Gazebo simulation with ROS 2.
