# 侧边栏优化设计方案 (磨砂玻璃悬浮通栏)

## 1. 目标
优化 EduAI Workbench 左侧侧边栏，从原本零散悬浮且缺乏文字标注的布局，重构为高度统一、具备现代磨砂玻璃质感、支持鼠标悬浮展开的高级通栏式侧边栏。

## 2. 方案细节

### 2.1 HTML 结构调整
将原本独立的 `.side-nav` 和 `.avatar` 合并为单一的 HTML 组件 `<aside class="side-nav">`：
- **`.side-header`**: 宫格图标与系统品牌简称（展开时显示）。
- **`.side-menu`**: 导航列表。各菜单项包含 `svg` 图标与 `span` 文字标签。
- **`.side-footer`**: 用户头像与角色文本（展开时显示详情）。

### 2.2 CSS 样式重构
- **定位与尺寸**:
  - `position: fixed; top: 20px; bottom: 20px; left: 20px; height: calc(100vh - 40px);`
  - 宽度在 `76px`（收纳）和 `220px`（展开）之间平滑过渡。
- **视觉风格**:
  - 半 transparent 浅色背景：`background: rgba(253, 255, 251, 0.45);`
  - 模糊滤镜：`backdrop-filter: blur(20px); -webkit-backdrop-filter: blur(20px);`
  - 半透明高亮边框：`border: 1px solid rgba(255, 255, 255, 0.65);`
- **动画动效**:
  - 悬浮伸缩过渡：`transition: width 0.3s cubic-bezier(0.4, 0, 0.2, 1);`
  - 文字淡入淡出与溢出隐藏。

### 2.3 响应式适配
- 在大屏幕（>1280px）下，侧边栏悬浮，内容区 `.shell` 左边距留白。
- 在中等屏幕（760px - 1280px）下，侧边栏保持原样，`.shell` 左侧外边距自适应。
- 在小屏幕（<760px）下，侧边栏切换为底部固定导航栏（Bottom Navigation），隐藏非核心选项。
