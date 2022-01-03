# 类: BaseNode
[Node](Node.md "Node") 的基类，他会负责：

- 维护场景树以及节点生命周期管理
- 提供 EventTarget 的事件管理和注册能力
- 派发节点状态相关的事件，参考：[[Node.EventType]]
- 管理组件

## 目录
### 属性
* 基础属性
    * [`name` 节点名称](#name)
    * [`uuid`](#uuid)
* 状态
    * [`active` 节点自身激活状态](#active)
    * [`activeInHierarchy` 节点在场景中的激活状态](#activeInHierarchy)
    * [`eventProcessor` 当前节点的事件处理器](#eventProcessor)
* 族系
    * [`components` 获取附加到此节点的所有组件](#components)
    * [`children` 节点的所有子节点](#children)
    * [`parent` 其父节点](#parent)
    * [`scene` 此节点属于哪个场景](#scene)
* CCObject
    * [`isValid` 该对象是否可用](#isValid)
    * [`hideFlags`](#hideFlags)
    * [`replicated`](#replicated)








------
## 属性
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
