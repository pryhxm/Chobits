# Chobits

这是一个牛逼的机器人🤖

## 代码结构

Chobits 按照机器人身体结构来组织工程目录，方便把仿真、机械、AI、硬件和运动控制分开演进。

- `avatar/`：机器人仿真相关内容，后续可以存放基于 Gazebo 的仿真世界、模型、传感器配置和仿真启动文件。
- `bones/`：机械设计相关内容，用于存放结构设计、装配资料、CAD 文件、加工图纸和机械约束说明。
- `brain/`：AI 相关内容，用于存放感知、决策、学习、推理和高层任务规划代码。
- `muscles/`：执行器和底层硬件相关内容，用于存放电机驱动、硬件接口、单片机固件和底层控制程序。
- `spine/`：整体运动控制相关内容，用于存放基于 ROS 的运动控制、运动规划、控制器编排、消息接口和系统启动配置。
- `docs/`：项目文档、设计记录和调研资料。
- `scripts/`：开发、构建、部署和辅助脚本。
- `tests/`：测试代码和验证用例。

## Git LFS

所有大于 `50 MB` 的文件都必须使用 Git LFS 管理，尤其是 CAD 文件、仿真资源、模型权重、数据集、图片、视频、日志包和固件产物等二进制或大体积文件。

首次使用前安装并初始化 Git LFS：

```bash
git lfs install
```

按文件类型跟踪大文件，例如：

```bash
git lfs track "*.stl"
git lfs track "*.step"
git lfs track "*.onnx"
git lfs track "*.pt"
git lfs track "*.bag"
```

提交时需要把 `.gitattributes` 和实际文件一起提交：

```bash
git add .gitattributes path/to/large-file
git commit -m "Add large asset with Git LFS"
```
