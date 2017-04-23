## 类: BrowserView

> 创建和控制视图

**注意：** BrowserView API目前为实验性质，可能会更改或删除。

进程:[主进程](../glossary.md#主进程)      

 `BrowserView`是 `webview`的替代标签,就像是子窗口一样让某个 `BrowserWindow`嵌入更多的Web内容. 

## 例子

```javascript
// 主进程中
const {BrowserView, BrowserWindow} = require('electron')

let win = new BrowserWindow({width: 800, height: 600})
win.on('closed', () => {
  win = null
})

let view = new BrowserView()
win.addChildView(view)
view.setBounds(0, 0, 300, 300)
view.webContents.loadURL('https://electron.atom.io')
```

### `new BrowserView([options])` _实验功能_

* `options` Object (可选)
  * `webPreferences` Object (可选) - 详细查看 [BrowserWindow](browser-window.md).

### 实例属性

使用 `new BrowserView`创建的对象具有以下属性:

#### `view.webContents` _实验功能_
> 属性:**视图的[`webContents`](web-contents.md)对象**

#### `win.id` _实验功能_
> 属性:**视图的唯一ID( `Integer`)**

### 实例方法

使用 `new BrowserWindow` 创建的对象具有以下实例方法:

#### `win.setBounds(bounds)` _实验功能_
> 用途:**调整视图大小并将它移动至窗口边界**

* `bounds` [Rectangle](structures/rectangle.md)

#### `win.setBackgroundColor(color)` _实验功能_
> 用途:**设置视图的背景颜色**

* `color` String - 颜色值格式如 `#aarrggbb` 或 `#argb`,可选透明度.