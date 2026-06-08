# AGENTS.md — ROS 2 书籍配套代码

## 目录结构

- **不是一个统一的工作空间。** 第2–10章各自有独立的 ROS 2 工作空间，位于 `chaptX/chaptX_ws/`（或 `topic_ws`、`topic_practice_ws`、`fishbot_ws`）。
- **chapt1/** — 独立的 CMake/C++ 示例（不含 ROS）。直接用 `cmake` + `make` 构建。
- **工作空间外的独立目录：** `chapt5/learn_git/`、`chapt5/rosbag2_*`、`chapt8/learn_pluginlib/`、`chapt10/rosbag2_message_filter/`。
- 每个工作空间下有 `src/`，包含一个或多个 ROS 2 包（C++ 用 `ament_cmake`，Python 用 `ament_python`）。

## ROS 2 版本

- **Humble**（路径 `/opt/ros/humble/`）。使用前务必 source：`source /opt/ros/humble/setup.bash`

## 构建与测试（每个工作空间独立执行）

```bash
cd chaptX/chaptX_ws/
colcon build
colcon test
```

- C++ 代码检查：`ament_lint_auto` / `ament_lint_common`（开启 `BUILD_TESTING` 时启用）
- Python 代码检查：`ament_flake8`、`ament_pep257`、`pytest`
- `.gitignore` 已排除 `install/`、`build/`、`log/` 等标准 colcon 产物。

## 本仓库说明

书籍 **《ROS 2 机器人开发：从入门到实践》**（fishros / mzebra）的配套代码。README 为中英双语。无 CI/CD、无 GitHub Actions、无 Docker（cpp-httplib 目录下的测试文件除外）。
