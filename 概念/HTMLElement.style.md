# HTMLElement.style

**`style`**只读属性以对象的形式返回元素的内联样式，该[`CSSStyleDeclaration`](https://developer.mozilla.org/en-US/docs/Web/API/CSSStyleDeclaration)对象包含该元素的所有样式属性的列表，并为元素的内联[`style`属性](https://developer.mozilla.org/en-US/docs/Web/HTML/Global_attributes/style)中定义的属性分配了值。

## [设置样式](https://developer.mozilla.org/en-US/docs/Web/API/HTMLElement/style#setting_styles)

虽然此属性被认为是只读的，但可以通过将字符串直接分配给该`style`属性来设置内联样式。在这种情况下，字符串被转发到[`CSSStyleDeclaration.cssText`](https://developer.mozilla.org/en-US/docs/Web/API/CSSStyleDeclaration/cssText). 以`style`这种方式使用将完全覆盖元素上的所有内联样式。

因此，要在不更改其他样式值的情况下向元素添加特定样式，通常最好在[`CSSStyleDeclaration`](https://developer.mozilla.org/en-US/docs/Web/API/CSSStyleDeclaration)对象上设置单独的属性。例如，`element.style.backgroundColor = "red"`。

样式声明通过将其设置为`null`或空字符串来重置，例如`elt.style.color = null`.

## 自己的理解

通过JS获取html元素，每个元素的style只读属性会返回一个CSSStyleDeclaration对象，该对象包含该元素的所有样式属性的列表。

```js
{
    // 动画属性
    "animation": "",
    "animationDelay": "",
    "animationDirection": "",
    "animationDuration": "",
    "animationFillMode": "",
    "animationIterationCount": "",
    "animationName": "",
    "animationPlayState": "",
    "animationTimingFunction": "",
    // 背景相关
    "background": "",
    "backgroundClip": "",
    "backgroundColor": "red",
    "backgroundImage": "",
    "backgroundOrigin": "",
    "backgroundPosition": "",
    "backgroundPositionX": "",
    "backgroundPositionY": "",
    "backgroundRepeat": "",
    "backgroundRepeatX": "",
    "backgroundRepeatY": "",
    "backgroundSize": "",
    // 其他常用属性
    "border": "",
    "borderBlock": "",
    "borderColor": "",
    "borderImage": "",
    "borderRadius": "",
    "borderSpacing": "",
    "borderStyle": "",
    "borderWidth": "",
        
    "boxShadow": "",
    "boxSizing": "",

    "color": "",
    
    "content": "",
   
    "display": "",
  
    "flex": "",
    "flexBasis": "",
    "flexDirection": "",
    "flexFlow": "",
    "flexGrow": "",
    "flexShrink": "",
    "flexWrap": "",
        
    "float": "",
   
    "font": "",
    "fontFamily": "",
    "fontSize": "",
    "fontStyle": "",
    "fontWeight": "",
   
    "height": "",
 
    "justifyContent": "",
    "justifyItems": "",
    "justifySelf": "",
   
    "listStyle": "",
    "listStyleImage": "",
    "listStylePosition": "",
    "listStyleType": "",
        
    "margin": "",
    "marginBottom": "",
    "marginLeft": "",
    "marginRight": "",
    "marginTop": "",
   
    "maxHeight": "",
    "maxWidth": "",
    "minHeight": "",
    "minWidth": "",
 
    "opacity": "",
  
    "padding": "",
    "paddingBottom": "",
    "paddingLeft": "",
    "paddingRight": "",
    "paddingTop": "",
    
    "textAlign": "",
    "textShadow": "",
  
    "transform": "",
    "transformOrigin": "",
    "transformStyle": "",
    "transition": "",
    "transitionDelay": "",
    "transitionDuration": "",
    "transitionProperty": "",
    "transitionTimingFunction": "",
        
    "visibility": "",
    
    "width": "",
    "zIndex": "",
    "zoom": ""
}
```

通过将对应的样式属性直接赋值给style属性的方式可以设置内联样式，而且通过这种方式设置的内联样式的优先级最高。