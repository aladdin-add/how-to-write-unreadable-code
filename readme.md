<!-- TOC -->

- [手把手教你写出不可读的代码(WIP) #](#1-手把手教你写出不可读的代码(WIP)#)
  - [缩进](#11-缩进)
  - [变量](#12-变量)
  - [注释](#13-注释)
  - [测试](#14-测试)

<!-- /TOC -->



<a id="toc_anchor" name="#1-手把手教你写出不可读的代码(WIP)#"></a>

# 1. 手把手教你写出不可读的代码(WIP) #
> 程序员这个行业的流动性非常高，如果你写的代码每个人都能看懂，那么可替代性就会非常高，这无疑是一个很大的职业缺点。本文给出一些实用的建议，手把手教你写出不可读的代码（在不使用混淆的情况下），可有效提高你的职场竞争力。

> 💚分享是一种美德，如果你觉得有帮助，请把它分享给你的朋友&同事。有好的想法，欢迎 issue & PR。



<a id="toc_anchor" name="#11-缩进"></a>

## 1.1. 缩进
+ **无规律的缩进是最重要的。** 举例来说，我们来写一个简单的函数，比较2个版本号：
```js
// func def.
// va < vb => -1
// va > vb => 1
// va = vb => 0
function compareVersion(va, vb) {
    va = va.split('.');
    vb = vb.split('.');
    var len = Math.max(va.length, vb.length);

    for (var i = 0; i < len; i++) {
        if (va[i] !== vb[i]) {
            return va[i] < vb[i] ? -1 : 1;
        }
    }
    return 0;
}

// test
compareVersion('0.0.0', '0.0.1'); // -1
compareVersion('1.0.0', '2.0.1'); // -1
compareVersion('0.0.1', '0.0.0'); // 1
compareVersion('2.0.1', '1.0.0'); // 1
compareVersion('0.0.0', '0.0.0'); // 0

```
这段代码有很多问题，首先就是缩进，太单调了，一点也不能彰显个性，我们稍微改一下：

```js
        function compareVersion(va, vb) {va = va.split('.');
      vb = vb.split('.');
 len = Math.max(va.length, vb.length);
          for (var i = 0; i < len; i++) {
  if (va[i] !== vb[i]) {
     return va[i] < vb[i] ? -1 : 1;
 }}return 0;}
```

<a id="toc_anchor" name="#12-变量"></a>

## 1.2. 变量
+ **变量命名应该带有某种随机性，长短错落有致。**
+ **尽量使用全局变量**
```js
function fxd(asdkg, sdgoie){
    // ...
    ghpeks = Math.max(jsklfwoer, oto349kd);
}
```

<a id="toc_anchor" name="#13-注释"></a>

## 1.3. 注释
很多人已经养成了写注释的坏习惯，一时可能难以改掉。**其实比起不写注释，写一些有误导性的注释效果更佳。**
```js
// 返回va, vb 中最大的数。
function compareVersion (va, vb){
    // ...
}
```

<a id="toc_anchor" name="#14-测试"></a>

## 1.4. 测试
一旦有了测试，别人就知道了你的代码的功能。这样，在不用读懂你的代码的情况下，就能够重新实现该功能。

**所以，千万千万不要写测试。**
