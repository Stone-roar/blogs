[（🔙返回上一级）](目录_Event.md "event模块") 
## 类: SystemEvent

`extend: ` [IEventified](https://docs.cocos.com/creator/api/zh/#/docs/3.4/zh/event/Interface/IEventified)

系统事件，它目前支持按键事件和重力感应事件。
你可以通过 `systemEvent` 获取到 `SystemEvent` 的实例。

**`deprecated`** since v3.4.0, please use Input class instead.

**`example`**

```typescript
import { systemEvent, SystemEvent } from 'cc';
systemEvent.on(SystemEvent.EventType.DEVICEMOTION, this.onDeviceMotionEvent, this);
systemEvent.off(SystemEvent.EventType.DEVICEMOTION, this.onDeviceMotionEvent, this);
```

## 目录

### 属性

* [**`static`** EventType 事件类型](#EventType_index)

### 方法
* [`on` 事件注册](#on)
* [`once` 一次性事件注册](#once)
* [`off` 事件注销](#off)
* [`targetOff` 移除目标上的所有注册事件](#targetOff)
* [`removeAll：`
1、移除在特定事件类型中注册的所有回调；
2、或在某个目标中注册的所有回调。](#removeall)
* [`hasEventListener` 检查事件目标是否有为特定类型的事件注册的回调](#hasEventListener)
* [`emit` 通过事件名发送自定义事件](#emit)
.
* [`setAccelerometerEnabled` 是否启用加速度计事件](#setaccelerometerenabled)
* [`setAccelerometerInterval` 设置加速度计间隔值](#setaccelerometerinterval)


---

## 属性

<h3 id="EventType_index">EventType</h3>

SystemEvent 支持的事件类型以及节点事件类型

- `static` **EventType**: `EnumAlias`<> = `SystemEventType`
--------------------

## 方法

### emit

• **emit**(`type`: `EventType`, `arg0`: `any`, `arg1`: `any`, `arg2`: `any`, `arg3`: `any`, `arg4`: `any`) :  `void`

派发一个指定事件，并传递需要的参数

#### 参数

| Name | Type | Description |
| :-: | :-: | :-: |
| `type` | `EventType` | event type |
| `arg0` | `any` | - |
| `arg1` | `any` | - |
| `arg2` | `any` | - |
| `arg3` | `any` | - |
| `arg4` | `any` | - |

##### Returns `void`

---

### hasEventListener

- **hasEventListener**(`type`: string, `callback`: undefined \| undefined, `target`: `any`) :  boolean

检查指定事件是否已注册回调。

#### 参数

| Name | Type | Description |
| :-: | :-: | :-: |
| `type` | string | Event type. |
| `callback` | undefined \| undefined | Callback function when event triggered. |
| `target` | `any` | Callback callee. |

##### Returns `void`

---

### off

• **off**(`type`: `K`, `callback`: undefined, `target`: `any`) :  void

删除之前用同类型，回调，目标或 useCapture 注册的事件监听器，如果只传递 type，将会删除 type 类型的所有事件监听器。

#### 参数

| Name | Type | Description |
| :-: | :-: | :-: |
| `type` | `K` | A string representing the event type being removed. |
| `callback` | undefined | The callback to remove. |
| `target` | `any` | The target (this object) to invoke the callback, if it's not given, only callback without target will be removed |

##### Returns `void`

---

### on

• **on**(`type`: `K`, `callback`: undefined, `target`: `any`, `once`: `undefined` | `false` | `true`) : `SystemEventMap[K]`

注册特定事件类型回调。

#### 参数

| Name | Type | Description |
| :-: | :-: | :-: |
| `type` | `K` | The event type |
| `callback` | undefined | The event listener's callback |
| `target` | `any` | The event listener's target and callee |
| `once` | undefined \| `false` \| `true` | Register the event listener once |

##### Returns  `SystemEventMap[K]`

---

### once

• **once**(`type`: `EventType`, `callback`: `TFunction`, `thisArg`: `any`)

注册事件目标的特定事件类型回调，回调会在第一时间被触发后删除自身。

**`example`**

```typescript
import { log } from 'cc';
eventTarget.once('fire', function () {
    log("this is the callback and will be invoked only once");
}, node);
```

#### 参数

| Name | Type | Description |
| :-: | :-: | :-: |
| `type` | `EventType` | A string representing the event type to listen for. |
| `callback` | `TFunction` | The callback that will be invoked when the event is dispatched. The callback is ignored if it is a duplicate (the callbacks are unique). |
| `thisArg` | `any` | - |

##### Returns `undefined`

---

### removeAll
• **removeAll**(`typeOrTarget`: `any`) :  void

移除在特定事件类型中注册的所有回调或在某个目标中注册的所有回调。

#### 参数

| Name | Type | Description |
| :-: | :-: | :-: |
| `typeOrTarget` | `any` | The event type or target with which the listeners will be removed |

##### Returns `void`

---

### setAccelerometerEnabled

• **setAccelerometerEnabled**(`isEnabled`: boolean) :  void

是否启用加速度计事件。

#### 参数

| Name | Type | Description |
| :-: | :-: | :-: |
| `isEnabled` | boolean | - |

##### Returns `void`

---

### setAccelerometerInterval

• **setAccelerometerInterval**(`interval`: number) :  void

设置加速度计间隔值。

#### 参数

| Name | Type | Description |
| :-: | :-: | :-: |
| `interval` | number | - |

##### Returns `void`

---

### targetOff

• **targetOff**(`typeOrTarget`: `any`) :  void

在当前 EventTarget 上删除指定目标（target 参数）注册的所有事件监听器。 这个函数无法删除当前 EventTarget 的所有事件监听器，也无法删除 target 参数所注册的所有事件监听器。 这个函数只能删除 target 参数在当前 EventTarget 上注册的所有事件监听器。

#### 参数

| Name | Type | Description |
| :-: | :-: | :-: |
| `typeOrTarget` | `any` | The target to be searched for all related listeners |

##### Returns `void`
