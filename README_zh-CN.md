原始版本來自凱文大叔AI程式設計教室
https://www.youtube.com/watch?v=wQDd0vq0I8I
凱文大叔免費去(換)水印工具:
https://kevintsai1202.github.io/GeminiWatermarkRemove/

# Gemini Watermark Remover

[![License: MIT](https://img.shields.io/badge/License-MIT-yellow.svg)](https://opensource.org/licenses/MIT)

[English](README.md) | [正體中文](README_zh-TW.md) | [殘體中文](README_zh-CN.md) | [日本語](README_ja.md) | [韓國語](README_ko.md)

这是一个强大的网页工具，专门设计用于去除由 Google Gemini 生成图片中的水印。此工具完全在浏览器端运行，无需将图片上传至服务器，确保您的隐私安全。

## ✨ 主要功能

- **🚫 自动去除水印**：利用逆向 Alpha 混合算法（Reverse Alpha Blending），精确还原被水印覆盖的像素。
- **🎨 自定义 Logo 替换**：上传您的 Logo 图片，取代原本水印位置，并可调整透明度（0% ~ 100%）及大小（10% ~ 200%）。
- **🔒 隐私优先**：所有处理皆在您的本地浏览器中完成，图片不会离开您的设备。
- **⚡ 即时预览**：上传即处理，快速查看结果。
- **🖱️ 拖拽支持**：支持将图片直接拖拽至窗口进行处理。
- **👀 对比模式**：长按处理后的图片即可查看原始图片，方便比较去除效果。
- **⚙️ 智能与手动模式**：
  - **自动检测**：根据图片分辨率自动判断水印大小。
  - **手动选择**：可强制选择小（48px）或大（96px）水印模式以应对特殊情况。
- **💾 高画质下载**：一鍵下载處理後的圖片，支持 PNG（无损）或 JPEG（压缩）格式。
- **🖥️ 桌面应用程序**：提供 Tauri 原生桌面应用，离线使用、性能更佳。
- **📋 剪贴板粘贴**：支持直接粘贴 (Ctrl+V) 截图或图片进行处理。
- **📦 批量 ZIP 下载**：下载多张图片时自动打包为 ZIP 文件，方便整理。
- **🌐 多语言支持**：界面支持英文、正體中文、殘體中文、日文及韩文。

## 🛠️ 技术原理

此项目使用纯 JavaScript (Canvas API) 实现。它預載了 Gemini 水印的 Alpha 遮罩（Mask），并通过计算每个像素的原始颜色值來「反算」扣除水印的影响，從而達到無損或近乎無痕的去除效果。

## 🚀 如何使用

1. **开启网页**：直接在浏览器中打开 `index.html`。
2. **上传图片**：点击上传区域选择图片，或直接将 JPG/PNG/WEBP 图片拖入。
3. **查看结果**：系统会自动处理并显示结果。
4. **调整设置**（如有需要）：如果效果不佳，可以尝试在下拉菜单中切换「Force Small」或「Force Large」。
5. **下载**：满意后点击「Download」按钮保存图片。

## 📦 安装与运行

本项目为静态网页，无需安装复杂的后端环境。

1. **克隆项目**：
   ```bash
   git clone https://github.com/springspirng/Gemin_remove_watermark.git
   ```
2. **进入目录**：
   ```bash
   cd Gemin_remove_watermark
   ```
3. **运行**：
   直接用浏览器打開 `index.html` 即可使用。
   *注意：由于浏览器安全策略（CORS），若直接開啟本地文件可能會導致遮罩圖片載入失敗。建議使用簡單的本地伺服器運行，例如使用 Python：*
   ```bash
   # Python 3
   python -m http.server 8000
   ```

   然後在瀏覽器訪問 `http://localhost:8000`。

## 🖥️ 桌面应用程序 (Tauri)

除網頁版本，我們也提供使用 [Tauri](https://tauri.app/) 建置的原生桌面應用程式。

### 特色功能
- **离线使用**：無需網路連線即可運作
- **原生性能**：通過原生 API 提供更快的文件處理
- **独立运行**：無需瀏覽器即可執行

### 從原始碼建置
```bash
# 前置需求：Rust、Node.js
cargo install tauri-cli

# 克隆并构建
git clone https://github.com/springspirng/Gemin_remove_watermark.git
cd Gemin_remove_watermark

# 开发模式
cargo tauri dev

# 建置安裝包
cargo tauri build
```
輸出位置：`src-tauri/target/release/bundle/`


## 🙏 致謝 (Acknowledgements)

特別感謝 [GeminiWatermarkTool](https://github.com/allenk/GeminiWatermarkTool) 項目提供的重要信息與靈感。

## 📄 授权条款 (License)

本项目采用 MIT 授权条款。详细内容请参阅 [LICENSE](LICENSE) 文件。
