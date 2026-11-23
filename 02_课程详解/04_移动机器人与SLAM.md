# 移动机器人与 SLAM

这一组是机器人方向真正的"专业核心"：**在噪声里估计自己的状态，并同时建出地图**。整个 21 个月里，MRS II 是分水岭——从这里开始，你才真正在写 SLAM 系统，而不是在调用现成库。

---

## 1. Mobile Robotics and Sensing I

| 项目 | 内容 |
|---|---|
| 学校 / 讲者 | University of Bonn / Cyrill Stachniss |
| 页面 | https://www.youtube.com/playlist?list=PLgnQpQtFTOGQEn33QDVGJpiZLi-SlL7vA |
| 学期 | T2 |
| 工作量 | 50–70 小时 |
| 前置 | 概率论基础、线代、Python |

### 讲什么

概率机器人（Probabilistic Robotics）的前半本书。

| 模块 | 内容 |
|---|---|
| 不确定性 | 为什么机器人问题本质是概率问题、高斯表示、协方差 |
| 贝叶斯滤波 | 递归贝叶斯更新、预测/校正两步 |
| 卡尔曼滤波 | KF、EKF 的线性化、雅可比、协方差传播 |
| 其他高斯滤波 | 信息滤波、无迹卡尔曼（UKF） |
| 非参数滤波 | 粒子滤波、重采样、粒子退化 |
| 定位 | 马尔可夫定位、蒙特卡洛定位（AMCL） |
| 占据栅格建图 | 逆传感器模型、log-odds 更新、栅格地图 |
| 传感器 | 轮式里程计、IMU、2D/3D LiDAR、RGB-D 的噪声模型 |

### 作业与产出

- 实现 EKF 做一维/二维定位，画出协方差椭圆
- 实现粒子滤波定位（蒙特卡洛），对比粒子数对精度的影响
- 实现占据栅格建图

### 怎么算学会

- 能写出 EKF 的五个公式并解释每一项；
- 能说清"粒子滤波什么时候比 EKF 好，代价是什么"；
- 能给一个激光雷达建出占据栅格图并解释 log-odds。

### 配套

- 书：《Probabilistic Robotics》Thrun, Burgard, Fox（必读，第 2–9 章）
- 代码：PythonRobotics（定位/建图部分）

### 坑

- 协方差矩阵必须是正定的，数值上要用 Joseph 形式更新。
- 里程计模型的角度归一化（-π, π）写错会导致定位发散。
- 粒子滤波的"有效粒子数"要监控，不重采样会退化。

---

## 2. Mobile Robotics and Sensing II

| 项目 | 内容 |
|---|---|
| 学校 / 讲者 | University of Bonn / Cyrill Stachniss |
| 页面 | https://www.youtube.com/watch?v=mQvKhmWagB4&list=PLgnQpQtFTOGQh_J16IMwDlji18SWQ2PZ6 |
| 学期 | T3 |
| 工作量 | 60–80 小时 |
| 前置 | MRS I、线代（最小二乘） |

### 讲什么

从滤波走向**优化**：现代 SLAM 的主流做法。

| 模块 | 内容 |
|---|---|
| 最小二乘 | 线性最小二乘、非线性最小二乘、Gauss-Newton、LM |
| 图优化 | 因子图、节点/边、稀疏结构、求解器（g2o/GTSAM 概念） |
| 位姿图 | 位姿图优化、信息矩阵、初始化 |
| Graph SLAM | 完整图 SLAM、前端/后端、稀疏化 |
| 回环检测 | 外观回环（词袋）、几何验证、鲁棒核函数 |
| 3D SLAM | 点云配准 ICP、NDT、LiDAR SLAM 架构（LOAM 类） |
| 建图表达 | 栅格、特征地图、surfel、TSDF |

### 作业与产出

- 实现一个**位姿图优化**：用 Gauss-Newton 解 2D 位姿图
- 实现回环检测 + 后端优化，跑一个公开数据集（如 Intel 数据集）

### 怎么算学会

- 能写出位姿图的误差函数和雅可比；
- 能解释"为什么 SLAM 后端是稀疏的，稀疏性从哪来"；
- 能说清前端（配准/跟踪）和后端（优化）的分工；
- 能跑通一个 LiDAR SLAM 并指出它在哪里漂移。

### 配套

- 书：《Probabilistic Robotics》第 11 章 + Stachniss 的 SLAM 课程讲义
- 代码：g2o、GTSAM、Cartographer（读架构）、LIO-SAM（LiDAR）
- 论文：Grisetti 的 "A Tutorial on Graph-Based SLAM"

### 坑

- 不要在笛卡尔坐标下直接优化角度，用旋转矩阵/李代数。
- 信息矩阵（协方差逆）写反会让优化朝错误方向跑。
- 回环的误匹配比漏检危害大得多，假阳性要用鲁棒核压住。

---

## 3. 这门组课和后面课程的关系

```
MRS I（滤波/定位/建图）
      ↓
MRS II（优化/位姿图/Graph SLAM）
      ↓
Vision Algorithms（视觉前端：VO）
      ↓
MIT VNAV（用因子图统一讲一遍，理论闭环）
      ↓
Underactuated（知道自己在哪之后，怎么控制）
```

- **只学 MRS I**：会做定位和 2D 建图，够做课程项目。
- **学完 MRS II**：能写 SLAM 后端，这是"机器人感知岗"的最低门槛。
- **两门都不学**：后面 Vision Algorithms 和 VNAV 会看不懂，因为它们默认你懂最小二乘和图优化。
