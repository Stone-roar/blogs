[（1、🔙返回上一级）](目录_Event.md "event模块")
[（2、转到 SystemEvent.EventType）](Event_Class_SystemEvent.md#EventType_index "点击查看 “系统事件—事件类型”")
# 枚举: SystemEvent.EventType

> 全局系统事件

## 目录
* [`DEVICEMOTION` **重力感应**](#DEVICEMOTION)
* **触摸事件**
  * [`TOUCH_START` 触摸开始](#TOUCH_START)
  * [`TOUCH_MOVE` 触摸移动](#TOUCH_MOVE)
  * [`TOUCH_END` 触摸结束](#TOUCH_END)
  * [`TOUCH_CANCEL` 取消触摸](#1TOUCH_CANCEL)
* **鼠标事件**
  * [`MOUSE_DOWN` 鼠标按下](#MOUSE_DOWN)
  * [`MOUSE_MOVE` 鼠标移动（按下状态）](#MOUSE_MOVE)
  * [`MOUSE_UP` 鼠标松开](#MOUSE_UP)
  * [`MOUSE_WHEEL` 滚轮](#MOUSE_WHEEL)
* **键盘事件**
  * [`KEY_DOWN` 按下按键](#KEY_DOWN)
  * [`KEY_UP` 松开按键](#KEY_UP)
---
## 重力感应
### DEVICEMOTION

重力感应

- **DEVICEMOTION** = `"devicemotion"`

---
## 触摸事件 {4}
[（🆙回到顶部）](#目录)
### TOUCH_START
> 手指开始触摸事件。
- TOUCH_START = `"touch-start"`

---
### TOUCH_MOVE
> 当手指在屏幕上移动时。

- TOUCH_MOVE = `"touch-move"`

---
### TOUCH_END
> 手指结束触摸事件。

- TOUCH_END = `"touch-end"`

---
### TOUCH_CANCEL
> 当手指在目标节点区域外离开屏幕时。

- TOUCH_CANCEL = `"touch-cancel"`

---
## 鼠标事件 {4}
[（🆙回到顶部）](#目录)
### MOUSE_DOWN
> 当鼠标按下时触发一次。

- MOUSE_DOWN = `"mouse-down"`

---
### MOUSE_MOVE
> 当鼠标在目标节点在目标节点区域中移动时，不论是否按下。

- MOUSE_MOVE = `"mouse-move"`

---
### MOUSE_UP
> 当鼠标从按下状态松开时触发一次。

- MOUSE_UP = `"mouse-up"`

---
### MOUSE_WHEEL
> 当鼠标滚轮滚动时。

- MOUSE_WHEEL = `"mouse-wheel"`

---
## 键盘事件 {2}
[（🆙回到顶部）](#目录)
### KEY_DOWN

> 当按下按键时触发的事件, 该事件在按下状态会持续派发

- **KEY_DOWN** = `"keydown"`

---

### KEY_UP

> 当松开按键时触发的事件

- **KEY_UP** = `"keyup"`
