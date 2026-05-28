# Style Synchronization for ppt-preview.html and workspace.html

> **For Claude:** REQUIRED SUB-SKILL: Use superpowers:executing-plans to implement this plan task-by-task.

**Goal:** Convert `ppt-preview.html` and `workspace.html` from their dark-theme styling to our signature light-green/yellow glassmorphism design style.

**Architecture:** Inject root design tokens, body gradients, grid textures, and glassmorphic panel styling (backdrop blur, white borders, soft drop shadows) into both HTML files. Apply lime-green styling to active triggers and buttons.

**Tech Stack:** HTML5, CSS3 Glassmorphism (backdrop-filter), CSS Grid/Flexbox.

---

### Task 1: Sync ppt-preview.html Styles

**Files:**
- Modify: [ppt-preview.html](file:///e:/Dev_Workspace/01_Projects/University/PPT_Agent/ppt-preview.html)

**Step 1: Replace Root and Global Styles**
Update `:root` variables to define `--ink`, `--muted`, `--lime`, `--green`, `--panel`, `--line`, and `--shadow`. Modify `body` to use the radial yellow-green background gradient and white grid overlay.

**Step 2: Update Header and Panel Containers**
- Change `.topbar` to light glassmorphic styling (white translucent background, blur filter, light white bottom border).
- Change `.left-panel` (slide list), `.main-panel` (canvas area), and `.ai-panel` (chat box) to light translucent panels (`rgba(249, 252, 245, 0.58)` background, backdrop blur, white borders, ink text).
- Re-style thumbnails (`.slide-thumb`) to use light translucent cards and set active highlight borders to dark green.
- Re-style chat bubbles (`.ai-msg`) to light translucent text boxes with dark gray borders.

**Step 3: Update Buttons to Lime-green Style**
Update `.btn-primary` and `.btn-send` to lime green (`var(--lime)`) background, `#0d120e` text, and matching shadows.

**Step 4: Commit**
Commit changes.

---

### Task 2: Sync workspace.html Styles

**Files:**
- Modify: [workspace.html](file:///e:/Dev_Workspace/01_Projects/University/PPT_Agent/workspace.html)

**Step 1: Replace Root and Global Styles**
Update `:root` design tokens and `body` background gradient/grid overlay.

**Step 2: Update Layout Panels**
- Style `.topbar` as light glassmorphic top bar.
- Style `.dock` (left column buttons), `.main-panel` (syllabus list), `.ai-panel` (chat list), and `.info-panel` (right sidebar) as light glassmorphic panels.
- Update overview hero card and cards/rows to light glassmorphic panels with dark text.

**Step 3: Style Buttons**
Make all primary action buttons (`.info-primary`, `.btn-send`, `.btn-generate`) lime-green with dark text.

**Step 4: Commit**
Commit changes.
