# Replicate My Courses Page Implementation Plan

> **For Claude:** REQUIRED SUB-SKILL: Use superpowers:executing-plans to implement this plan task-by-task.

**Goal:** Create a high-fidelity interactive replication of the "My Courses" page in `my-courses.html` to match the user's screenshot.

**Architecture:** Create a new page `my-courses.html` that imports the styling system, unified glassmorphic sidebar, top header, title/sub-filters, and a two-column layout for the course list and details. Include interactive tab switching via Vanilla JS.

**Tech Stack:** HTML5, CSS3, Vanilla JS.

---

### Task 1: Create my-courses.html Base & Sidebar

**Files:**
- Create: [my-courses.html](file:///e:/Dev_Workspace/01_Projects/University/PPT_Agent/my-courses.html)
- Modify: [eduai-workbench.html](file:///e:/Dev_Workspace/01_Projects/University/PPT_Agent/eduai-workbench.html)

**Step 1: Copy styling and sidebar structure**
Initialize `my-courses.html` with the document structure, full page layout, CSS styling variables, and layout styles from `eduai-workbench.html`. Add the updated unified glassmorphic sidebar.

**Step 2: Set "My Courses" active link**
In the sidebar, make the "My Courses" (`.side-item`) link active. Add navigation links between `eduai-workbench.html` and `my-courses.html`.

**Step 3: Commit**
Commit changes.

---

### Task 2: Implement Header, Title, Filters, and Columns Layout

**Files:**
- Modify: [my-courses.html](file:///e:/Dev_Workspace/01_Projects/University/PPT_Agent/my-courses.html)

**Step 1: Add Search Bar and Header button**
Update header top-actions: search placeholder "搜索课程名称、学科...", button text "+ 新建课程".

**Step 2: Add Headline Section and Filter tabs**
Create headline section with title "我的课程" and sub-caption. Add the tab filters: "全部" (active), "进行中", "已完成", "未开始".

**Step 3: Implement Content grid columns**
Define a `.content` grid container.
- Left column: `.courses-card` with "课程列表" header, count indicator "1", and the list item "初二 · 牛顿第二定律" card.
- Right column: `.details-panel` containing the green tag "未开始", course details info card, key-value detail rows, and the large green "继续设计" button.

**Step 4: Commit**
Commit changes.

---

### Task 3: Interactive JS & Polish

**Files:**
- Modify: [my-courses.html](file:///e:/Dev_Workspace/01_Projects/University/PPT_Agent/my-courses.html)

**Step 1: Add interactive tabs**
Add JavaScript to toggle active states for the filter tabs on click.

**Step 2: Verify responsive layout**
Verify styles look identical to screenshot and scale beautifully on different viewports.

**Step 3: Commit**
Commit.
