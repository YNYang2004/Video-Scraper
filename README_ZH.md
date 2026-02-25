# 🎬 HD Video Scraper (高清视频下载器) 使用手册
[English Version](./README_EN.md) | 中文说明


本工具是一个基于 Python 开发的高效视频下载解决方案，支持 Bilibili、YouTube 等主流平台的高清资源抓取。它具备强大的列表解析能力，能够自动识别多 P 视频、UGC 合集及播放列表。

---

## 🚀 快速上手 (发布版 .exe 用户)

如果您是从 Release 页面下载的已打包版本，请按以下步骤操作：

### 1. 环境准备

* **安装 FFmpeg (核心步骤)**：由于高质量视频的音视频流通常是分离的，本程序依赖 FFmpeg 进行合并。
* **Windows**: 下载 `ffmpeg.exe`，建议将其放置在程序同级目录下，或添加到系统环境变量 `Path` 中。


* **放置 Cookie**: 如果您有大会员或需要下载高清画质，请将导出的 `cookies.txt` 放在程序同一文件夹内。

### 2. 使用流程

1. **运行程序**：双击运行 `video_scraper_zh.exe`。
2. **输入链接**：将视频或合集链接粘贴至 URL 输入框。
3. **解析与预览**：点击“解析链接”，程序将抓取封面、标题及分集列表。
4. **批量勾选**：
* 使用“全选/取消全选”按钮。
* **进阶操作**：按住 `Shift` 或 `Ctrl` 选中多项，按 **空格键** 即可同步切换所有选中项的勾选状态。


5. **开始下载**：设置好保存目录后，点击“下载选中视频”。

---

## 🛠️ 开发者部署 (Python 环境运行)

如果您希望直接运行源代码或进行二次开发，请参考以下部署流程：

### 1. 源码结构

* `video_scraper_zh.py`: 中文界面主程序。
* `video_scraper_en.py`: 英文界面主程序。
* `requirements.txt`: Python 依赖项列表。

### 2. 环境搭建

1. **安装 Python**: 建议版本为 3.8 或以上。
2. **安装依赖库**:
在项目根目录打开终端，执行以下命令安装必要的 GUI 框架和下载引擎：
```bash
pip install -r requirements.txt

```


该指令会自动安装 `yt-dlp` (下载核心) 和 `PyQt6` (界面框架)。

### 3. 运行程序

```bash
python video_scraper_zh.py

```

---

## 📦 打包指南 (PyInstaller)

如果您修改了代码并想重新打包为 `.exe`，可以使用以下建议指令：

```bash
# 建议安装 pyinstaller
pip install pyinstaller

# 执行打包命令
pyinstaller --noconsole --onefile --name "HD_Video_Scraper" --icon="icon.ico" video_scraper_zh.py

```

* `--noconsole`: 运行时不显示黑色命令行窗口。
* `--onefile`: 将所有依赖打包进一个独立的 exe 文件中。

---

## 🔑 关键配置说明

### 关于 Cookie

本程序内置了 **JSON 转 Netscape** 的兼容逻辑。

* **获取方式**：在浏览器安装 `Cookie-Editor` 扩展，登录视频网站后，选择 `Export` -> `Netscape`。
* **自动加载**：程序会记录上次使用的 Cookie 路径，并在启动时尝试自动加载。

### 网络代理

对于需要访问 YouTube 的用户，请勾选“启用代理”并填入您的本地代理地址（如 `http://127.0.0.1:1080` 或 `socks5://127.0.0.1:1080`）。程序会自动保存您的代理配置以便下次使用。

---

## 📂 项目清单

| 文件名 | 用途 |
| --- | --- |
| `video_scraper_zh.py` | 具备完整中文交互逻辑的主程序文件 |
| `requirements.txt` | 定义了运行所需的 `yt-dlp` 和 `PyQt6` 版本 |
| `cookies.txt` | 存放身份校验信息，用于解锁高清画质 |
| `downloads/` | 默认的视频文件存储位置 |

---

## ⚠️ 注意事项

* **版权申明**：本工具仅限个人学习研究使用，请勿用于非法抓取及商业获利。
* **画质限制**：部分 4K 或 8K 资源需要对应的 Cookie 权限方可解析最高画质。