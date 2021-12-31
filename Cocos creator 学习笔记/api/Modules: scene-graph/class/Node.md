# 类: Node
`extend: `[BaseNode](https://github.com/Stone-roar/blogs/edit/main/Cocos%20creator%20%E5%AD%A6%E4%B9%A0%E7%AC%94%E8%AE%B0/api/Modules:%20scene-graph/class/BaseNode.md "Node基类")

Cocos Creator 场景中的所有节点类。 基本特性有：

- 具有层级关系
- 持有各类组件
- 维护 3D 空间左边变换（坐标、旋转、缩放）信息

## 目录
### 属性
- `static` reserveContentsForAllSyncablePrefabTag
- `static` TransformDirtyBit
- `static` TransformBit
- `static` NodeSpace
- `static` EventType
- [editorExtrasTag]
- active
- activeInHierarchy
- angle
- children
- components
- eulerAngles
- eventProcessor
- forward
- hasChangedFlags
- hideFlags
- isValid
- layer
- matrix
- name
- native
- parent
- position
- replicated
- right
- rotation
- scale
- scene
- up
- uuid
- worldMatrix
- worldPosition
- worldRotation
- worldScale

### 构造函数
- constructor

### 方法
- `static` resetHasChangedFlags
- `static` isNode
- `static` clearNodeArray
- [serializeTag]
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
- getPosition
- getRotation
- getScale
- getSiblingIndex
- getWorldMatrix
- getWorldPosition
- getWorldRS
- getWorldRT
- getWorldRotation
- getWorldScale
- hasEventListener
- insertChild
- invalidateChildren
- inverseTransformPoint
- isChildOf
- lookAt
- off
- on
- once
- pauseSystemEvents
- removeAllChildren
- removeChild
- removeComponent
- removeFromParent
- resumeSystemEvents
- rotate
- setParent
- setPosition
- setRTS
- setRotation
- setRotationFromEuler
- setScale
- setSiblingIndex
- setWorldPosition
- setWorldRotation
- setWorldRotationFromEuler
- setWorldScale
- targetOff
- translate
- updateWorldTransform
- walk
----------
## 属性
