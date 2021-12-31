# 类: Node
`extend: `[BaseNode](https://github.com/Stone-roar/blogs/edit/main/Cocos%20creator%20%E5%AD%A6%E4%B9%A0%E7%AC%94%E8%AE%B0/api/Modules:%20scene-graph/class/BaseNode.md "Node基类")

Cocos Creator 场景中的所有节点类。 基本特性有：

- 具有层级关系
- 持有各类组件
- 维护 3D 空间左边变换（坐标、旋转、缩放）信息

## 目录
### 属性
- [editorExtrasTag]
- active
- activeInHierarchy
- children
- components
- eventProcessor
- hideFlags
- isValid
- name
- parent
- replicated
- scene
- uuid

### 枚举
- `static` Flags

### 构造函数
- constructor

### 方法
- addChild
- addComponent
- attr
- destroy
- destroyAllChildren
- dispatchEvent
- emit
- getChildByName
- getChildByPath
- getChildByUuid
- getComponent
- getComponentInChildren
- getComponents
- getComponentsInChildren
- getParent
- getSiblingIndex
- hasEventListener
- insertChild
- isChildOf
- off
- on
- once
- removeAllChildren
- removeChild
- removeComponent
- removeFromParent
- setParent
- setSiblingIndex
- targetOff
- walk
