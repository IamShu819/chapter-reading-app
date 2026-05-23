# 章章 - 中文电子书阅读器

一款专注于中文阅读体验的离线电子书阅读器，支持多格式、字典查词、生词本、书签批注。

## 支持格式

| 格式 | 说明 |
|------|------|
| EPUB | 电子书标准格式，自动解析目录和元信息 |
| TXT | 纯文本，自动识别章节目录 |
| MD | Markdown，按标题自动分章 |
| PDF | 支持文本提取和页面渲染两种模式 |
| DOCX | Word 文档，自动按标题分章 |

## 功能

- **字典查词** — 内置古典汉语词典和 CC-CEDICT，点击任意字词即可查看释义
- **生词本** — 查词时可收藏生词，支持闪卡复习模式
- **书签** — 标记阅读位置，随时跳转
- **批注** — 选中文本添加笔记，PDF 图片页支持按页添加笔记
- **主题切换** — 浅色 / 深色 / 护眼三种主题
- **PDF 缩放** — 支持按钮缩放和双指捏合，缩放级别按书保存
- **阅读进度** — 自动保存并同步进度
- **编辑书名** — 支持修改书籍标题和作者信息
- **完全离线** — 所有数据存储在本地，无需联网

## 安装

### Android

在 [releases/](releases/) 目录下载最新 APK，安装即可使用。

### 从源码运行

```bash
# 克隆仓库
git clone https://github.com/IamShu819/chapter.git
cd chapter

# 安装依赖
npm install

# 启动开发服务器
npm run dev

# 构建生产版本
npm run build
```

### 构建 APK

需要 JDK 21 和 Android SDK：

```bash
npm run build
npx cap copy android
npx cap sync android
cd android
./gradlew assembleDebug
```

APK 输出路径：`android/app/build/outputs/apk/debug/app-debug.apk`

## 技术栈

- **前端框架** Svelte 5 (runes)
- **构建工具** Vite
- **数据库** Dexie (IndexedDB)
- **字典** CC-CEDICT + 古典汉语词典
- **PDF** pdf.js
- **EPUB** epubjs + JSZip
- **Word** mammoth.js
- **Markdown** marked
- **移动端** Capacitor (Android)
