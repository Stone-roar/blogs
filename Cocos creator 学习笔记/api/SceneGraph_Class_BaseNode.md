[ï¼ðè¿åä¸ä¸çº§ï¼](ç®å½_SceneGraph.md "scene-graphæ¨¡å")
# ç±»: BaseNode
[Node](SceneGraph_Class_Node.md "Nodeç±»") çåºç±»ï¼ä»ä¼è´è´£ï¼

- ç»´æ¤åºæ¯æ ä»¥åèç¹çå½å¨æç®¡ç
- æä¾ EventTarget çäºä»¶ç®¡çåæ³¨åè½å
- æ´¾åèç¹ç¶æç¸å³çäºä»¶ï¼åèï¼[Node.EventType](SceneGraph_Class_Node.md#EventType_index "ç¹å»æ¥ç âèç¹âäºä»¶ç±»åâ")
- ç®¡çç»ä»¶

## ç®å½
### å±æ§
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
* å class CCObject
  * [`isValid` è¯¥å¯¹è±¡æ¯å¦å¯ç¨](#isValid)
  * [`hideFlags`](#hideFlags)
  * [`replicated`](#replicated)

### æä¸¾
* `static` Flags

### æé å½æ°
* constructor

### æ¹æ³
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






------
## å±æ§
### name
> è¯¥èç¹åç§°ã

- name: `string`

### uuid
> ä¸»è¦ç¨äºç¼è¾å¨ç uuidï¼å¨ç¼è¾å¨ä¸å¯ç¨äºæä¹åå­å¨ï¼å¨é¡¹ç®æå»ºä¹åå°åæèªå¢ç idã

- uuid: `string`

------
### active
> å½åèç¹çèªèº«æ¿æ´»ç¶æã

å¼å¾æ³¨æçæ¯ï¼ä¸ä¸ªèç¹çç¶èç¹å¦æä¸è¢«æ¿æ´»ï¼é£ä¹å³ä½¿å®èªèº«è®¾ä¸ºæ¿æ´»ï¼å®ä»ç¶æ æ³æ¿æ´»ã å¦æä½ æ³æ£æ¥èç¹å¨åºæ¯ä¸­å®éçæ¿æ´»ç¶æå¯ä»¥ä½¿ç¨ `activeInHierarchy`ã

é»è®¤å¼ï¼`true`

- active: boolean

### activeInHierarchy
> è¡¨ç¤ºæ­¤èç¹æ¯å¦å¨åºæ¯ä¸­æ¿æ´»ã

- activeInHierarchy: `boolean`

### eventProcessor
> å½åèç¹çäºä»¶å¤çå¨ï¼æä¾ EventTarget è½åã

- eventProcessor: `any`

------
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
