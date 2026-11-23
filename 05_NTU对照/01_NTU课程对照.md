# NTU 课程 vs 这套课

如果你同时在上/要上 NTU 的 MSc (Robotics & Intelligent Systems)，这一页解决一个问题：**哪些课可以不看，哪些必须补，顺序怎么排。**

---

## 1. NTU 课程结构（一句话版）

MAE 学院开的授课型硕士，30 AU 纯课程（默认 Option 2）或 24 AU + 论文（Option 1）。课程分 Core、Group A（规定选修）、Group B（一般选修）、Group C（实践）。

| 类别 | 课程 | 一句话 |
|---|---|---|
| Core | MA6210 Introduction to Advanced Robotics and Autonomous Systems | 全景导论，见导师的窗口 |
| Core | MA6121 Applied Mathematics for Engineering | 线代 + PDE + 数值方法 |
| Group A | MA6211 AI and ML Fundamentals for Robotics | 机器学习入门（深度有限） |
| Group A | MA6212 Robotics Manipulation and Advanced Control | 机械臂 + 高级控制 |
| Group A | MA6213 Sensors and Data Fusion | 状态估计，被低估的一门 |
| Group A | MA6214 Autonomous Mobile Robot | 定位/建图/规划/控制浓缩版 |
| Group A | MA6216 Vision | 传统视觉 + 物理原理 |
| Group A | MA6217 Advanced Linear Systems and Control | 状态空间、LQR、观测器 |
| Group B | MA6220 Metaverse and Digital Twin | 数字孪生 |
| Group B | MA6221 Medical and Healthcare Robotics | 医疗机器人 |
| Group B | MA6223 Human-Robot Interaction | 人机交互 + 神经力学 |
| Group B | MA6224 Unmanned Vehicles | 无人机 / 无人船 |
| Group B | MA6501 Manufacturing Control and Automation | 工控 / 产线 |
| Group C | MA6215 Robotics Projects / MA6788 Independent Study | 项目 / 独立研究 |

---

## 2. 对照表：这套课覆盖了 NTU 的哪些部分

| 本仓库课程 | 对应 NTU 课 | 关系 | 建议 |
|---|---|---|---|
| Modern C++ for CV | 无 | NTU 没有编程课 | **必学**，否则作业写不动 |
| Photogrammetry I/II | MA6216 Vision 部分章节 | 补 3D 重建与 BA | 上 MA6216 前先看 I |
| Multiview Geometry | MA6216 的几何部分 | 深度超出 | 想深挖几何再学 |
| Mobile Robotics & Sensing I | MA6213 + MA6214 | 高度重叠 | 当这两门的预习/复习 |
| Mobile Robotics & Sensing II | MA6214 后半 | 补图优化 SLAM | **必学**，MA6214 深度不够 |
| Vision Algorithms | MA6214 + MA6216 | 补视觉里程计 | **必学**，代码量大 |
| TUM 实践课 | MA6215 Robotics Projects | 同类，可替代 | 二选一 |
| EECS498 | MA6211 | 远超 MA6211 | **必学**，MA6211 只够建立术语 |
| 3D Scanning | MA6220（部分） | 数字孪生的技术底座 | 选学 |
| MIT VNAV | MA6213 + MA6224 | 优化视角更硬 | 想读博/做自驾必学 |
| Underactuated | MA6212 + MA6217 | 动力学 + 最优控制 | 控制方向必学 |
| Convex Optimization | 无 | NTU 没有优化课 | **必学**，SLAM/MPC 都要 |

---

## 3. NTU 的强项与缺口

### 强项（这套课补不了的）
1. **控制与机构**：MA6212 + MA6217，比任何网课都系统，且有大作业和考试逼你学。
2. **传感与状态估计**：MA6213 质量高，有实验。
3. **系统集成**：MAE 的天然优势，能摸到真机。
4. **导师与实验室**：RRC 的资源和 Independent Study 机会。

### 缺口（这套课来补）
1. **编程工程能力**：没有 C++/ROS 系统训练 → Modern C++ + 项目课。
2. **深度学习深度**：MA6211 只到入门 → EECS498。
3. **优化课**：完全没有 → Convex Optimization。
4. **SLAM 深度**：MA6214 只到"会用什么"，不到"能写什么" → MRS II + VNAV。
5. **生成模型/世界模型**：完全没有 → 本仓库也不覆盖，需另找资源。

---

## 4. 如果 NTU 在读，怎么排

| 学期 | NTU 课 | 并行自学（每周 6–8 h） |
|---|---|---|
| 第 1 学期 | MA6210、MA6121、MA6213 | Modern C++（前 8 讲）+ 18.06 复习 |
| 第 1 学期末 | — | 联系导师，问能否做 Independent Study |
| 第 2 学期 | MA6214、MA6216、MA6212 | MRS II（图优化）+ Photogrammetry I |
| 假期 | — | Vision Algorithms（集中 4–6 周） |
| 第 3 学期 | 选修 + 项目 | EECS498（跨两个学期慢推） |
| 第 4 学期 | Option 1 论文 / 纯课程收尾 | VNAV 或 Underactuated 二选一 |

**原则**：不要在 NTU 课上重复学同一门的内容。MA6214 讲了定位建图，你就直接跳到 MRS II 的图优化部分；MA6216 讲了相机模型，你就从 Photogrammetry I 第 4 讲（特征匹配）开始。

---

## 5. 一句话结论

把 NTU 当**骨架 + 真机 + 导师**，把本仓库这套 Bonn/TUM/MIT 课当**深度 + 代码量**。只上 NTU，你会知道很多概念但写不出系统；只刷网课，你会写代码但没有真机和项目背书。
