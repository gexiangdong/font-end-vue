# 插槽


有些组件需要在组件内预留空间给父元素填充。例如对话框，非常常用、通用，但是对话框内的内容，每个不同，对话框内的内容从简单的字符串显示到复杂的HTML界面、表单等等什么情况都可能有。因此需要把内容部分留给父级元素指定。这就需要用到slot功能，翻译过来是插槽。

## 单一插槽

组件内定义插槽

```
<template>
  <div>
     <!-- 只要把下面这行放在模版里预留位置处就好了 -->
     <slot></slot>
  </div>
</template>
```
如果在<slot></slot>之间写了内容，会作为该插槽的默认内容，当调用方不指定内容时，显示默认内容，指定内容时，这些内容会被替换成调用方指定的内容。


在父级调用组件的时候

```
<MyComponent>
  <!--这里直接写在组件标签内的东西都会进入到上面定义的插槽内显示 -->
  <p>hello, slot</p>
</MyComponet>
```

## 多插槽

上面的例子是一个插槽的例子，有的时候需要定义多个插槽，最常见需求的就是做多个tab可切换的那种控件，每个面板内容都需要在父元素指定。

这是时候需要在组件里为每个插槽指定一个名字，最多可以有一个没名字的默认插槽。

```
<div>
  <slot name="header"></slot>
  <hr>
  <slot></slot>
  <hr>
  <slot name="footer"></slot>
</div>
```
上面的例子就是定义了三个插槽，其中两个有名字，一个没名字的默认插槽。在调用方就需要这么调用：

```
<MyComponent>
  <!--可以是任意元素标签，不必须是div，只要增加属性slot指明把内容放到哪个插槽即可 -->
  <div slot="header">This is Title</div>
  <div slot="footer">Footer here </div>
  <div>
    hello, world.
  </div>
</MyComponent>
```

没写slot属性的元素加入到默认插槽中。

