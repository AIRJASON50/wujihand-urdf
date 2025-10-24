# WujiHand 机器人手仿真

20自由度灵巧机器人手仿真系统，支持RViz可视化和MuJoCo物理仿真

##  文件结构

```
wujihand-urdf/
├── Description/                    # 机器人描述文件
│   ├── meshes/                     # STL网格文件
│   ├── urdf/                       # URDF模型文件
│   ├── xml_for_mujoco/             # MuJoCo仿真文件
│   │   ├── mjmodel.xml
│   │   └── mujoco_simulation.py    # MuJoCo仿真脚本
│   └── yaml/                       # 配置文件
├── .scripts/                       # 脚本工具
│   ├── launch/                     # ROS2 Launch文件
│   │   ├── display.left.py         # 左手RViz显示
│   │   └── display.right.py        # 右手RViz显示
│   └── rviz/                       # RViz配置文件
├── CMakeLists.txt                  # CMake构建文件
└── requirements.txt                # Python依赖
```

##  使用方法

### 方法1: RViz可视化 (需要ROS2)

#### 构建包
```bash
# 在ROS2工作空间中
colcon build --packages-select wujihand-urdf
source install/setup.bash
```

#### 启动RViz显示
```bash
# 显示左手
ros2 launch wujihand-urdf display.left.py

# 显示右手  
ros2 launch wujihand-urdf display.right.py
```

### 方法2: MuJoCo物理仿真

#### 安装依赖
```bash
pip install -r requirements.txt
```

#### 启动仿真
```bash
python Description/xml_for_mujoco/mujoco_simulation.py
```
