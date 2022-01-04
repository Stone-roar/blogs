# 类: Node
继承于: [BaseNode](BaseNode.md "Node基类")

Cocos Creator 场景中的所有节点类。 基本特性有：

- 具有层级关系
- 持有各类组件
- 维护 3D 空间左边变换（坐标、旋转、缩放）信息

## 目录
### 属性
* 同 class [**BaseNode**](BaseNode.md "Node基类")
    * 基础属性
        * [`name` 节点名称](#name)
        * [`uuid`](#uuid "uuid")
    * 状态
        * [`active` 节点自身激活状态](#active)
        * [`activeInHierarchy` 节点在场景中的激活状态](#activeInHierarchy)
        * [`eventProcessor` 当前节点的事件处理器](#eventProcessor)
    * 族系
        * [`components` 获取附加到此节点的所有组件](#components)
        * [`children` 节点的所有子节点](#children)
        * [`parent` 其父节点](#parent)
        * [`scene` 此节点属于哪个场景](#scene)
    * 同 class CCObject
        * [`isValid` 该对象是否可用](#isValid)
        * [`hideFlags`](#hideFlags)
        * [`replicated`](#replicated)
*  **Node**
    * static
        * `static` [reserveContentsForAllSyncablePrefabTag](#reserveContentsForAllSyncablePrefabTag)
        * `static` [（枚举）TransformBit](#TransformBit_index)
        * `static` [（枚举）EventType 节点事件类型](#EventType_index)
        * `static` [NodeSpace 空间变换操作的坐标系](#NodeSpace)
    * 基础属性
        * [`layer` 节点所属层](#layer)
        * [`native`](#native)
        * [`editorExtrasTag`]
    * 方向向量
        * [`forward` 节点朝前方](#forward)
        * [`right` 节点朝右方向](#right)
        * [`up` 节点朝上方向](#up)
    * 节点的变换（位置、旋转、变换、缩放）
        * [`position` 本地坐标](#position)
        * [`worldPosition` 世界坐标](#worldPosition)
.
        * [`angle` 本地坐标系下z轴的旋转角度](#angle)
        * [`eulerAngles` 本地坐标系下的旋转-Vec3](#eulerAngles)
.
        * [`rotation` 本地坐标系下的旋转](#rotation)
        * [`worldRotation` 世界坐标系下的旋转](#worldRotation)
.
        * [`hasChangedFlags` 在当前帧内节点的空间变换信息是否有变过](#hasChangedFlags)
        * [`matrix` 本地坐标系变换矩阵](#matrix)
        * [`worldMatrix` 世界坐标系变换矩阵](#worldMatrix)
.
        * [`scale` 本地坐标系下的缩放](#scale)
        * [`worldScale` 世界坐标系下的缩放](#worldScale)



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

------
## 属性
[（🆙回到顶部）](#目录)
### name
> 该节点名称。

- name: `string`

### uuid
> 主要用于编辑器的 uuid，在编辑器下可用于持久化存储，在项目构建之后将变成自增的 id。

- uuid: `string`

------
### active
> 当前节点的自身激活状态。

值得注意的是，一个节点的父节点如果不被激活，那么即使它自身设为激活，它仍然无法激活。 如果你想检查节点在场景中实际的激活状态可以使用 `activeInHierarchy`。

默认值：`true`

- active: boolean

### activeInHierarchy
> 表示此节点是否在场景中激活。

- activeInHierarchy: `boolean`

### eventProcessor
> 当前节点的事件处理器，提供 EventTarget 能力。

- eventProcessor: `any`

------
### components
> 获取附加到此节点的所有组件。

- components: ReadonlyArray<Component>

### children
> 节点的所有子节点。

- children: `array`

### parent
> 父节点

- parent: `null | this`

### scene
> 此节点属于哪个场景。

- scene: `Scene`

------
### isValid
> 表示该对象是否可用（被 destroy 后将不可用）。

当一个对象的 destroy 调用以后，会在这一帧结束后才真正销毁。
因此从下一帧开始 isValid 就会返回 false，而当前帧内 isValid 仍然会是 true。
如果希望判断当前帧是否调用过 destroy，请使用 isValid(obj, true)，不过这往往是特殊的业务需求引起的，通常情况下不需要这样。

默认值为：`true`

例子：
```typescript
import { Node, log } from 'cc';
const node = new Node();
log(node.isValid);    // true
node.destroy();
log(node.isValid);    // true, still valid in this frame
// after a frame...
log(node.isValid);    // false, destroyed in the end of last frame
```
- isValid: `boolean`

### hideFlags
> 在继承 CCObject 对象后，控制是否需要隐藏，锁定，序列化等功能。

- hideFlags: `Flags`

### replicated
- replicated: `boolean`

------
[（🆙回到顶部）](#目录)
### reserveContentsForAllSyncablePrefabTag
机翻：“保留所有可同步预制标记的内容”。
- `static` reserveContentsForAllSyncablePrefabTag: `symbol` = `reserveContentsForAllSyncablePrefabTag`

<h3 id="TransformBit_index">（枚举）TransformBit</h3>
节点变换更新的具体部分，可用于判断 `NodeEventType.TRANSFORM_CHANGED` 事件的具体类型。

- `static` TransformBit: [TransformBit](Node_Enum_TransformBit.md "点击查看所有 “节点变换” 枚举类型") = TransformBit

```typescript
this.node.on(Node.EventType.TRANSFORM_CHANGED, (type)=>{
 if (type & Node.TransformBit.POSITION) {
      //...
  }
}, this);
```

<h3 id="EventType_index">（枚举）EventType</h3>
> 节点可能发出的事件类型

- `static` EventType: [NodeEventType](Node_Enum_NodeEventType.md "点击查看所有节点监听事件类型") = `NodeEventType`

### NodeSpace
> 空间变换操作的坐标系

- `static` NodeSpace: NodeSpace = `NodeSpace`

---
### layer
> 节点所属层，主要影响射线检测、物理碰撞等，参考 [[Layers]]

- layer: `number`

### native
- native: `any`

---
### forward
> 当前节点面向的前方方向，默认前方为 -z 方向

- forward: `Vec3`

### right
> 返回当前节点在世界空间中朝右的方向向量

- right: `Vec3`

### up
返回当前节点在世界空间中朝上的方向向量

- up: `Vec3`

---
### position
> 本地坐标系下的坐标

- position: `Readonly<Vec3>`

### worldPosition
> 世界坐标系下的坐标

- worldPosition: `Readonly<Vec3>`

---
### angle
> 本地坐标系下的旋转，用欧拉角表示，但是限定在 z 轴上。

- angle: `number`

### eulerAngles
> 本地坐标系下的旋转，用欧拉角表示

- eulerAngles: `Readonly<Vec3>`
---
### rotation
> 本地坐标系下的旋转，用四元数表示

- rotation: `Readonly<Quat>`

### worldRotation
> 世界坐标系下的旋转，用四元数表示

- worldRotation: `Readonly<Quat>`

---
### hasChangedFlags
> 这个节点的空间变换信息在当前帧内是否有变过？

- hasChangedFlags: `number`

### matrix
> 本地坐标系变换矩阵

- matrix:`Readonly<Mat4>`

### worldMatrix
> 世界坐标系变换矩阵

- worldMatrix: `Readonly<Mat4>`

---
### scale
> 本地坐标系下的缩放

- scale: `Readonly<Vec3>`

### worldScale
> 世界坐标系下的缩放

- worldScale: `Readonly<Vec3>`
