# Sidebar Optimization Implementation Plan

> **For Claude:** REQUIRED SUB-SKILL: Use superpowers:executing-plans to implement this plan task-by-task.

**Goal:** Refactor the left sidebar of the EduAI Workbench application into a full-height glassmorphic floating column that smoothly expands on hover.

**Architecture:** Combine `.side-nav` and `.avatar` into a single container positioned relative to the screen height. Style the container with a blurred background (`backdrop-filter`) and smooth transition logic for hover expansion. Adjust the shell margin to accommodate the sidebar.

**Tech Stack:** HTML5, CSS3 transitions, Backdrop Filter.

---

### Task 1: HTML Structure Restructuring

**Files:**
- Modify: [eduai-workbench.html](file:///e:/Dev_Workspace/01_Projects/University/PPT_Agent/eduai-workbench.html)

**Step 1: Locate existing sidebar and avatar elements**
Lines 784-809.

**Step 2: Restructure into a unified aside element**
Replace the separate `.side-nav` and `.avatar` sections with a single `.side-nav` containing:
- `.side-header` (brand/main logo grid button and a hidden text branding)
- `.side-icons` containing each `.side-item` (with nested labels in `span` elements)
- `.side-footer` containing the avatar and text label.

**Step 3: Commit**
Commit changes to local Git.

---

### Task 2: CSS Styles Implementation

**Files:**
- Modify: [eduai-workbench.html](file:///e:/Dev_Workspace/01_Projects/University/PPT_Agent/eduai-workbench.html)

**Step 1: Write sidebar dimensions and positioning**
Update style definitions for `.side-nav` to:
```css
.side-nav {
  position: fixed;
  top: 20px;
  bottom: 20px;
  left: 20px;
  width: 76px;
  height: calc(100vh - 40px);
  padding: 24px 0;
  display: flex;
  flex-direction: column;
  justify-content: space-between;
  align-items: center;
  border-radius: 24px;
  border: 1px solid rgba(255, 255, 255, 0.65);
  background: rgba(253, 255, 251, 0.45);
  backdrop-filter: blur(20px);
  -webkit-backdrop-filter: blur(20px);
  box-shadow: 0 20px 48px rgba(43, 64, 42, 0.08);
  z-index: 100;
  transition: width 0.3s cubic-bezier(0.4, 0, 0.2, 1);
  overflow: hidden;
}
.side-nav:hover {
  width: 220px;
  align-items: stretch;
  padding: 24px 16px;
}
```

**Step 2: Add hover item effects and label visibility transitions**
Implement classes for text hiding/showing inside the sidebar items:
```css
.side-item span, .side-brand-text, .side-user-info {
  opacity: 0;
  white-space: nowrap;
  transition: opacity 0.2s ease;
  pointer-events: none;
}
.side-nav:hover .side-item span,
.side-nav:hover .side-brand-text,
.side-nav:hover .side-user-info {
  opacity: 1;
  pointer-events: auto;
}
```

**Step 3: Modify `.shell` margin**
Update the main page layout margin to accommodate the sidebar:
`margin-left: 116px` (instead of default margin-left auto/88px).

**Step 4: Commit**
Commit changes.

---

### Task 3: Mobile Layout and Verification

**Files:**
- Modify: [eduai-workbench.html](file:///e:/Dev_Workspace/01_Projects/University/PPT_Agent/eduai-workbench.html)

**Step 1: Check media queries**
Verify phone and tablet viewport behavior at `<760px` to hide or transform the sidebar to a bottom bar.

**Step 2: Commit**
Commit.
