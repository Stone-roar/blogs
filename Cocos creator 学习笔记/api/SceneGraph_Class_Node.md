[ï¼ðè¿åä¸ä¸çº§ï¼](ç®å½_SceneGraph.md "scene-graphæ¨¡å")
# ç±»: Node
ç»§æ¿äº: [BaseNode](SceneGraph_Class_BaseNode.md "èç¹åºç±»")

Cocos Creator åºæ¯ä¸­çææèç¹ç±»ã åºæ¬ç¹æ§æï¼

- å·æå±çº§å³ç³»
- ææåç±»ç»ä»¶
- ç»´æ¤ 3D ç©ºé´å·¦è¾¹åæ¢ï¼åæ ãæè½¬ãç¼©æ¾ï¼ä¿¡æ¯

## ç®å½
### å±æ§

* å class [**BaseNode**](SceneGraph_Class_BaseNode.md "èç¹åºç±»")
  * å class CCObject
    * [`isValid` è¯¥å¯¹è±¡æ¯å¦å¯ç¨](#isValid)
    * [`hideFlags`](#hideFlags)
    * [`replicated`](#replicated)
  * åºç¡å±æ§
    * [`name` èç¹åç§°](#name)
    * [`uuid`](#uuid "uuid")
  * ç¶æ
    * [`active` èç¹èªèº«æ¿æ´»ç¶æ](#active)
    * [`activeInHierarchy` èç¹å¨åºæ¯ä¸­çæ¿æ´»ç¶æ](#activeInHierarchy)
    * [`eventProcessor` å½åèç¹çäºä»¶å¤çå¨](#eventProcessor)
  * æç³»
    * [`components` è·åéå å°æ­¤èç¹çææç»ä»¶](#components)
    * [`children` èç¹çææå­èç¹](#children)
    * [`parent` å¶ç¶èç¹](#parent)
    * [`scene` æ­¤èç¹å±äºåªä¸ªåºæ¯](#scene)
.
* **Node**
  * static
    * `static` [`reserveContentsForAllSyncablePrefabTag`](#reserveContentsForAllSyncablePrefabTag)
    * `static` [`ï¼æä¸¾ï¼TransformBit` èç¹çç©ºé´åæ¢ä½ **æ è®°**](#TransformBit_index)
    * `static` [`ï¼æä¸¾ï¼EventType` èç¹äºä»¶ç±»å](#EventType_index)
    * `static` [`ï¼æä¸¾ï¼NodeSpace` ç©ºé´åæ¢æä½çåæ ç³»](#NodeSpace_index)
  * åºç¡å±æ§
    * [`layer` èç¹æå±å±](#layer)
    * [`native`](#native)
    * [`editorExtrasTag`]
  * æ¹ååé
    * [`forward` èç¹æåæ¹](#forward)
    * [`right` èç¹æå³æ¹å](#right)
    * [`up` èç¹æä¸æ¹å](#up)
  * èç¹çåæ¢ï¼ä½ç½®ãæè½¬ãåæ¢ãç¼©æ¾ï¼
    * [`position` æ¬å°åæ ](#position)
    * [`worldPosition` ä¸çåæ ](#worldPosition)
.
    * [`angle` æ¬å°åæ ç³»ä¸zè½´çæè½¬è§åº¦](#angle)
    * [`eulerAngles` æ¬å°åæ ç³»ä¸çæè½¬-Vec3](#eulerAngles)
.
    * [`rotation` æ¬å°åæ ç³»ä¸çæè½¬](#rotation)
    * [`worldRotation` ä¸çåæ ç³»ä¸çæè½¬](#worldRotation)
.
    * [`hasChangedFlags` å¨å½åå¸§åèç¹çç©ºé´åæ¢ä¿¡æ¯æ¯å¦æåè¿](#hasChangedFlags)
    * [`matrix` æ¬å°åæ ç³»åæ¢ç©éµ](#matrix)
    * [`worldMatrix` ä¸çåæ ç³»åæ¢ç©éµ](#worldMatrix)
.
    * [`scale` æ¬å°åæ ç³»ä¸çç¼©æ¾](#scale)
    * [`worldScale` ä¸çåæ ç³»ä¸çç¼©æ¾](#worldScale)



### æé å½æ°
*  [constructor](#æé å½æ°)

### æ¹æ³
* å class [**BaseNode**](SceneGraph_Class_BaseNode.md "Nodeåºç±»")
  * èç¹å±æ§éç½®
    *  [`attr` èç¹å±æ§éç½®å½æ°](#attr)
  * äºä»¶ç¸å³
    *  [`on` äºä»¶æ³¨å](#on)
    *  [`once` ä¸æ¬¡æ§äºä»¶æ³¨å](#once)
    *  [`off` äºä»¶æ³¨é](#off)
    *  [`targetOff` ç§»é¤ç®æ ä¸çæææ³¨åäºä»¶](#targetOff)
    *  [`hasEventListener` æ£æ¥äºä»¶ç®æ æ¯å¦æä¸ºç¹å®ç±»åçäºä»¶æ³¨åçåè°](#hasEventListener)
    *  [`emit` éè¿äºä»¶ååéèªå®ä¹äºä»¶](#emit)
    *  [`dispatchEvent` ååäºä»¶å°äºä»¶æµä¸­](#dispatchEvent)
  * ç»ä»¶ç¸å³æ¹æ³
    *  [`addComponent` åèç¹æ·»å ä¸ä¸ªæå®ç±»åçç»ä»¶ç±»](#addComponent)
    *  [`getComponent`](#getComponent)
    *  [`getComponentInChildren`](#getComponentInChildren)
    *  [`getComponents`](#getComponents)
    *  [`getComponentsInChildren`](#getComponentsInChildren)
    *  [`removeComponent`](#removeComponent)
  * æç³»ç¸å³æ¹æ³
    *  [`walk`](#walk)
.
    *  [`setParent`](#setParent)
    *  [`getParent`](#getParent)
.
    *  [`addChild`](#addChild)
    *  [`insertChild`](#insertChild)
    *  [`isChildOf`](#isChildOf)
    *  [`getChildByName`](#getChildByName)
    *  [`getChildByPath`](#getChildByPath)
    *  [`getChildByUuid`](#getChildByUuid)
    *  [`removeFromParent`](#removeFromParent)
.
    *  [`setSiblingIndex`](#setSiblingIndex)
    *  [`getSiblingIndex`](#getSiblingIndex)
    *  [`removeChild`](#removeChild)
    *  [`removeAllChildren`](#removeAllChildren)
.
    *  [`destroy`](#destroy)
    *  [`destroyAllChildren`](#destroyAllChildren)
.
* **Node**
  * static
    *  `static` [`resetHasChangedFlags`](#resetHasChangedFlags)
    *  `static` [`isNode`](#isNode)
    *  `static` [`clearNodeArray`](#clearNodeArray)
    *  [serializeTag]
  * äºä»¶ç¸å³
    *  [`pauseSystemEvents`](#pauseSystemEvents)
    *  [`resumeSystemEvents`](#resumeSystemEvents)
  * èç¹çåæ¢ç¸å³æ¹æ³ï¼ä½ç½®ãç§»å¨ãæè½¬ãåæ¢ãç¼©æ¾ï¼
    *  [`invalidateChildren`](#invalidateChildren)
.
    *  [`updateWorldTransform`](#updateWorldTransform)
.
    *  [`setPosition`](#setPosition)
    *  [`getPosition`](#getPosition)
    *  [`setWorldPosition`](#setWorldPosition)
    *  [`getWorldPosition`](#getWorldPosition)
    *  [`inverseTransformPoint`](#inverseTransformPoint)
.
    *  [`lookAt`](#lookAt)
    *  [`translate`](#translate)
    *  [`rotate`](#rotate)
.
    *  [`setRotation`](#setRotation)
    *  [`setRotationFromEuler`](#setRotationFromEuler)
    *  [`getRotation`](#getRotation)
    *  [`setWorldRotation`](#setWorldRotation)
    *  [`setWorldRotationFromEuler`](#setWorldRotationFromEuler)
    *  [`getWorldRotation`](#getWorldRotation)
.
    *  [`getWorldMatrix`](#getWorldMatrix)
.
    *  [`setScale`](#setScale)
    *  [`getScale`](#getScale)
    *  [`setWorldScale`](#setWorldScale)
    *  [`getWorldScale`](#getWorldScale)
.
    *  [`setRTS`](#setRTS)
    *  [`getWorldRS`](#getWorldRS)
    *  [`getWorldRT`](#getWorldRT)

------
# å±æ§
[ï¼ðåå°é¡¶é¨ï¼](#ç®å½)
## åºç¡å±æ§
### name
> è¯¥èç¹åç§°ã

- name: `string`

---
### uuid
> ä¸»è¦ç¨äºç¼è¾å¨ç uuidï¼å¨ç¼è¾å¨ä¸å¯ç¨äºæä¹åå­å¨ï¼å¨é¡¹ç®æå»ºä¹åå°åæèªå¢ç idã

- uuid: `string`

------
## èç¹ç¶æ
### active
> å½åèç¹çèªèº«æ¿æ´»ç¶æã

å¼å¾æ³¨æçæ¯ï¼ä¸ä¸ªèç¹çç¶èç¹å¦æä¸è¢«æ¿æ´»ï¼é£ä¹å³ä½¿å®èªèº«è®¾ä¸ºæ¿æ´»ï¼å®ä»ç¶æ æ³æ¿æ´»ã å¦æä½ æ³æ£æ¥èç¹å¨åºæ¯ä¸­å®éçæ¿æ´»ç¶æå¯ä»¥ä½¿ç¨ `activeInHierarchy`ã

é»è®¤å¼ï¼`true`

- active: boolean

---
### activeInHierarchy
> è¡¨ç¤ºæ­¤èç¹æ¯å¦å¨åºæ¯ä¸­æ¿æ´»ã

- activeInHierarchy: `boolean`

---
### eventProcessor
> å½åèç¹çäºä»¶å¤çå¨ï¼æä¾ EventTarget è½åã

- eventProcessor: `any`

------
## æç³»
### components
> è·åéå å°æ­¤èç¹çææç»ä»¶ã

- components: ReadonlyArray<Component>

### children
> èç¹çææå­èç¹ã

- children: `array`

### parent
> ç¶èç¹

- parent: `null | this`

### scene
> æ­¤èç¹å±äºåªä¸ªåºæ¯ã

- scene: `Scene`

------
### isValid
> è¡¨ç¤ºè¯¥å¯¹è±¡æ¯å¦å¯ç¨ï¼è¢« destroy åå°ä¸å¯ç¨ï¼ã

å½ä¸ä¸ªå¯¹è±¡ç destroy è°ç¨ä»¥åï¼ä¼å¨è¿ä¸å¸§ç»æåæçæ­£éæ¯ã
å æ­¤ä»ä¸ä¸å¸§å¼å§ isValid å°±ä¼è¿å falseï¼èå½åå¸§å isValid ä»ç¶ä¼æ¯ trueã
å¦æå¸æå¤æ­å½åå¸§æ¯å¦è°ç¨è¿ destroyï¼è¯·ä½¿ç¨ isValid(obj, true)ï¼ä¸è¿è¿å¾å¾æ¯ç¹æ®çä¸å¡éæ±å¼èµ·çï¼éå¸¸æåµä¸ä¸éè¦è¿æ ·ã

é»è®¤å¼ä¸ºï¼`true`

ä¾å­ï¼
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
> å¨ç»§æ¿ CCObject å¯¹è±¡åï¼æ§å¶æ¯å¦éè¦éèï¼éå®ï¼åºååç­åè½ã

- hideFlags: `Flags`

### replicated
- replicated: `boolean`

------
[ï¼ðåå°é¡¶é¨ï¼](#ç®å½)
## æä¸¾æ è®°
### reserveContentsForAllSyncablePrefabTag
æºç¿»ï¼âä¿çææå¯åæ­¥é¢å¶æ è®°çåå®¹âã
- `static` reserveContentsForAllSyncablePrefabTag: `symbol` = `reserveContentsForAllSyncablePrefabTag`

---
<h3 id="TransformBit_index">ï¼æä¸¾ï¼TransformBit</h3>

> èç¹çç©ºé´åæ¢ä½**æ è®°**

èç¹åæ¢æ´æ°çå·ä½é¨åï¼å¯ç¨äºå¤æ­ `NodeEventType.TRANSFORM_CHANGED` äºä»¶çå·ä½ç±»åã

- `static` TransformBit: [TransformBit](SceneGraph_Enum_TransformBit.md "ç¹å»æ¥çææ âèç¹åæ¢â æä¸¾ç±»å") = TransformBit

```typescript
this.node.on(Node.EventType.TRANSFORM_CHANGED, (type)=>{
 if (type & Node.TransformBit.POSITION) {
      //...
  }
}, this);
```

---
<h3 id="EventType_index">ï¼æä¸¾ï¼EventType</h3>

> èç¹å¯è½ååºçäºä»¶ç±»å

- `static` EventType: [NodeEventType](SceneGraph_Enum_Node.EventType.md "ç¹å»æ¥çææèç¹çå¬äºä»¶ç±»å") = `NodeEventType`

---
<h3 id="NodeSpace_index">ï¼æä¸¾ï¼NodeSpace</h3>

> ç©ºé´åæ¢æä½çåæ ç³» **æ è®°**ï¼æ¬å°åæ ç³» Or ä¸çåæ ç³»

- `static` NodeSpace: [NodeSpace](SceneGraph_Enum_NodeSpace.md) = `NodeSpace`

---
## åºç¡å±æ§
### layer
> èç¹æå±å±ï¼ä¸»è¦å½±åå°çº¿æ£æµãç©çç¢°æç­ï¼åè [[Layers]]

- layer: `number`

---
### native
- native: `any`

---
## æ¹ååé
### forward
> å½åèç¹é¢åçåæ¹æ¹åï¼é»è®¤åæ¹ä¸º -z æ¹å

- forward: `Vec3`

---
### right
> è¿åå½åèç¹å¨ä¸çç©ºé´ä¸­æå³çæ¹ååé

- right: `Vec3`

---
### up
è¿åå½åèç¹å¨ä¸çç©ºé´ä¸­æä¸çæ¹ååé

- up: `Vec3`

---
## èç¹çåæ¢ââä½ç½®
### position
> æ¬å°åæ ç³»ä¸çåæ 

- position: `Readonly<Vec3>`

---
### worldPosition
> ä¸çåæ ç³»ä¸çåæ 

- worldPosition: `Readonly<Vec3>`

---
## èç¹çåæ¢ââæè½¬
### angle
> æ¬å°åæ ç³»ä¸çæè½¬ï¼ç¨æ¬§æè§è¡¨ç¤ºï¼ä½æ¯éå®å¨ z è½´ä¸ã

- angle: `number`

---
### eulerAngles
> æ¬å°åæ ç³»ä¸çæè½¬ï¼ç¨æ¬§æè§è¡¨ç¤º

- eulerAngles: `Readonly<Vec3>`
---
### rotation
> æ¬å°åæ ç³»ä¸çæè½¬ï¼ç¨ååæ°è¡¨ç¤º

- rotation: `Readonly<Quat>`

---
### worldRotation
> ä¸çåæ ç³»ä¸çæè½¬ï¼ç¨ååæ°è¡¨ç¤º

- worldRotation: `Readonly<Quat>`

---
## èç¹çåæ¢ââåæ¢
### hasChangedFlags
> è¿ä¸ªèç¹çç©ºé´åæ¢ä¿¡æ¯å¨å½åå¸§åæ¯å¦æåè¿ï¼

- hasChangedFlags: `number`

---
### matrix
> æ¬å°åæ ç³»åæ¢ç©éµ

- matrix:`Readonly<Mat4>`

---
### worldMatrix
> ä¸çåæ ç³»åæ¢ç©éµ

- worldMatrix: `Readonly<Mat4>`

---
## èç¹çåæ¢ââç¼©æ¾
### scale
> æ¬å°åæ ç³»ä¸çç¼©æ¾

- scale: `Readonly<Vec3>`

---
### worldScale
> ä¸çåæ ç³»ä¸çç¼©æ¾

- worldScale: `Readonly<Vec3>`

---
# æé å½æ°



---
# æ¹æ³
## èç¹å±æ§éç½®æ¹æ³
[ï¼ðåå°é¡¶é¨ï¼](#ç®å½)
### attr
- **attr**(`attrs`: `unknown`) :  void

å±æ§éç½®å½æ°ãå¨ attrs çææå±æ§å°è¢«è®¾ç½®ä¸ºèç¹å±æ§ã

**ä¾å­ï¼**

```typescript
var attrs = { name: 'New Name', active: false };
node.attr(attrs);
```

---
## èç¹äºä»¶ç¸å³æ¹æ³
### on

- **on**(type: `string` | `NodeEventType`, callback: `AnyFunction`, target?: `unknown`, useCapture?: `any`) :  `void`

å¨èç¹ä¸æ³¨åæå®ç±»åçåè°å½æ°ï¼ä¹å¯ä»¥è®¾ç½® target ç¨äºç»å®ååºå½æ°ç this å¯¹è±¡ã é¼ æ æè§¦æ¸äºä»¶ä¼è¢«ç³»ç»è°ç¨ dispatchEvent æ¹æ³è§¦åï¼è§¦åçè¿ç¨åå«ä¸ä¸ªé¶æ®µï¼

1. æè·é¶æ®µï¼æ´¾åäºä»¶ç»æè·ç®æ ï¼æ¯å¦ï¼èç¹æ ä¸­æ³¨åäºæè·é¶æ®µçç¶èç¹ï¼ä»æ ¹èç¹å¼å§æ´¾åç´å°ç®æ èç¹ã
2. ç®æ é¶æ®µï¼æ´¾åç»ç®æ èç¹ççå¬å¨ã
3. åæ³¡é¶æ®µï¼æ´¾åäºä»¶ç»åæ³¡ç®æ ï¼æ¯å¦ï¼èç¹æ ä¸­æ³¨åäºåæ³¡é¶æ®µçç¶èç¹ï¼ä»ç®æ èç¹å¼å§æ´¾åç´å°æ ¹èç¹ã åæ¶æ¨å¯ä»¥å°äºä»¶æ´¾åå°ç¶èç¹æèéè¿è°ç¨ stopPropagation æ¦æªå®ã ä½ ä¹å¯ä»¥æ³¨åèªå®ä¹äºä»¶å°èç¹ä¸ï¼å¹¶éè¿ emit æ¹æ³è§¦åæ­¤ç±»äºä»¶ï¼å¯¹äºè¿ç±»äºä»¶ï¼ä¸ä¼åçæè·åæ³¡é¶æ®µï¼åªä¼ç´æ¥æ´¾åç»æ³¨åå¨è¯¥èç¹ä¸ççå¬å¨ ä½ å¯ä»¥éè¿å¨ emit æ¹æ³è°ç¨æ¶å¨ type ä¹åä¼ éé¢å¤çåæ°ä½ä¸ºäºä»¶åè°çåæ°åè¡¨ã

**ä¾å­ï¼**

```typescript
this.node.on(NodeEventType.TOUCH_START, this.memberFunction, this);  // if "this" is component and the "memberFunction" declared in CCClass.
node.on(NodeEventType.TOUCH_START, callback, this);
node.on(NodeEventType.TOUCH_MOVE, callback, this);
node.on(NodeEventType.TOUCH_END, callback, this);
```

#### åæ°

| Name | Type | Description |
| :-: | :-: | :-: |
| `type` | `string` \| `NodeEventType` | `string` è¡¨ç¤ºè¦ä¾¦å¬çäºä»¶ç±»åçå­ç¬¦ä¸²ãæææå³åç½®äºä»¶è¯·æ¥é [Node.EventType](SceneGraph_Class_Node_Enum_NodeEventType.md "ç¹å»æ¥çææèç¹çå¬äºä»¶ç±»å") |
| `callback` | `AnyFunction` | **äºä»¶è§¦åæ¶æ§è¡çå½æ°**ãåè°å½æ°å·æå¯ä¸æ§ï¼éå¤çåè°å½æ°å°è¢«å¿½ç¥ã |
| `target?` | `unknown` | `target` è¡¨ç¤ºåè°å½æ°æ§è¡æ¶çthisæåï¼åè°å½æ°ç±è°è°ç¨ï¼ï¼å¯ä»¥ä¸º `null`ã |
| `useCapture?` | `any` | åªæèç¹äºä»¶æä¼è®¾ç½®è¿ä¸ªå¼ãå½ `useCapture?` è®¾ç½®ä¸º`true`æ¶ï¼åæ³¡é¡ºåºå°ä¸ååç¸åãWhen set to true, the listener will be triggered at capturing phase which is ahead of the final target emit, otherwise it will be triggered during bubbling phase. |

**Returns** `void`

---
### once
- **once**(type: `string`, callback: `AnyFunction`, target?: `unknown`, useCapture?: `any`) : `void `

æ³¨åèç¹çç¹å®äºä»¶ç±»ååè°ï¼åè°ä¼å¨ç¬¬ä¸æ¶é´è¢«è§¦ååå é¤èªèº«ã

#### åæ°

| Name | Type | Description |
| :-: | :-: | :-: |
| `type` | `string` | `string` è¡¨ç¤ºè¦ä¾¦å¬çäºä»¶ç±»åçå­ç¬¦ä¸²ã |
| `callback` | `AnyFunction` | äºä»¶è§¦åæ¶æ§è¡çå½æ°ãåè°å½æ°å·æå¯ä¸æ§ï¼éå¤çåè°å½æ°å°è¢«å¿½ç¥ã  |
| `target?` | `unknown` | `target` è¡¨ç¤ºåè°å½æ°æ§è¡æ¶çthisæåï¼åè°å½æ°ç±è°è°ç¨ï¼ï¼å¯ä»¥ä¸º `null`ã |
| `useCapture?` | `any` | - |

**Returns** `void`

---
### off
- **off**(type: `string`, callback?: `AnyFunction`, target?: `unknown`, useCapture?: `any`) : `void`

å é¤ä¹åä¸åç±»åï¼åè°ï¼ç®æ æ useCapture æ³¨åçåè°ã

**ä¾å­**

```typescript
this.node.off(NodeEventType.TOUCH_START, this.memberFunction, this);
node.off(NodeEventType.TOUCH_START, callback, this.node);
```

#### åæ°

| Name | Type | Description |
| :-: | :-: | :-: |
| `type` | `string` | `string` è¡¨ç¤ºè¦ä¾¦å¬çäºä»¶ç±»åçå­ç¬¦ä¸²ã |
| `callback?` | `AnyFunction` | äºä»¶è§¦åæ¶æ§è¡çå½æ°ãåè°å½æ°å·æå¯ä¸æ§ï¼éå¤çåè°å½æ°å°è¢«å¿½ç¥ã  |
| `target?` | `unknown` | `target` è¡¨ç¤ºåè°å½æ°æ§è¡æ¶çthisæåï¼åè°å½æ°ç±è°è°ç¨ï¼ï¼å¯ä»¥ä¸º `null`ã |
| `useCapture?` | `any` | - |

**Returns** `void`

---
### targetOff
- **targetOff**(target: `string` | `unknown`) : `void`

ç§»é¤ç®æ ä¸çæææ³¨åäºä»¶ã

#### åæ°

| Name | Type | Description |
| :-: | :-: | :-: |
| `target` | `string`\| `unknown` | The target to be searched for all related callbacks |

**Returns** `void`

---
### hasEventListener
- **hasEventListener**(type: `string`, callback: `AnyFunction`, target: `unknown`) : `any`

æ£æ¥äºä»¶ç®æ å¯¹è±¡æ¯å¦æä¸ºç¹å®ç±»åçäºä»¶æ³¨åçåè°ã

#### åæ°

| Name | Type | Description |
| :-: | :-: | :-: |
| `type` | string |äºä»¶ç±»å |
| `callback` | `AnyFunction` | äºä»¶è§¦åæ¶æ§è¡çå½æ°ï¼å¦ææç»å®çäºä»¶ç±»åçææçå¬å¨é½ä¸å­å¨è¯¥åè°å½æ°ï¼è¯¥å½æ°å°è¢«ç§»é¤ã|
| `target` | `unknown` | The callback called of the event listener |

**Returns** `any`

---
### emit
- **emit**(type: `string`, arg0: `any`, arg1: `any`, arg2: `any`, arg3: `any`, arg4: `any`) :  void

éè¿äºä»¶ååéèªå®ä¹äºä»¶

**ä¾å­**

```typescript
eventTarget.emit('fire', event);
eventTarget.emit('fire', message, emitter);
```

#### åæ°

| Name | Type | Description |
| :-: | :-: | :-: |
| `type` | `string` | event type |
| `arg0` | `any` | - |
| `arg1` | `any` | First argument in callback |
| `arg2` | `any` | Second argument in callback |
| `arg3` | `any` | Third argument in callback |
| `arg4` | `any` | Fourth argument in callback |

**Returns** `void`

---
### dispatchEvent
- **dispatchEvent**(event: `Event`) :  `void`

ååäºä»¶å°äºä»¶æµä¸­ã

#### åæ°

| Name | Type | Description |
| :-: | :-: | :-: |
| `event` | `Event` | The Event object that is dispatched into the event flow |

**Returns** `void`

---
## ç»ä»¶ç¸å³æ¹æ³
### addComponent

- **addComponent**(`classConstructor`: `Constructor`<`T`>) : `T`

åèç¹æ·»å ä¸ä¸ªæå®ç±»åçç»ä»¶ç±»ï¼ä½ è¿å¯ä»¥éè¿ä¼ å¥èæ¬çåç§°æ¥æ·»å ç»ä»¶ã

**`throws`** `TypeError` if the `classConstructor` does not specify a cc-class constructor extending the `Component`.

**`example`**

```
var sprite = node.addComponent(Sprite);
```

#### åæ°

| Name | Type | Description |
| :-: | :-: | :-: |
| `classConstructor` | `Constructor`<`T`> | The class of the component to add |

##### Returns  `T`


---
- **addComponent**(`className`: `string`) :  `Component`

åèç¹æ·»å ä¸ä¸ªæå®ç±»åçç»ä»¶ç±»ï¼ä½ è¿å¯ä»¥éè¿ä¼ å¥èæ¬çåç§°æ¥æ·»å ç»ä»¶ã

**`throws`** `TypeError` if the `className` does not specify a cc-class constructor extending the `Component`.

**`example`**

```
var test = node.addComponent("Test");
```

#### åæ°

| Name | Type | Description |
| :-: | :-: | :-: |
| `className` | `string` | The class name of the component to add |

##### Returns `Component`
