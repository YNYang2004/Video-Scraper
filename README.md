# 🎬 HD Video Scraper

English | [中文说明](./README_ZH.md)

An efficient video downloading solution based on Python and PyQt6, supporting HD resource extraction from Bilibili, YouTube, and other mainstream platforms. It features intelligent playlist parsing, multi-part video recognition, and a user-friendly GUI.

---

## 🚀 Quick Start (For .exe Users)

If you are using the pre-compiled version from the **Release** page, follow these steps:

### 1. Prerequisite: FFmpeg

* **Why it's needed**: High-quality videos (1080P/4K) often store video and audio in separate streams. **FFmpeg** is required to merge them into a single MP4 file.
* **Setup**: Download `ffmpeg.exe` and place it in the same folder as the application, or add it to your system's `PATH`.

### 2. Cookies (Optional but Recommended)

* To download **4K/8K** videos or **Member-only** content, you need to provide your account cookies.
* Place your `cookies.txt` (Netscape format) in the application folder. The program will auto-load it on startup.

### 3. Usage Steps

1. **Launch**: Double-click `video_scraper_en.exe`.
2. **Analyze**: Paste a video or playlist URL and click **"Analyze"**.
3. **Select**:
* Use the **"Select All"** button for batch tasks.
* **Pro Tip**: Highlight multiple items with `Shift/Ctrl` and press **Space** to toggle their check states simultaneously.


4. **Download**: Click **"Download Selected"**.

---

## 🛠️ Developer Deployment (Python Source)

If you want to run the code from the source or modify it, follow these instructions:

### 1. Environment Setup

* **Python**: Version 3.8 or higher is required.
* **Install Dependencies**:
```bash
pip install -r requirements.txt

```


This will install `yt-dlp` (the download engine) and `PyQt6` (the UI framework).

### 2. Running the App

```bash
python video_scraper_en.py

```

### 3. Build Your Own .exe

Use **PyInstaller** to package the script:

```bash
pip install pyinstaller
pyinstaller --noconsole --onefile --name "HD_Video_Scraper_EN" video_scraper_en.py

```

---

## 🔑 Key Features & Configurations

### Smart Cookie Conversion

The program includes a built-in logic to handle modern browser cookie formats. If you provide a **JSON** format cookie file, the app will automatically convert it to the required **Netscape** format.

### Network Proxy

For users accessing region-restricted content (e.g., YouTube), you can enable the **"Proxy"** option in the UI.

* **Format**: `http://127.0.0.1:1080` or `socks5://127.0.0.1:1080`.
* Your proxy settings are automatically saved for future sessions.

---

## 📂 Project Structure

* `video_scraper_en.py`: Main program with English UI.
* `video_scraper_zh.py`: Main program with Chinese UI.
* `requirements.txt`: List of required Python packages.
* `downloads/`: Default directory for saved videos.

---

## ⚠️ Disclaimer

This tool is for educational and research purposes only. Please respect the copyright of content creators. Do not use this tool for illegal distribution or commercial gain.