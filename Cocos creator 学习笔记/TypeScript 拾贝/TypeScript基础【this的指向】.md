```typescript
function a() {
    var user = "追梦子";
    console.log(this.user); //undefined
    console.log(this); //Window
}
a();
```
