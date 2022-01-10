## SystemEventMap
```typescript
interface SystemEventMap {
        [SystemEvent.EventType.MOUSE_DOWN]: (event: EventMouse) => void;
        [SystemEvent.EventType.MOUSE_MOVE]: (event: EventMouse) => void;
        [SystemEvent.EventType.MOUSE_UP]: (event: EventMouse) => void;
        [SystemEvent.EventType.MOUSE_WHEEL]: (event: EventMouse) => void;
        [SystemEvent.EventType.TOUCH_START]: (touch: Touch, event: EventTouch) => void;
        [SystemEvent.EventType.TOUCH_MOVE]: (touch: Touch, event: EventTouch) => void;
        [SystemEvent.EventType.TOUCH_END]: (touch: Touch, event: EventTouch) => void;
        [SystemEvent.EventType.TOUCH_CANCEL]: (touch: Touch, event: EventTouch) => void;
        [SystemEvent.EventType.KEY_DOWN]: (event: EventKeyboard) => void;
        [SystemEvent.EventType.KEY_UP]: (event: EventKeyboard) => void;
        [SystemEvent.EventType.DEVICEMOTION]: (event: EventAcceleration) => void;
    }
```
