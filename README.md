# 三色墨水屏课程表设计器（epaper-course-designer）

浏览器端单文件 HTML 设计器，用于给「黑 / 白 / 红」三色墨水屏设备（如 EPD-nRF5 系列）
生成课程表 / 界面，并导出为设备原生分辨率的 PNG 与配置 JSON。

本仓库保存两个版本的设计器：

| 文件 | 说明 |
| --- | --- |
| [`epaper-course-designer.v2.html`](epaper-course-designer.v2.html) | v2（最新）：当前主版本 |
| [`epaper-course-designer.v1-backup.html`](epaper-course-designer.v1-backup.html) | v1 备份：早期版本 |

> 访问站点根目录会自动跳转到 **v2** 设计器。

## 特性
- 画布渲染 + 三色像素量化管线（无灰阶、无抖动），与 EPD-nRF5 固件逐像素对齐。
- 文泉驿 WQY 点阵字（GB2312 全量），本地嵌入，无需联网字体。
- 导出 PNG / 配置 JSON，可直接推送至墨水屏设备。

## 字体资源（`fonts/`）
设计器为**单文件自包含**：文泉驿点阵字库已 base64 内嵌进 HTML，因此打开页面**无需**任何外部字体文件。
但仓库仍保留字体源资源，便于复现 / 重新生成内嵌字库：

| 文件 | 说明 |
| --- | --- |
| `wqy_wenquanyi_9ptb.bdf` / `wqy_wenquanyi_12ptb.bdf` | 文泉驿点阵字 BDF 源（来自 `tsl0922/EPD-nRF5`） |
| `wqy_WQY9.js` / `wqy_WQY12.js` | 由 BDF 解析生成、GB2312 全量的内嵌字库（已打包进 v2） |
| `HZK16.bin` / `hzk24.bin` | 早期 HZK 点阵字（v2 已弃用，保留备用） |

## 本地运行
直接用浏览器打开对应的 `.html` 文件即可，无需构建、无需服务器。

## 在线预览（GitHub Pages）
https://shimingluo.github.io/epaper-course-designer/
