# 章章 - 中文电子书阅读器

一款专注于中文阅读体验的离线电子书阅读器，支持多格式、字典查词、生词本、书签批注。

## 下载安装

**Android 用户：** 前往 [Releases](https://github.com/IamShu819/chapter-reading-app/releases) 下载最新 APK，安装即可。

## 支持格式

| 格式 | 说明 |
|------|------|
| EPUB | 电子书标准格式，自动解析目录和封面 |
| TXT | 纯文本，自动识别章节标题（第X章、Chapter N 等） |
| MD | Markdown，按 `#` `##` 标题自动分章 |
| PDF | 文本提取 + 图片渲染，无文字的扫描件也能看 |
| DOCX | Word 文档，按标题自动分章 |

## 使用指南

### 导入书籍

1. 打开应用，点击底部「导入」标签
2. 点击上传区域选择文件，或直接拖拽文件到页面
3. 导入成功后自动跳转到书架

### 阅读

- 点击书架上的书籍封面进入阅读
- 底部进度条显示当前阅读位置
- 点击屏幕中央区域呼出工具栏
- 工具栏包含：字号调节（A-/A+）、书签、主题切换、搜索、目录

### 字典查词

1. 在阅读界面，**点击任意字词**即可弹出释义窗口
2. 词典内置古典汉语词典和 CC-CEDICT（中英对照）
3. 弹窗中点击「收藏」可将生词加入生词本

### 生词本

1. 底部导航切换到「生词」标签
2. 查看所有收藏的生词
3. 点击「开始复习」进入闪卡模式
4. 认识的卡片向右滑，不认识的再看一遍

### 书签与批注

- **添加书签：** 工具栏点击书签图标，标记当前阅读位置
- **添加批注：** 选中一段文字，在弹出菜单中选择「笔记」，输入想法后保存
- **PDF 图片页笔记：** PDF 扫描件无法选文字时，每页标题旁有 📝 按钮，点击可为该页添加笔记
- 书签和批注在工具栏的书签/批注图标中查看

### PDF 缩放

当 PDF 渲染为图片页时，工具栏会显示缩放控制按钮：

- **−** 缩小（每次 0.02，细微调整）
- **1x** 点击循环切换：1x → 1.1x → 1.3x → 1.5x → 2x → 3x → 还原
- **+** 放大
- 也支持**双指捏合**缩放
- 缩放级别**按书保存**，翻章和重新打开都会恢复

### 编辑书籍信息

1. 在阅读界面，点击工具栏的**铅笔图标**
2. 可修改书名和作者
3. 保存后书架同步更新

### 设置

底部导航切换到「设置」标签：

- **字体：** 宋体（衬线）/ 黑体（无衬线）/ 等宽
- **字号：** 12px - 32px
- **行距：** 1.2 - 2.4
- **主题：** 浅色 / 深色 / 护眼

## 从源码运行

```bash
git clone https://github.com/IamShu819/chapter-reading-app.git
cd chapter-reading-app
npm install
npm run dev
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

APK 输出：`android/app/build/outputs/apk/debug/app-debug.apk`

## 技术栈

| 类别 | 技术 |
|------|------|
| 前端 | Svelte 5 (runes) |
| 构建 | Vite |
| 数据库 | Dexie (IndexedDB) |
| 字典 | CC-CEDICT + 古典汉语词典 |
| PDF | pdf.js |
| EPUB | epubjs + JSZip |
| Word | mammoth.js |
| Markdown | marked |
| 移动端 | Capacitor (Android) |
