---
title: Qt简明教程
tags:
  - Qt
categories:
  - Qt
date: 2021-07-02 22:17:26
---

https://doc.qt.io/qt-6/gettingstarted.html

| 时间           | 版本     |
| -------------- | -------- |
| 2005年6月27日  | Qt 4.0   |
| 2008年5月      | Qt 4.4   |
| 2012年12月19日 | Qt 5.0   |
| 2017年5月31日  | Qt 5.9   |
| 2020年5月26日  | Qt 5.15  |
| 2020.12.8      | Qt6      |
| 2021年7月1日   | Qt 6.1.2 |

https://download.qt.io/archive/qt/5.9/5.9.9/ open source offline installers are not available any more since Qt 5.15 

https://download.qt.io/official_releases/online_installers/

声明槽

```
public slots:
```

关联

```
connect(sender, SIGNAL(signal()), receiver, SLOT(slot()));
```

- 一个信号可以连接多个槽
- 一个信号可以连接另外一个信号

```
connect(spinNum, SIGNAL(valueChanged(int)), this, SIGNAL (refreshInfo(int));
```

- 信号与槽的参数个数和类型需要一致

## 示例

https://doc.qt.io/qt-6/qtwidgets-tutorials-notepad-example.html

创建一个Qt Widgets Application

## 其它

为了将界面上的各个组件的分布设计得更加美观，经常使用一些容器类，如 QgoupBox、QtabWidget、QFrame 等

函数名上面，单击右键，在弹出的快捷菜单中选择“Refactor”→“Add Definition in elesos.cpp”，就可以自动为函数生成一个函数框架。

选中 chkBoxUnder 组件，单击右键调出其快捷菜单。在快捷菜单中单击菜单项“Go to slot…”

在 UI 设计器里，单击上方工具栏里的“Edit Signals/Slots”按钮，窗体进入信号与槽函数编辑状态

将鼠标移动到按钮上方，再按下鼠标左键，移动到窗体的空白区域释放左键，这时出现信号与槽的关联设置对话框。左侧的列表框里信号，右边的列表框里显示了槽函数。

