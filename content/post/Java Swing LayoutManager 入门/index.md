---
title: "Java Swing LayoutManager 入门"
description: "告别手算坐标，用布局管理器优雅地排列组件"
date: 2026-04-29
draft: false
math: false
tags: [Java, Swing, GUI, LayoutManager]
categories: [技术笔记]
---

## 为什么要用 LayoutManager

手算坐标（`setLayout(null)` + `setBounds(x, y, w, h)`）的痛点：

- 改一个组件的位置，要重算所有依赖它的坐标
- 窗口大小变了就乱掉
- 加新组件要重新调整整个布局
- 代码里全是魔法数字，可读性差

LayoutManager 帮你**声明式地描述布局**，组件的位置和大小由管理器自动计算。

---

## 五种常用布局

### 1. FlowLayout — 流式排列

```java
setLayout(new FlowLayout());
add(button1);  // 从左到右排
add(button2);
add(button3);  // 排不下自动换行
```

**特点**：保持组件原始大小，水平排列。适合工具栏、按钮组。

几个构造参数：
- `FlowLayout(FlowLayout.CENTER)` — 居中对齐
- `FlowLayout(FlowLayout.LEFT, 10, 5)` — 左对齐，水平间距10，垂直间距5

### 2. BorderLayout — 东南西北中

```java
setLayout(new BorderLayout());
add(button1, BorderLayout.NORTH);   // 上
add(button2, BorderLayout.SOUTH);   // 下
add(button3, BorderLayout.WEST);    // 左
add(button4, BorderLayout.EAST);    // 右
add(button5, BorderLayout.CENTER);  // 中间（占剩余空间）
```

**特点**：五个区域，NORTH/SOUTH 保持组件高度，WEST/EAST 保持组件宽度，CENTER 填充剩余空间。

非常适合作为**窗口的主布局**。比如你的连连看：

```java
GameFrame.setLayout(new BorderLayout());
add(statusPanel, BorderLayout.NORTH);   // 顶部状态栏
add(boardPanel, BorderLayout.CENTER);   // 中间棋盘（撑满剩余空间）
add(controlPanel, BorderLayout.SOUTH);  // 底部控制按钮
```

### 3. GridLayout — 网格均分

```java
setLayout(new GridLayout(2, 3));  // 2行3列
add(btn1);  // 按行填充
add(btn2);
// ...
add(btn6);
```

**特点**：每个格子大小**完全相等**。适合棋盘、数字键盘。

你的连连看棋盘其实很适合 GridLayout：

```java
// BoardPanel 用 GridLayout
boardPanel.setLayout(new GridLayout(rows, cols));
// 每个格子自动等大，不用算 cellWidth/cellHeight
```

### 4. BoxLayout — 单行或单列

```java
setLayout(new BoxLayout(this, BoxLayout.Y_AXIS));  // 垂直排列
add(label);
add(button);
add(textField);
```

**特点**：比 FlowLayout 更灵活，可以控制对齐方式和固定大小。

### 5. GridBagLayout — 终极方案（不推荐新手）

可以做到非常复杂的布局，但代码量巨大。**大多数情况下 GridLayout + BorderLayout 嵌套就够了。**

---

## 核心技巧：布局嵌套

**一个面板用一个布局，不够就套一层。**

```
JFrame (BorderLayout)
├── NORTH: StatusPanel (GridLayout 1x2)
│   ├── leftPanel (FlowLayout): "剩余时间" + "00:23"
│   └── rightPanel (FlowLayout): "已经用时" + "01:37"
├── CENTER: BoardPanel (GridLayout 8x8)
│   └── 64个格子
└── SOUTH: ControlPanel (FlowLayout)
    └── "重新开始" + "提示" 按钮
```

代码结构：

```java
// 顶层
GameFrame.setLayout(new BorderLayout());
add(statusPanel, BorderLayout.NORTH);
add(boardPanel, BorderLayout.CENTER);
add(controlPanel, BorderLayout.SOUTH);

// 状态栏内部
StatusPanel.setLayout(new GridLayout(1, 2));
JPanel left = new JPanel(new FlowLayout());
left.add(new JLabel("剩余时间"));
left.add(timeLabel);
JPanel right = new JPanel(new FlowLayout());
right.add(new JLabel("已经用时"));
right.add(timecountLabel);
add(left);
add(right);
```

**零坐标计算，全自动排列。**

---

## 几个实用小细节

### setPreferredSize

某些布局（如 FlowLayout）尊重组件的「期望大小」：

```java
button.setPreferredSize(new Dimension(100, 40));
```

### setMinimumSize / setMaximumSize

BoxLayout 会尊重这些限制，可以在垂直布局里控制组件不撑开。

### 间距设置

```java
setLayout(new GridLayout(3, 3, 10, 10));  // 水平间距10，垂直间距10
```

或通过 empty border 加边距：

```java
panel.setBorder(BorderFactory.createEmptyBorder(10, 10, 10, 10));
```

---

## 你的 StatusPanel 可以改成这样

```java
public StatusPanel() {
    setLayout(new GridLayout(1, 2));  // 一行两列
    
    // 左：剩余时间
    JPanel left = new JPanel(new FlowLayout(FlowLayout.CENTER, 20, 10));
    left.add(new JLabel("剩余时间"));
    left.add(timeLabel);
    
    // 右：已经用时
    JPanel right = new JPanel(new FlowLayout(FlowLayout.CENTER, 20, 10));
    right.add(new JLabel("已经用时"));
    right.add(timecountLabel);
    
    add(left);
    add(right);
}
```

不需要任何一个 x/y 坐标。以后想调整布局，改 LayoutManager 的参数就行，不用重算位置。

---

## 总结

| 布局 | 适用场景 |
|:----|:--------|
| `FlowLayout` | 按钮组、工具栏 |
| `BorderLayout` | 窗口主布局（上下中） |
| `GridLayout` | 棋盘、等大方块 |
| `BoxLayout` | 垂直表单 |
| `GridBagLayout` | 复杂布局（慎用）|

**永远不要再写 `setLayout(null)` + `setBounds()` 了。**
