# 枚举: NodeEventType
## 触摸事件(4)
### TOUCH_START
> 手指开始触摸事件。

- TOUCH_START = `"touch-start"`

### TOUCH_MOVE
> 当手指在屏幕上移动时。

- TOUCH_MOVE = `"touch-move"`

### TOUCH_END
> 手指结束触摸事件。

- TOUCH_END = `"touch-end"`

### TOUCH_CANCEL
> 当手指在目标节点区域外离开屏幕时。

- TOUCH_CANCEL = `"touch-cancel"`

## 鼠标事件

### MOUSE_DOWN
> 当鼠标按下时触发一次。

- MOUSE_DOWN = `"mouse-down"`

### MOUSE_MOVE
> 当鼠标在目标节点在目标节点区域中移动时，不论是否按下。

- MOUSE_MOVE = `"mouse-move"`

### MOUSE_UP
> 当鼠标从按下状态松开时触发一次。

- MOUSE_UP = `"mouse-up"`

### MOUSE_WHEEL
> 当鼠标滚轮滚动时。

- MOUSE_WHEEL = `"mouse-wheel"`

### MOUSE_ENTER
> 当鼠标**移入**目标节点区域时，不论是否按下。

- MOUSE_ENTER = `"mouse-enter"`

### MOUSE_LEAVE
> 当鼠标**移出**目标节点区域时，不论是否按下。

- MOUSE_LEAVE = `"mouse-leave"`

### TRANSFORM_CHANGED
> 节点改变位置、旋转或缩放事件。如果具体需要判断是哪一个事件，可通过判断回调的第一个参数类型是 [[Node.TransformBit]] 中的哪一个来获取。

`@example 例子`
```typescript
this.node.on(Node.EventType.TRANSFORM_CHANGED, (type)=>{
 if (type & Node.TransformBit.POSITION) {
      //...
  }
}, this);
```
- TRANSFORM_CHANGED = `"transform-changed"`
