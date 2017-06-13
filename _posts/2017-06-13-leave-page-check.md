---
bg: "tools.jpg"
layout: post
title:  "页面退出检测"
crawlertitle: "About ES6"
summary: "What's new in ES6"
date:   2017-06-13 23:14:47 +0700
categories: posts
tags: ['front-end']
author: NowhereToRun
---
前段时间由于需要检测文章的阅读率，为了精确统计想要在退出之前发出请求，于是对一些方法进行了尝试。

网上主要说的有两种方法`onunload` 和 `onbeforeunload`，在移动端测试了几个浏览器，兼容性如下：

<table>
<tbody>
    <tr>
        <th style="width: 80px;">浏览器</th>
        <th style="width: 100px;">方法</th>
        <th style="width: 50px;">onunload</th>
        <th style="width: 50px;">onbeforeunload</th>
    </tr>
    <tr>
        <td rowspan="3"><font>UC</font></td>
        <td>刷新</td>
        <td bgcolor="ForestGreen"></td>
        <td bgcolor="ForestGreen"></td>
    </tr>
    <tr>
        <td>关闭</td>
        <td bgcolor="ForestGreen"></td>
        <td bgcolor="ForestGreen"></td>
    </tr>
    <tr>
        <td>回退</td>
        <td bgcolor="ForestGreen"></td>
        <td bgcolor="ForestGreen"></td>
    </tr>
    <tr>
        <td rowspan="3"><font>Chrome</font></td>
        <td>刷新</td>
        <td bgcolor="ForestGreen"></td>
        <td bgcolor="ForestGreen"></td>
    </tr>
    <tr>
        <td>关闭</td>
        <td bgcolor="ForestGreen"></td>
        <td bgcolor="ForestGreen"></td>
    </tr>
    <tr>
        <td>回退</td>
        <td bgcolor="ForestGreen"></td>
        <td bgcolor="ForestGreen"></td>
    </tr>
    <tr>
        <td rowspan="3"><font>Chrome PC</font></td>
        <td>刷新</td>
        <td bgcolor="ForestGreen"></td>
        <td bgcolor="ForestGreen"></td>
    </tr>
    <tr>
        <td>关闭</td>
        <td bgcolor="ForestGreen"></td>
        <td bgcolor="ForestGreen"></td>
    </tr>
    <tr>
        <td>回退</td>
        <td bgcolor="ForestGreen"></td>
        <td bgcolor="ForestGreen"></td>
    </tr>
        <tr>
        <td rowspan="3"><font>华为原生 安卓6.0</font></td>
        <td>刷新</td>
        <td bgcolor="ForestGreen"></td>
        <td bgcolor="ForestGreen"></td>
    </tr>
    <tr>
        <td>关闭</td>
        <td bgcolor="ForestGreen"></td>
        <td bgcolor="ForestGreen"></td>
    </tr>
    <tr>
        <td>回退</td>
        <td bgcolor="ForestGreen"></td>
        <td bgcolor="ForestGreen"></td>
    </tr>
</tbody>
</table>
If you are still looking for confidence with JavaScript, I highly recommend you read the other titles in this series first:

Up & Going: Are you new to programming and JS? This is the roadmap you need to consult as you start your learning journey.

- Up & Going
- Scope & Closures
- this & Object Prototypes
- Types & Grammar
- Async & Performance

[![railroad]({{ site.images }}/rails.jpg)]({{ site.images }}/rails.jpg)

If you've already read all those titles and you feel pretty comfortable with the topics they cover, it's time we dive into the evolution of JS to explore all the changes coming not only soon but farther over the horizon.

## `let` Declarations

However, we can now create declarations that are bound to any block, called (unsurprisingly) *block scoping*. This means all we need is a pair of `{ .. }` to create a scope. Instead of using var, which always declares variables attached to the enclosing function (or global, if top level) scope, use `let`:

{% highlight js %}
var a = 2;

{
    let a = 3;
    console.log( a );   // 3
}

console.log( a );       // 2
{% endhighlight %}
