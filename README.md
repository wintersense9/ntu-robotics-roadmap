# 机器人方向课程体系

本仓库整理机器人方向的学习内容与课程安排。课程清单来自 [brunoeducsantos/robotics_master](https://github.com/brunoeducsantos/robotics_master)，该清单把 Bonn、TUM、MIT（以及 UZH、Michigan）的机器人核心课按 7 个阶段组织。本仓库在其基础上补充了每门课的内容拆分、先修要求与作业产出，并附有就业方向与 NTU 课程对照。

---

## 1. 机器人的能力构成

机器人系统的难点集中在四个环节的衔接：感知、状态估计、规划控制、工程实现。四者构成闭环，误差会在闭环中累积，同时对实时性有约束。

| 环节 | 解决的问题 | 相关课程 |
|---|---|---|
| 工程实现 | 算法能否用 C++ 实现并满足实时性 | Modern C++ for Computer Vision |
| 感知（视觉与几何） | 图像如何转换为三维点与位姿 | Photogrammetry I/II、Multiview Geometry、Vision Algorithms |
| 状态估计与建图 | 位姿与环境结构如何在噪声中估计 | Mobile Robotics & Sensing I/II、MIT VNAV |
| 规划与控制 | 已知状态后的运动生成与稳定性 | Convex Optimization、Underactuated Robotics |
| 学习（视觉端） | 语义类问题由神经网络处理 | Deep Learning for CV (EECS498) |

这五项能力不随应用对象改变，移动机器人、机械臂、自动驾驶、无人机使用的都是同一组能力，差别在权重分配：

- 移动机器人、自动驾驶：感知与状态估计占比最高
- 机械臂、腿足机器人：规划与控制占比最高
- 感知算法岗：视觉几何与深度学习占比最高
- 三维重建、数字孪生：视觉几何占比最高

因此课程按依赖关系排列为一条学习序列，不按应用方向拆分。

---

## 2. 课程总表

| 阶段 | 课程 | 学校 / 讲者 |
|---|---|---|
| T1 | [Modern C++ for Computer Vision](https://www.ipb.uni-bonn.de/teaching/cpp-2020/) | Bonn / Cyrill Stachniss |
| T1 | [Photogrammetry I](https://www.ipb.uni-bonn.de/photo12-2021/) | Bonn / Cyrill Stachniss |
| T2 | [Mobile Robotics and Sensing I](https://www.youtube.com/playlist?list=PLgnQpQtFTOGQEn33QDVGJpiZLi-SlL7vA) | Bonn / Cyrill Stachniss |
| T2 | [Photogrammetry II](https://www.ipb.uni-bonn.de/photo12-2021/) | Bonn / Cyrill Stachniss |
| T3 | [Mobile Robotics and Sensing II](https://www.youtube.com/watch?v=mQvKhmWagB4&list=PLgnQpQtFTOGQh_J16IMwDlji18SWQ2PZ6) | Bonn / Cyrill Stachniss |
| T3 | [Multiview Geometry](https://cvg.cit.tum.de/teaching/ss2019/mvg2019) | TUM / Daniel Cremers |
| T4 | [Vision Algorithms for Mobile Robotics](https://rpg.ifi.uzh.ch/teaching.html) | UZH / Davide Scaramuzza |
| T4 | [Project: 视觉导航实践](https://cvg.cit.tum.de/teaching/ws2020/visnav_ws2020#lectures) | TUM |
| T5 | [Practical Course: Vision-based Navigation](https://cvg.cit.tum.de/teaching/ws2021/visnav_ws2021) | TUM |
| T5 | [Deep Learning for Computer Vision (EECS498)](https://web.eecs.umich.edu/~justincj/teaching/eecs498/WI2022/schedule.html) | Michigan / Justin Johnson |
| T6 | [3D Scanning and Motion Capture](https://www.cs.cit.tum.de/cg/teaching/winter-term-2122/3d-scanning-motion-capture/) | TUM / Matthias Niessner |
| T6 | Deep Learning for Computer Vision（续） | Michigan / Justin Johnson |
| T7 | [Visual Navigation for Autonomous Vehicles (VNAV)](https://vnav.mit.edu/) | MIT / Luca Carlone |
| T7 | [Underactuated Robotics](https://underactuated.csail.mit.edu/index.html) | MIT / Russ Tedrake |
| 备选 | [Convex Optimization](https://www.edx.org/course/convex-optimization) | Stanford / Stephen Boyd |
| 前置 | [18.06 Linear Algebra](https://ocw.mit.edu/courses/18-06-linear-algebra-spring-2010/)、[微积分](https://www.youtube.com/watch?v=f0BxAtprWts)、[PyTorch 入门](https://learn.microsoft.com/en-us/training/paths/pytorch-fundamentals/) | MIT / Microsoft |

各门课的内容模块、先修要求与作业见 `02_课程详解/`。

---

## 3. 文件结构

| 文件 | 内容 |
|---|---|
| [01_课程总表/01_课程总表.md](01_课程总表/01_课程总表.md) | 课程依赖关系、工作量、产出汇总 |
| [02_课程详解/01_编程与数学基础.md](02_课程详解/01_编程与数学基础.md) | Modern C++、18.06 线代、微积分、PyTorch |
| [02_课程详解/02_视觉几何与三维重建.md](02_课程详解/02_视觉几何与三维重建.md) | Photogrammetry I/II、Multiview Geometry、3D Scanning |
| [02_课程详解/03_深度学习视觉.md](02_课程详解/03_深度学习视觉.md) | EECS498 内容与作业 |
| [02_课程详解/04_移动机器人与SLAM.md](02_课程详解/04_移动机器人与SLAM.md) | Mobile Robotics and Sensing I/II |
| [02_课程详解/05_视觉导航.md](02_课程详解/05_视觉导航.md) | Vision Algorithms、TUM 实践课、MIT VNAV |
| [02_课程详解/06_控制与优化.md](02_课程详解/06_控制与优化.md) | Convex Optimization、Underactuated Robotics |
| [03_就业方向/01_就业方向.md](03_就业方向/01_就业方向.md) | 岗位分类、技能要求、面试内容、行业与薪资 |
| [04_工具链/01_工具链与仿真环境.md](04_工具链/01_工具链与仿真环境.md) | 按课程阶段的环境配置 |
| [05_NTU对照/01_NTU课程对照.md](05_NTU对照/01_NTU课程对照.md) | NTU MSc 与本课程体系的对应关系 |

---

## 4. 使用方式

1. 先完成先修内容：18.06 线代、Python、基础 C++。缺少这部分时，Modern C++ 课程会停留在语法层面，几何内容难以展开。
2. 按依赖顺序推进：Modern C++ → Photogrammetry I → MRS I → Multiview Geometry → Vision Algorithms → EECS498 → VNAV → Underactuated。控制与优化课程可在后期并行。
3. 同一时间只开一门主课。Bonn 的 C++ 与 Photogrammetry 作业量较大，多门并行会导致进度停留在观看视频。
4. 每门课的产出为代码与结论说明两部分，仅有可运行的 demo 不计入完成。
5. 就业方向与岗位所需能力见 `03_就业方向/`。

---

## 5. 适用范围

- 原仓库为课程链接汇总，不提供证书、作业答案与助教支持。多数课程为往年学期页面，视频存在失效可能，讲义 PDF 通常仍可访问。
- 本课程体系以几何、视觉、状态估计与控制为主线，属于机器人系统工程的经典路径。大模型、VLA、具身智能、强化学习工程、嵌入式 MCU/RTOS 等内容不在此范围内。
- 完成后的能力范围：能够读懂 ICRA/IROS/CoRL 中感知与导航方向的论文，能够用 C++/Python 复现视觉里程计或 SLAM 系统，能够定位系统中的主要误差来源。不包含训练通用机器人基础模型的能力。
