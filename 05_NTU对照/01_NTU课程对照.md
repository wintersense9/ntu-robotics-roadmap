# NTU 课程与本课程体系的对应关系

本页用于同时修读 NTU MSc (Robotics & Intelligent Systems) 的情况，说明哪些课程内容重叠、哪些需要补充，以及顺序安排。

---

## 1. NTU 课程结构

MAE 学院开设的授课型硕士，30 AU 纯课程（默认 Option 2）或 24 AU 加论文（Option 1）。课程分为 Core、Group A（规定选修）、Group B（一般选修）与 Group C（实践）。

| 类别 | 课程 | 内容 |
|---|---|---|
| Core | MA6210 Introduction to Advanced Robotics and Autonomous Systems | 领域导论 |
| Core | MA6121 Applied Mathematics for Engineering | 线代、PDE、数值方法 |
| Group A | MA6211 AI and ML Fundamentals for Robotics | 机器学习入门 |
| Group A | MA6212 Robotics Manipulation and Advanced Control | 机械臂与高级控制 |
| Group A | MA6213 Sensors and Data Fusion | 状态估计 |
| Group A | MA6214 Autonomous Mobile Robot | 定位、建图、规划、控制 |
| Group A | MA6216 Vision | 传统视觉与物理原理 |
| Group A | MA6217 Advanced Linear Systems and Control | 状态空间、LQR、观测器 |
| Group B | MA6220 Metaverse and Digital Twin | 数字孪生 |
| Group B | MA6221 Medical and Healthcare Robotics | 医疗机器人 |
| Group B | MA6223 Human-Robot Interaction | 人机交互与人体神经力学 |
| Group B | MA6224 Unmanned Vehicles | 无人机、无人船 |
| Group B | MA6501 Manufacturing Control and Automation | 工业控制与产线 |
| Group C | MA6215 Robotics Projects / MA6788 Independent Study | 项目、独立研究 |

---

## 2. 课程对应表

| 本体系课程 | 对应 NTU 课 | 关系 | 用途 |
|---|---|---|---|
| Modern C++ for CV | 无 | NTU 无编程课 | 提供作业所需的编程能力 |
| Photogrammetry I/II | MA6216 Vision 部分章节 | 补充三维重建与 BA | 在 MA6216 之前学习 |
| Multiview Geometry | MA6216 的几何部分 | 深度超出 | 几何方向的深入内容 |
| Mobile Robotics & Sensing I | MA6213、MA6214 | 高度重叠 | 作为两门课的预习或复习 |
| Mobile Robotics & Sensing II | MA6214 后半 | 补充图优化 SLAM | 覆盖 MA6214 未涉及的部分 |
| Vision Algorithms | MA6214、MA6216 | 补充视觉里程计 | 编程训练 |
| TUM 实践课 | MA6215 Robotics Projects | 同类 | 二选一 |
| EECS498 | MA6211 | 深度远超 MA6211 | 建立模型实现能力 |
| 3D Scanning | MA6220 部分内容 | 数字孪生的技术基础 | 选学 |
| MIT VNAV | MA6213、MA6224 | 优化视角更完整 | 研究或自动驾驶方向 |
| Underactuated | MA6212、MA6217 | 动力学与最优控制 | 控制方向 |
| Convex Optimization | 无 | NTU 无优化课 | SLAM 与 MPC 所需 |

---

## 3. NTU 的覆盖范围与本体系的补充

### NTU 覆盖较完整的部分

1. 控制与机构：MA6212 与 MA6217 体系完整，配有作业与考试。
2. 传感与状态估计：MA6213 含实验环节。
3. 系统集成：具备真机与实验平台。
4. 导师与实验室资源：RRC 与 Independent Study 通道。

### 本体系补充的部分

1. 编程工程能力：C++ 与 ROS 的系统训练（Modern C++、项目课）。
2. 深度学习深度：MA6211 仅覆盖入门内容（EECS498）。
3. 最优化：NTU 无对应课程（Convex Optimization）。
4. SLAM 深度：MA6214 覆盖应用层面（MRS II、VNAV）。
5. 生成模型与世界模型：两套体系均未覆盖，需另行补充。

---

## 4. 在读期间的安排

| 学期 | NTU 课程 | 并行自学（每周 6–8 h） |
|---|---|---|
| 第 1 学期 | MA6210、MA6121、MA6213 | Modern C++（前 8 讲）、18.06 复习 |
| 第 1 学期末 | — | 联系导师，确认 Independent Study 可行性 |
| 第 2 学期 | MA6214、MA6216、MA6212 | MRS II（图优化）、Photogrammetry I |
| 假期 | — | Vision Algorithms（集中 4–6 周） |
| 第 3 学期 | 选修与项目 | EECS498（跨两个学期） |
| 第 4 学期 | Option 1 论文或课程收尾 | VNAV 与 Underactuated 二选一 |

安排原则：避免与 NTU 课程内容重复。MA6214 已覆盖定位与建图时，直接从 MRS II 的图优化部分开始；MA6216 已覆盖相机模型时，从 Photogrammetry I 的特征匹配部分开始。

---

## 5. 两者的关系

NTU 提供学位、真机平台与导师资源；本体系提供课程深度与编程训练量。单独完成 NTU 课程时，概念覆盖较全但系统实现经验有限；单独完成本体系时，代码经验充足但缺少真机与项目背景。
