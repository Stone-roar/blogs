[ï¼1ãðè¿åä¸ä¸çº§ï¼](ç®å½_Event.md "eventæ¨¡å")
[ï¼2ãè½¬å° SystemEvent.EventTypeï¼](Event_Class_SystemEvent.md#EventType_index "ç¹å»æ¥ç âç³»ç»äºä»¶âäºä»¶ç±»åâ")
# æä¸¾: SystemEvent.EventType

> å¨å±ç³»ç»äºä»¶

## ç®å½
* [`DEVICEMOTION` **éåæåº**](#DEVICEMOTION)
* **è§¦æ¸äºä»¶**
  * [`TOUCH_START` è§¦æ¸å¼å§](#TOUCH_START)
  * [`TOUCH_MOVE` è§¦æ¸ç§»å¨](#TOUCH_MOVE)
  * [`TOUCH_END` è§¦æ¸ç»æ](#TOUCH_END)
  * [`TOUCH_CANCEL` åæ¶è§¦æ¸](#1TOUCH_CANCEL)
* **é¼ æ äºä»¶**
  * [`MOUSE_DOWN` é¼ æ æä¸](#MOUSE_DOWN)
  * [`MOUSE_MOVE` é¼ æ ç§»å¨ï¼æä¸ç¶æï¼](#MOUSE_MOVE)
  * [`MOUSE_UP` é¼ æ æ¾å¼](#MOUSE_UP)
  * [`MOUSE_WHEEL` æ»è½®](#MOUSE_WHEEL)
* **é®çäºä»¶**
  * [`KEY_DOWN` æä¸æé®](#KEY_DOWN)
  * [`KEY_UP` æ¾å¼æé®](#KEY_UP)
---
## éåæåº
### DEVICEMOTION

éåæåº

- **DEVICEMOTION** = `"devicemotion"`

---
## è§¦æ¸äºä»¶ {4}
[ï¼ðåå°é¡¶é¨ï¼](#ç®å½)
### TOUCH_START
> ææå¼å§è§¦æ¸äºä»¶ã
- TOUCH_START = `"touch-start"`

---
### TOUCH_MOVE
> å½ææå¨å±å¹ä¸ç§»å¨æ¶ã

- TOUCH_MOVE = `"touch-move"`

---
### TOUCH_END
> ææç»æè§¦æ¸äºä»¶ã

- TOUCH_END = `"touch-end"`

---
### TOUCH_CANCEL
> å½ææå¨ç®æ èç¹åºåå¤ç¦»å¼å±å¹æ¶ã

- TOUCH_CANCEL = `"touch-cancel"`

---
## é¼ æ äºä»¶ {4}
[ï¼ðåå°é¡¶é¨ï¼](#ç®å½)
### MOUSE_DOWN
> å½é¼ æ æä¸æ¶è§¦åä¸æ¬¡ã

- MOUSE_DOWN = `"mouse-down"`

---
### MOUSE_MOVE
> å½é¼ æ å¨ç®æ èç¹å¨ç®æ èç¹åºåä¸­ç§»å¨æ¶ï¼ä¸è®ºæ¯å¦æä¸ã

- MOUSE_MOVE = `"mouse-move"`

---
### MOUSE_UP
> å½é¼ æ ä»æä¸ç¶ææ¾å¼æ¶è§¦åä¸æ¬¡ã

- MOUSE_UP = `"mouse-up"`

---
### MOUSE_WHEEL
> å½é¼ æ æ»è½®æ»å¨æ¶ã

- MOUSE_WHEEL = `"mouse-wheel"`

---
## é®çäºä»¶ {2}
[ï¼ðåå°é¡¶é¨ï¼](#ç®å½)
### KEY_DOWN

> å½æä¸æé®æ¶è§¦åçäºä»¶, è¯¥äºä»¶å¨æä¸ç¶æä¼æç»­æ´¾å

- **KEY_DOWN** = `"keydown"`

---

### KEY_UP

> å½æ¾å¼æé®æ¶è§¦åçäºä»¶

- **KEY_UP** = `"keyup"`
