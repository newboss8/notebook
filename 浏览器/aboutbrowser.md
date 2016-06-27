浏览器兼容问题


IE可以设置浏览模式
<meta http-equiv="X-UA-Compatible" content="IE=EmulateIE7" />
<meta http-equiv="X-UA-Compatible" content="IE=8" />

360安全浏览器：
<meta name="renderer" content="webkit|ie-comp|ie-stand">
content的取值为webkit，ie-comp，ie-stand之一，区分大小写，分别代表用极速模式，兼容模式，IE模式打开。

目前国内双核浏览器的默认内核模式情况如下：
搜狗高速浏览器：默认使用IE内核（兼容模式）
360极速浏览器：默认使用Chromium内核（极速模式）
傲游浏览器：默认使用Webkit内核（极速模式）
QQ浏览器：默认使用IE内核（兼容模式）


<meta name=”renderer” content=”webkit”>
<meta http-equiv=”X-UA-Compatible” content=”IE=edge,chrome=1” />




<meta http-equiv=X-UA-Compatible content="IE=edge,chrome=1">
<meta content=always name=referrer>
