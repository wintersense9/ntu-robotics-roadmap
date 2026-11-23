# 移动机器人与 SLAM

本组课程处理机器人系统的核心问题：在噪声条件下估计自身状态并同步构建环境地图。MRS II 是由滤波方法转向优化方法的分界点，从该课程开始进入实际 SLAM 系统的实现。

---

## 1. Mobile Robotics and Sensing I

| 项目 | 内容 |
|---|---|
| 学校 / 讲者 | University of Bonn / Cyrill Stachniss |
| 页面 | https://www.youtube.com/playlist?list=PLgnQpQtFTOGQEn33QDVGJpiZLi-SlL7vA |
| 阶段 | T2 |
| 工作量 | 50–70 小时 |
| 前置 | 概率论、线代、Python |

### 内容

以《Probabilistic Robotics》前半部分为主。

| 模块 | 内容 |
|---|---|
| 不确定性 | 概率建模的原因、高斯表示、协方差 |
| 贝叶斯滤波 | 递归贝叶斯更新、预测与校正 |
| 卡尔曼滤波 | KF、EKF 的线性化、雅可比、协方差传播 |
| 其他高斯滤波 | 信息滤波、无迹卡尔曼（UKF） |
| 非参数滤波 | 粒子滤波、重采样、粒子退化 |
| 定位 | 马尔可夫定位、蒙特卡洛定位（AMCL） |
| 占据栅格建图 | 逆传感器模型、log-odds 更新、栅格地图 |
| 传感器 | 轮式里程计、IMU、2D/3D LiDAR、RGB-D 的噪声模型 |

### 作业与产出

- 用 EKF 完成一维或二维定位，输出协方差椭圆
- 用粒子滤波完成定位，对比不同粒子数的精度
- 占据栅格建图

### 能力目标

- 能写出 EKF 的五个公式并解释各项
- 能说明粒子滤波相对 EKF 的适用条件与代价
- 能用激光雷达建出占据栅格图，并解释 log-odds 更新

### 参考

- 书：《Probabilistic Robotics》Thrun, Burgard, Fox（第 2–9 章）
- 代码：PythonRobotics（定位与建图部分）

### 注意事项

- 协方差矩阵需保持正定，数值上使用 Joseph 形式更新
- 里程计模型中的角度归一化（-π, π）错误会导致定位发散
- 粒子滤波需监控有效粒子数，否则出现粒子退化

---

## 2. Mobile Robotics and Sensing II

| 项目 | 内容 |
|---|---|
| 学校 / 讲者 | University of Bonn / Cyrill Stachniss |
| 页面 | https://www.youtube.com/watch?v=mQvKhmWagB4&list=PLgnQpQtFTOGQh_J16IMwDlji18SWQ2PZ6 |
| 阶段 | T3 |
| 工作量 | 60–80 小时 |
| 前置 | MRS I、线代（最小二乘） |

### 内容

由滤波方法转向基于优化的现代 SLAM 方法。

| 模块 | 内容 |
|---|---|
| 最小二乘 | 线性与非线性最小二乘、Gauss-Newton、LM |
| 图优化 | 因子图、节点与边、稀疏结构、求解器（g2o/GTSAM 概念） |
| 位姿图 | 位姿图优化、信息矩阵、初始化 |
| Graph SLAM | 完整图 SLAM、前端与后端、稀疏化 |
| 回环检测 | 外观回环（词袋）、几何验证、鲁棒核函数 |
| 3D SLAM | 点云配准 ICP、NDT、LiDAR SLAM 架构（LOAM 类） |
| 建图表达 | 栅格、特征地图、surfel、TSDF |

### 作业与产出

- 用 Gauss-Newton 实现二维位姿图优化
- 实现回环检测与后端优化，运行公开数据集（如 Intel 数据集）

### 能力目标

- 能写出位姿图的误差函数与雅可比
- 能说明 SLAM 后端的稀疏结构及其来源
- 能区分前端（配准与跟踪）与后端（优化）的职责
- 能运行 LiDAR SLAM，并定位其漂移来源

### 参考

- 书：《Probabilistic Robotics》第 11 章、Stachniss 的 SLAM 课程讲义
- 代码：g2o、GTSAM、Cartographer（架构）、LIO-SAM（LiDAR）
- 论文：Grisetti, "A Tutorial on Graph-Based SLAM"

### 注意事项

- 角度优化应在旋转矩阵或李代数上完成，避免直接优化欧拉角
- 信息矩阵为协方差的逆，写法错误会使优化方向相反
- 回环误匹配的影响大于漏检，需用鲁棒核抑制假阳性

---

## 3. 与后续课程的关系

```
MRS I（滤波、定位、建图）
      ↓
MRS II（优化、位姿图、Graph SLAM）
      ↓
Vision Algorithms（视觉前端：VO）
      ↓
MIT VNAV（因子图统一处理，理论闭环）
      ↓
Underactuated（状态已知后的控制）
```

- MRS I 的覆盖范围为定位与二维建图，可支撑课程项目
- MRS II 覆盖 SLAM 后端，是机器人感知岗位的基本要求
- Vision Algorithms 与 VNAV 默认已具备最小二乘与图优化基础
