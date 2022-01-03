# 类: Node
继承于: [BaseNode](BaseNode.md "Node基类")

Cocos Creator 场景中的所有节点类。 基本特性有：

- 具有层级关系
- 持有各类组件
- 维护 3D 空间左边变换（坐标、旋转、缩放）信息

## 目录
### 属性
- `static` reserveContentsForAllSyncablePrefabTag
- `static` [（枚举）TransformBit](#TransformBit)
- `static` NodeSpace
- `static` [（枚举）EventType 节点事件类型](#EventType)
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
## •属性

### （枚举）TransformBit
节点变换更新的具体部分，可用于判断 `NodeEventType.TRANSFORM_CHANGED` 事件的具体类型。

- `static` TransformBit: [TransformBit](Node_Enum_TransformBit.md "点击查看所有 “节点变换” 枚举类型") = TransformBit

```typescript
this.node.on(Node.EventType.TRANSFORM_CHANGED, (type)=>{
 if (type & Node.TransformBit.POSITION) {
      //...
  }
}, this);
```

### （枚举）EventType
> 节点可能发出的事件类型

- `static` EventType: [NodeEventType](Node_Enum_NodeEventType.md "点击查看所有节点监听事件类型") = `NodeEventType`
