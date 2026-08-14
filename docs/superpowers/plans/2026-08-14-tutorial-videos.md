# TC16 教学视频页面 Implementation Plan

> **For agentic workers:** REQUIRED SUB-SKILL: Use superpowers:subagent-driven-development (recommended) or superpowers:executing-plans to implement this plan task-by-task. Steps use checkbox (`- [ ]`) syntax for tracking.

**Goal:** 在 TC16 GitHub Pages 网站提供 10 个可在电脑和手机上直接播放的教学视频。

**Architecture:** 视频以静态 MP4 文件存放在 `assets/videos/`，独立的 `tutorials.html` 使用原生 HTML5 播放器展示，现有 `index.html` 只增加导航入口。无需 JavaScript、构建工具或第三方播放器。

**Tech Stack:** GitHub Pages、HTML5、CSS、MP4

## Global Constraints

- 保留现有首页下载和更新逻辑。
- 10 个播放器必须使用 `controls` 和 `preload="metadata"`。
- 视频文件名使用 ASCII 小写短横线格式。
- 桌面端双列，移动端单列。

---

### Task 1: 导入视频资源

**Files:**
- Create: `assets/videos/01-software-start-connect.mp4` 至 `assets/videos/10-firmware-update.mp4`

**Interfaces:**
- Consumes: `W:\python上位机\TC16教学视频.zip`
- Produces: `tutorials.html` 引用的 10 个静态 MP4 URL

- [ ] **Step 1: 解压压缩包到临时目录**

运行 `Expand-Archive -LiteralPath 'W:\python上位机\TC16教学视频.zip' -DestinationPath $tempDir`，预期得到 10 个非空 MP4。

- [ ] **Step 2: 按序号复制并改为 ASCII 文件名**

将原始中文文件名依次映射为 `01-software-start-connect.mp4`、`02-curve-import.mp4`、`03-temperature-measurement.mp4`、`04-history-curve-export.mp4`、`05-heater-open-loop.mp4`、`06-oscilloscope-mode.mp4`、`07-pid-autotune.mp4`、`08-pid-control.mp4`、`09-control-software-update.mp4`、`10-firmware-update.mp4`。

- [ ] **Step 3: 验证资源数量和大小**

运行 `Get-ChildItem assets/videos/*.mp4`，预期文件数为 10，且每个 `Length` 大于 0。

### Task 2: 创建教学视频页面与首页入口

**Files:**
- Create: `tutorials.html`
- Modify: `index.html`
- Modify: `README.md`

**Interfaces:**
- Consumes: Task 1 生成的视频 URL
- Produces: `/tc16-updates/tutorials.html` 页面和首页导航入口

- [ ] **Step 1: 创建语义化视频列表**

为每个教程生成一个 `<article>`，包含 `<h2>` 和 `<video controls preload="metadata">`，视频源指向对应的 `assets/videos/*.mp4`。

- [ ] **Step 2: 添加响应式样式**

使用 `grid-template-columns: repeat(2, minmax(0, 1fr))`，在 `760px` 以下切换为单列；视频设置 `width: 100%` 和稳定的 `aspect-ratio: 16 / 9`。

- [ ] **Step 3: 添加首页导航和维护说明**

在 `index.html` 顶部导航加入 `tutorials.html`；在 README 仓库内容中记录教学页及 `assets/videos/`。

### Task 3: 验证并发布

**Files:**
- Verify: `index.html`
- Verify: `tutorials.html`
- Verify: `assets/videos/*.mp4`

**Interfaces:**
- Consumes: 完整静态网站
- Produces: GitHub Pages 线上教学视频页面

- [ ] **Step 1: 运行静态资源检查**

解析 `tutorials.html` 中全部 `src` 和 `href` 本地引用，预期文件均存在；预期播放器数量和 MP4 文件数均为 10。

- [ ] **Step 2: 本地浏览器验证**

启动本地 HTTP 服务，打开首页和教学页，分别在桌面与移动端检查导航、双列/单列布局和播放器元数据加载。

- [ ] **Step 3: 提交并推送**

运行 `git add`、`git commit -m "发布 TC16 教学视频"`、`git push origin main`，预期远端 `main` 更新成功。

- [ ] **Step 4: 验证线上页面**

访问 `https://stuartsysu-glitch.github.io/tc16-updates/tutorials.html`，预期 HTTP 200，且页面包含 10 个播放器。
