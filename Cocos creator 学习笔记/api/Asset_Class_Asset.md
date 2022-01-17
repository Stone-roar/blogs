[（🔙返回上一级）](目录_Asset.md "asset模块")
# 类: Asset

`extend: `  [IEventified](Event_Interface_IEventified.md "事件处理的接口")

Creator 中的资源基类。

您可能需要重写：

* createNode
* _nativeAsset 的 getset 方法
* `Object._serialize`
* `Object._deserialize`

## 目录

### 属性
* [[editorExtrasTag]](#[editorExtrasTag])
* [isDefault](#isDefault)
* [loaded](#loaded)
* [hideFlags](#hideFlags)
* [isValid](#isValid)
* [name](#name)
* [nativeUrl](#nativeUrl)
* [refCount](#refCount)
* [replicated](#replicated)

### 构造函数

* [constructor](#constructor)

### 方法
* [**`static`** deserialize](#deserialize)
* [addRef](#addRef)
* [createNode](#createNode)
* [decRef](#decRef)
* [destroy](#destroy)
* [emit](#emit)
* [equals](#equals)
* [hasEventListener](#hasEventListener)
* [initDefault](#initDefault)
* [off](#off)
* [on](#on)
* [onLoaded](#onLoaded)
* [once](#once)
* [removeAll](#removeAll)
* [targetOff](#targetOff)
* [toString](#toString)
* [validate](#validate)
