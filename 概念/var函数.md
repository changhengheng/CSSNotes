# HTMLElement.style

**`style`**只读属性以对象的形式返回元素的内联样式，该[`CSSStyleDeclaration`](https://developer.mozilla.org/en-US/docs/Web/API/CSSStyleDeclaration)对象包含该元素的所有样式属性的列表，并为元素的内联[`style`属性](https://developer.mozilla.org/en-US/docs/Web/HTML/Global_attributes/style)中定义的属性分配了值。

## [设置样式](https://developer.mozilla.org/en-US/docs/Web/API/HTMLElement/style#setting_styles)

虽然此属性被认为是只读的，但可以通过将字符串直接分配给该`style`属性来设置内联样式。在这种情况下，字符串被转发到[`CSSStyleDeclaration.cssText`](https://developer.mozilla.org/en-US/docs/Web/API/CSSStyleDeclaration/cssText). 以`style`这种方式使用将完全覆盖元素上的所有内联样式。