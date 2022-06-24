# <link>：外部资源链接元素

## [Try it](https://developer.mozilla.org/zh-CN/docs/Web/HTML/Element/link#try_it)

**HTML 外部资源链接元素** (**`<link>`**) 规定了当前文档与外部资源的关系。该元素最常用于链接[样式表](https://developer.mozilla.org/zh-CN/docs/Glossary/CSS)，此外也可以被用来创建站点图标 (比如 PC 端的 “favicon” 图标和移动设备上用以显示在主屏幕的图标) 。

要链接一个外部的样式表，你需要像这样在你的[``](https://developer.mozilla.org/zh-CN/docs/Web/HTML/Element/head)中包含一个[``](https://developer.mozilla.org/zh-CN/docs/Web/HTML/Element/link)元素：

```
<link href="main.css" rel="stylesheet">
```

Copy to Clipboard

在这个简单的例子中，使用了 `href` 属性设置外部资源的路径，并设置 `rel` 属性的值为 “`stylesheet`”(样式表)。`rel` 表示 “关系 (relationship) ”，它可能是`<link>`元素其中一个关键的特性——属性值表示`<link>`项的链接方式与包含它的文档之间的关系。你将在我们的[链接类型](https://developer.mozilla.org/en-US/docs/Web/HTML/Link_types)中看到很多不同类型的关系。

这里有一些你经常遇到的其它类型。例如，这里是一个网站图标的链接：

```
<link rel="icon" href="favicon.ico">
```

Copy to Clipboard

还有一些其它的与图标相关的`rel`值，主要用于表示不同移动平台上特殊的图标类型，例如：

```
<link rel="apple-touch-icon-precomposed" sizes="114x114"
      href="apple-icon-114.png" type="image/png">
```

Copy to Clipboard

`sizes`属性表示图标大小，`type`属性包含了链接资源的 MIME 类型。这些属性为浏览器选择最合适的图标提供了有用的提示。

你也可以提供一个媒体类型，或者在`media`属性内部进行查询；这种资源将只在满足媒体条件的情况下才被加载进来。例如：

```
<link href="print.css" rel="stylesheet" media="print">
<link href="mobile.css" rel="stylesheet" media="screen and (max-width: 600px)">
```

Copy to Clipboard

其它用法的注解：

- `<link>`元素可以出现在[`<head>`](https://developer.mozilla.org/zh-CN/docs/Web/HTML/Element/head)元素或者[`<body>`](https://developer.mozilla.org/zh-CN/docs/Web/HTML/Element/body)元素中，具体取决于它是否有一个**body-ok**的[链接类型](https://html.spec.whatwg.org/multipage/links.html#body-ok)。例如，`stylesheet`链接类型是 body-ok 的，因此`<link rel="stylesheet">`允许出现在 body 中。然而，这不是一种好的可遵循的实践方式；更合理的方式是，将你的`<link>`元素从你的 body 内容中分离出来，将其放在`<head>`中。
- 当使用`<link>`为网站创建一个 favicon 时，你的网站使用内容安全策略 (Content Security Policy，CSP) 来增强它的安全性，这种策略适用于 favicon。如果你遇到 favicon 未加载的问题，验证[`Content-Security-Policy`](https://developer.mozilla.org/zh-CN/docs/Web/HTTP/Headers/Content-Security-Policy)头的[`img-src` directive](https://developer.mozilla.org/en-US/docs/Web/HTTP/Headers/Content-Security-Policy/img-src)没有在阻止对它的访问。
- HTML 和 XHTML 规范为`<link>`元素定义了一些事件处理器 (*event handler*) ，但是对于它们的使用方法不明确。
- 在 XHTML 1.0 下，例如`<link>`的空元素需要一个尾斜杠：`<link />`。
- WebTV 支持`rel`使用`next`值，用于在一个 document series 中预加载下一页。