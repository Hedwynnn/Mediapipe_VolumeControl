# MediaPipe Volume Control

一个用手势控制 Windows 系统音量的简单 Python 实验项目。

项目通过摄像头获取画面，使用 MediaPipe 识别手部关键点，并根据拇指和食指之间的距离调整 Windows 主音量。实时画面会显示手部骨架、当前音量和 FPS。

> 这是 2021 年的学习项目，现作为历史记录保留，不再主动维护。

## 功能

- 使用 MediaPipe Hands 检测手部关键点。
- 通过拇指和食指的张合调整 Windows 系统音量。
- 在摄像头画面中显示手势连线、音量条和帧率。
- 提供独立的关键点坐标调试脚本。

## 环境要求

- Windows
- Python 3
- 可用的摄像头
- OpenCV
- MediaPipe
- NumPy
- pycaw
- comtypes

安装依赖：

```bash
pip install opencv-python mediapipe numpy pycaw comtypes
```

## 使用方法

启动手势音量控制：

```bash
python VolumeHandControl.py
```

将手放在摄像头前，改变拇指与食指之间的距离，即可调整系统主音量。要结束运行，请在终端中中止程序。

如果只想查看手部关键点坐标：

```bash
python position.py
```

`position.py` 会在终端输出关键点编号与坐标，按 `Q` 退出。

## 文件说明

- `VolumeHandControl.py`：手势音量控制主程序。
- `HandTrackingMoudle.py`：对 MediaPipe 手部检测的简单封装。文件名保留了早期项目中的原始拼写。
- `position.py`：用于查看和输出手部关键点坐标。

## 说明

项目直接调用 Windows Core Audio 接口，不适用于 macOS 或 Linux。现代版本的 MediaPipe、OpenCV 或 pycaw 可能与 2021 年的 API 有所差异，运行时可能需要使用与当时相近的依赖版本。

MediaPipe Hands 参考资料：<https://ai.google.dev/edge/mediapipe/solutions/vision/hand_landmarker>
