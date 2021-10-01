---
title: Electron简明教程
tags:
  - Electron
categories:
  - Electron
date: 2021-07-03 07:50:34
---

GitHub开发的，可通过JavaScript（主要还是node.js）, HTML和CSS开发跨平台的桌面软件，兼容 Mac、Windows 和 Linux，vscode就是基于electron开发的。teams也是

2021年，有道云笔记也用这个了。

https://github.com/electron/electron

https://www.electronjs.org/

参考：https://www.zhihu.com/question/53230344

# electron-quick-start

Electron不是某个GUI库的javascript版本，可以把它当作一个精简版的 Chromium 浏览器，使用web页面作为它的GUI

```
npm install -g electron --save-dev //Mac下不要-g
```

示例工程

```
git clone https://github.com/electron/electron-quick-start
cd electron-quick-start
npm install
npm start  //npm start命令会让npm执行定义在package.json中的start命令
```

这样会生成一个GUI桌面程序，参考文档：https://electronjs.org/docs/tutorial/quick-start

应用的入口是 package.json 文件，

最基本的 Electron 应用一般包含3个文件， package.json，main.js(应用的启动脚本)和index.html

electron.app负责管理Electron 应用程序的生命周期

electron.BrowserWindow类负责创建窗口

第一行是js解构赋值

```
const { app, BrowserWindow } = require('electron')
```

参考var {name, age, passport} = person;

# electron-api-demos

https://github.com/electron/electron-api-demos && https://github.com/electron/electron-api-demos/blob/master/docs.md

```
$ git clone https://github.com/electron/electron-api-demos
$ cd electron-api-demos
$ npm install
$ npm start  //or npm run dev
```

# electron-sample-apps

https://github.com/sindresorhus/awesome-electron

https://github.com/hokein/electron-sample-apps

```
npm install -g electron
electron <electron-sample-apps-path>/<sample-name>
```

### window

 https://www.electronjs.org/docs/api/browser-window

 

使窗口显示时没有视觉闪烁:建议立刻显示窗口，并使用接近应用程序背景的 backgroundColor

 

const win = new BrowserWindow({ backgroundColor: '#2e2c29' })
 win.loadURL('https://github.com')

 

子窗口
  const top = new BrowserWindow()
  const child = new BrowserWindow({ parent: top }) 

 

 创建时设置show=false可以用来执行后台任务