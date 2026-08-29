# SparkOS

SparkOS 是一個從零開始開發、專為現代觸控平板設計的 32-bit x86 作業系統。不依賴 HTML/CSS/JavaScript，完全使用 C 語言與組合語言（Assembly）撰寫，並透過硬體 Framebuffer 自行實作輕量化的 2D 圖形渲染引擎。

![Architecture](https://img.shields.io/badge/Architecture-x86-blue.svg)
![Bootloader](https://img.shields.io/badge/Bootloader-GRUB%20Multiboot-orange.svg)
![License](https://img.shields.io/badge/License-MIT-green.svg)

---

## 🌟 特色與亮點

- **純粹 OS 架構**：無網頁包裝，不依賴高階 GUI 庫，直連硬體渲染。
- **現代平板風格 GUI**：內建自研 2D Renderer，支援圓角矩形、按鈕、視窗、Slider 與 Dock 欄。
- **高移植性建置**：支援 GitHub Actions 雲端打包，在 Android 平板或行動裝置上記錄開發，雲端自動產出 ISO。
- **標準 Multiboot 1**：支援 GRUB 引導，相容 QEMU、VirtualBox 與實機開機。

---

## 📁 專案目錄結構

```text
SparkOS/
├── .github/
│   └── workflows/
│       └── build.yml      # GitHub Actions 自動編譯腳本
├── iso_root/
│   └── boot/
│       └── grub/
│           └── grub.cfg   # GRUB 開機選單設定
├── src/
│   ├── arch/
│   │   └── x86/
│   │       ├── boot.asm   # Multiboot 引導與 Entry
│   │       └── linker.ld  # Kernel 記憶體配置腳本
│   └── kernel/
│       ├── kernel.c       # Kernel 主程式 logic
│       └── graphics.c     # 2D 繪圖引擎實作
├── include/
│   └── graphics.h         # Framebuffer 與繪圖 API 標頭檔
├── Makefile               # 編譯規則
├── build_iso.sh           # 本地 ISO 打包腳本
└── README.md

