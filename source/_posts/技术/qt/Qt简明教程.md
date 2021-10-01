---
title: Qt简明教程
tags:
  - Qt
categories:
  - Qt
date: 2021-07-02 22:17:26
---

https://doc.qt.io/qt-6/gettingstarted.html

| 时间           | 版本                                     |
| -------------- | ---------------------------------------- |
| 2005年6月27日  | Qt 4.0                                   |
| 2008年5月      | Qt 4.4                                   |
| 2012年12月19日 | Qt 5.0                                   |
| 2017年5月31日  | Qt 5.9                                   |
| 2021.5.25      | 5.12 LTS                                 |
| 2020年5月26日  | Qt 5.15 lts only for Commercial licenses |
| 2020.12.8      | Qt6                                      |
| 2021年7月1日   | Qt 6.1.2                                 |

https://en.wikipedia.org/wiki/Qt_version_history

## 下载 

https://download.qt.io/archive/qt/5.9/5.9.9/ open source offline installers are not available any more since Qt 5.15 

https://download.qt.io/archive/qt/

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



## 其它

为了将界面上的各个组件的分布设计得更加美观，经常使用一些容器类，如 QgoupBox、QtabWidget、QFrame 等

### 在UI界面上关联信号与槽

ui中选中比如一个 chkBoxUnder 组件，右键调出其快捷菜单。在快捷菜单中单击菜单项“Go to slot…”



头文件声明的函数名上面，右键，选择“Refactor重构”→“Add Definition in elesos.cpp”，就可以自动在cpp中生成定义。



在 UI 设计器里，单击上方工具栏里的“Edit Signals/Slots”按钮，窗体进入信号与槽函数编辑状态

将鼠标移动到按钮上方，再按下鼠标左键，移动到窗体的空白区域释放左键，这时出现信号与槽的关联设置对话框。左侧的列表框里信号，右边的列表框里显示了槽函数（如果没有显示，把复选框勾选上）。

http://c.biancheng.net/view/1822.html

https://www.cnblogs.com/schips/p/framework-cpp-qt-02-ui-layout-manage.html



## 示例

安装qt时选择安装源码。

https://doc.qt.io/qt-6/qtwidgets-tutorials-notepad-example.html

创建一个Qt Widgets Application

Qt Quick for building modern, fluid, animated UIs.

 用到什么知识点：文本文件读写

 

2,https://doc.qt.io/qt-6/qtconcurrent-imagescaling-example.html
 QFuture class represents the result of an asynchronous computation.
 QPromise class provides a way to store computation results to be accessed by QFuture
 异步下载



 https://doc.qt.io/qt-6/qtexamplesandtutorials.html  这个页面有2个子页面的示例列表。

 

 

 

 



参考 

https://qmlbook.github.io  focuses on Qt Quick, but also provides the information needed to use QML together with C++.



#### 常用知识点

##### Q_DECLARE_PRIVATE：用于声明对应的私有类的，比如XXXPrivate 类

https://wiki.qt.io/D-Pointer

Binary compatibility ：更新库不需要重新编译

d-pointer：指向一个私有实现子类，d弟，Q_D返回私有子类指针。

q-pointer:指向父类。



QMetaObject::invokeMethod调用一个对象的方法





## qt资料

基本上看一去二三里的这个就够了https://blog.csdn.net/liang19890820/article/details/50277095

Qt 快速入门系列教程  - http://shouce.jb51.net/qt-beginning/  简洁明了，干净排版，目录清晰。 分基础，图形，数据，网络篇，进阶，过度篇。

Qt开发学习教程  - https://blog.51cto.com/u_9291927/2138876  - 来自天山老妖，51博客上的，分为基础，中阶，高阶，其他。

https://www.devbean.net/2012/08/qt-study-road-2-catelog/ 亮哥推荐

Q_OBJECT宏： 在类的私有部分声明这个宏





运行时类别信息（RTTI）：实例化对象所属的类信息在运行时才真正确定  dynamic_cast





```
label->setAttribute(Qt::WA_DeleteOnClose);
```

所谓信号槽，实际就是观察者模式。

按钮在 Qt 中被称为`QPushButton`

`QDialog::exec()`实现应用程序级别的模态对话框，`QDialog::show()`实现非模态对话框



### 书籍推荐

入门推荐《C++ GUI Qt 4编程》https://blog.csdn.net/net_syc/article/details/80236963

qt 源码



# 栈和堆

A a；栈

堆上创建对象，使用`new`运算符





写数据前QMutexLocker locker(&QMutex);







blockSignals



qt 用 QEventLoop可以阻塞工作线程，同时不影响主线程

类似这样的将要删除的接口可以用  QT_DEPRECATED_X("XXXX")  定义一下，这样的接口被引用，会有警告信息







## 常用语法

#### tr

All classes that inherit [QObject](https://doc.qt.io/qt-5/qobject.html) have a `tr()` function. 

QObject::tr("Hello world!")





#### QScopedPointer



Q_DECLARE_METATYPE



#### QStringList 

字符串列表,从QList <QString>继承而来, 合并字符串使用join( ),类似php的implode,拆分字符串split