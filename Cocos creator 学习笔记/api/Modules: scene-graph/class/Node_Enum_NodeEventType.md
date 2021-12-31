[（返回上一级）](https://github.com/Stone-roar/blogs/blob/main/Cocos%20creator%20%E5%AD%A6%E4%B9%A0%E7%AC%94%E8%AE%B0/api/Modules:%20scene-graph/class/Node.md "类：Node")  
# 枚举: NodeEventType
## 目录
* **触摸事件**
    * [TOUCH_START](#TOUCH_START)
    * [TOUCH_MOVE](#TOUCH_MOVE)
    * [TOUCH_END](#TOUCH_END)
    * [TOUCH_CANCEL](#TOUCH_CANCEL)
* **鼠标事件**
    * [MOUSE_DOWN【按下】](#MOUSE_DOWN)
    * [MOUSE_MOVE【移动】](#MOUSE_MOVE)
    * [MOUSE_UP【松开】](#MOUSE_UP)
    * [MOUSE_WHEEL【滚轮】](#MOUSE_WHEEL)
    * [MOUSE_ENTER【进入区域】](#MOUSE_ENTER)
    * [MOUSE_LEAVE【离开区域】](#MOUSE_LEAVE)
* **节点状态事件**
    * 节点自身状态
        * [ACTIVE_IN_HIERARCHY_CHANGED](#ACTIVE_IN_HIERARCHY_CHANGED)
        * [TRANSFORM_CHANGED【位置改变、旋转、缩放】](#TRANSFORM_CHANGED)
        * [NODE_DESTROYED【被销毁】](#NODE_DESTROYED)
        * [LAYER_CHANGED【layer改变】](#LAYER_CHANGED)
        * [SCENE_CHANGED_FOR_PERSISTS【所在场景改变】](#)
        * [！SIZE_CHANGED](#SIZE_CHANGED)
        * [！ANCHOR_CHANGED](#ANCHOR_CHANGED)
        * [！COLOR_CHANGED](#COLOR_CHANGED)
    * 节点族系状态改变
        * [CHILD_ADDED【添加子节点】](#CHILD_ADDED)
        * [CHILD_REMOVED【移除子节点】](#CHILD_REMOVED)
        * [PARENT_CHANGED【父节点状态改变】](#PARENT_CHANGED)
        * [SIBLING_ORDER_CHANGED【…中顺序改变】](#SIBLING_ORDER_CHANGED)




---
## 触摸事件 {4}
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

## 鼠标事件 {6}

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

## 节点状态事件 {12}
### ACTIVE_IN_HIERARCHY_CHANGED
> 注意：此节点激活时，此事件仅从最顶部的节点发出。

- ACTIVE_IN_HIERARCHY_CHANGED = `"active-in-hierarchy-changed"`

### TRANSFORM_CHANGED
> 节点改变位置、旋转或缩放事件。

如果具体需要判断是哪一个事件，可通过判断回调的第一个参数类型是 [[Node.TransformBit]] 中的哪一个来获取。

```typescript
this.node.on(Node.EventType.TRANSFORM_CHANGED, (type)=>{
 if (type & Node.TransformBit.POSITION) {
      //...
  }
}, this);
```
- TRANSFORM_CHANGED = `"transform-changed"`

### NODE_DESTROYED
> 目标节点被销毁时触发的事件。

- NODE_DESTROYED = `"node-destroyed"`

### LAYER_CHANGED
> 节点 layer 改变时触发的事件。

- LAYER_CHANGED = `"layer-changed"`

### SCENE_CHANGED_FOR_PERSISTS
> 当场景常驻节点的场景发生改变时触发的事件，一般在切换场景过程中触发。

- SCENE_CHANGED_FOR_PERSISTS = `"scene-changed-for-persists"`

### SIZE_CHANGED
> 当节点尺寸改变时触发的事件。

**性能警告**：这个事件会在每次对应的属性被修改时触发，如果事件回调损耗较高，有可能对性能有很大的负面影响，请尽量避免这种情况。

- SIZE_CHANGED = `"size-changed"`

### ANCHOR_CHANGED
> 当节点的 UITransform 锚点改变时触发的事件。

**性能警告**：这个事件会在每次对应的属性被修改时触发，如果事件回调损耗较高，有可能对性能有很大的负面影响，请尽量避免这种情况。

- ANCHOR_CHANGED = `"anchor-changed"`

### COLOR_CHANGED
> 当节点的 UI 渲染组件颜色属性改变时触发的事件。

**性能警告**：这个事件会在每次对应的属性被修改时触发，如果事件回调损耗较高，有可能对性能有很大的负面影响，请尽量避免这种情况。

- COLOR_CHANGED = `"color-changed"`

---
### CHILD_ADDED
给目标节点添加子节点时触发的事件。

- CHILD_ADDED = `"child-added"`

### CHILD_REMOVED
> 给目标节点移除子节点时触发的事件。

- CHILD_REMOVED = `"child-removed"`

### PARENT_CHANGED
> 目标节点的父节点改变时触发的事件。

- PARENT_CHANGED = `"parent-changed"`

### SIBLING_ORDER_CHANGED
> 当节点在兄弟节点中的顺序发生变化时触发的事件。

- SIBLING_ORDER_CHANGED = `"sibling-order-changed"`
