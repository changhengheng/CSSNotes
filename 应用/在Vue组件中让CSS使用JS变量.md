##### 第一步：html部分   标签绑定动态style

```xml
<div :style="{
            '--setColor': setColor,
            '--setBackground': setBackground
          }"
>
</div>
```

##### 第二步： script部分    data设置变量

```kotlin
data(){
    return{
      setColor: "#fff",
      setBackground: "#eee"
  }
}
```

##### 第三步： style部分    通过var函数引用data变量

```css
div{
    color: var(--setColor),
    background: var(--setBackground)
}
```