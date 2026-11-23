# 机器人方向怎么学：一套 21 个月的课程表

> 这个仓库只做一件事：**把"做机器人"这件事讲清楚，并给出一门一门具体的课**。
>
> 课程来源：[brunoeducsantos/robotics_master](https://github.com/brunoeducsantos/robotics_master) —— 把 Bonn、TUM、MIT（以及 UZH、Michigan）的机器人核心课拼成一个 21 个月、7 个 trimester 的学习计划。本仓库在此基础上补了每门课的**内容拆解、前置要求、作业产出、验收标准**，并对照了 NTU MSc (Robotics & Intelligent Systems) 的课程设置。

---

## 一、先搞清楚：机器人方向到底在学什么

很多人以为机器人 = 深度学习 + 机械臂。真正难的是**把感知、状态估计、规划控制、工程实现四件事串成一个闭环**，而且误差会累积、传感器会坏、实时性会卡。

| 能力支柱 | 回答的问题 | 对应课程 |
|---|---|---|
| **① 工程实现** | 能不能用 C++ 把算法写出来、跑到实时 | Modern C++ for Computer Vision |
| **② 感知（视觉/几何）** | 相机拍到的东西，怎么变成 3D 点和位姿 | Photogrammetry I/II、Multiview Geometry、Vision Algorithms |
| **③ 状态估计与建图** | 机器人在哪、周围长什么样、怎么在噪声里估出来 | Mobile Robotics & Sensing I/II、MIT VNAV |
| **④ 规划与控制** | 知道在哪之后，怎么动、怎么稳、怎么最优 | Convex Optimization、Underactuated Robotics |
| **⑤ 学习（视觉端）** | 传统几何做不了的语义问题交给神经网络 | Deep Learning for CV (EECS498) |

这五根支柱不分方向——**做移动机器人、做机械臂、做自动驾驶、做无人机，用的都是这五根**。区别只是配比：
- 移动机器人/自动驾驶：②③ 权重最高
- 机械臂/腿足：④ 权重最高
- 感知算法岗：②⑤ 权重最高
- 三维重建/数字孪生：② 权重最高

所以本仓库**不按方向拆课**，而是按「由浅入深、前后依赖」排成一条线。

---

## 二、21 个月课程总表（一眼看全）

| 学期 | 课程 | 学校 / 讲者 |
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

每门课"讲什么、前置是什么、作业是什么、怎么算学会"写在 `02_课程详解/` 里。

---

## 三、文件地图

| 文件 | 内容 |
|---|---|
| [01_课程总表/01_21个月课程总表.md](01_课程总表/01_21个月课程总表.md) | 全部课程逐门表：先修关系、工作量、产出 |
| [02_课程详解/01_编程与数学基础.md](02_课程详解/01_编程与数学基础.md) | Modern C++、18.06 线代、微积分、PyTorch |
| [02_课程详解/02_视觉几何与三维重建.md](02_课程详解/02_视觉几何与三维重建.md) | Photogrammetry I/II、Multiview Geometry、3D Scanning |
| [02_课程详解/03_深度学习视觉.md](02_课程详解/03_深度学习视觉.md) | EECS498 全课拆解 |
| [02_课程详解/04_移动机器人与SLAM.md](02_课程详解/04_移动机器人与SLAM.md) | Mobile Robotics and Sensing I/II |
| [02_课程详解/05_视觉导航.md](02_课程详解/05_视觉导航.md) | Vision Algorithms、TUM 实践课、MIT VNAV |
| [02_课程详解/06_控制与优化.md](02_课程详解/06_控制与优化.md) | Convex Optimization、Underactuated Robotics |
| [03_学习节奏/01_21个月排期.md](03_学习节奏/01_21个月排期.md) | 每周投入、每学期任务、里程碑 |
| [03_学习节奏/02_课程验收标准.md](03_学习节奏/02_课程验收标准.md) | 每门课"学完"的客观判据 |
| [04_工具链/01_工具链与仿真环境.md](04_工具链/01_工具链与仿真环境.md) | Ubuntu/ROS2/OpenCV/Eigen/GTSAM/仿真器 |
| [05_NTU对照/01_NTU课程对照.md](05_NTU对照/01_NTU课程对照.md) | NTU MSc 课程 vs 这套课，怎么互补 |
| [05_NTU对照/02_申请要点与时间线.md](05_NTU对照/02_申请要点与时间线.md) | 若同时申请 NTU：材料与倒排时间 |

---

## 四、怎么用

1. **先补前置**：线性代数（18.06 前 18 讲）+ Python + 一点 C++。不补直接上 Modern C++ 会卡在语法而不是几何。
2. **一次只开一门**。这套课作业量很大（Bonn 的 C++ 和 Photogrammetry 都是大量编程作业），同时开三门的结果是"看过 = 学会"。
3. **按依赖顺序走**：Modern C++ → Photogrammetry I → MRS I → Multiview Geometry → Vision Algorithms → EECS498 → VNAV → Underactuated。控制/优化可以并行插在后期。
4. **每门课都要交东西**：跑通一个 demo 不算，要产出代码 + 一段能讲清楚的结论（见验收标准）。
5. **建议每周 10–12 小时**，21 个月约 900–1000 小时，正好是一套硕士课程的量。

---

## 五、几句实话

- 原 repo 只是**链接聚合**：不给证书、不给作业答案、没有助教。视频多是往年学期，部分可能失效，但讲义 PDF 一般还在。
- 这套课偏**几何 + 视觉 + 状态估计 + 控制**，是"机器人系统工程"的经典路线；**几乎不覆盖**大模型、VLA、具身智能、强化学习工程、嵌入式 MCU/RTOS。这些要另找资源。
- 学完的合理预期：能读懂 ICRA/IROS/CoRL 的感知与导航论文，能用 C++/Python 复现一个视觉里程计或 SLAM 系统，能解释清楚"误差从哪来"。不是"能训一个通用机器人基础模型"。
