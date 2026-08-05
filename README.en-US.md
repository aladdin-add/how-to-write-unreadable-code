

<!-- TOC -->

- [A Step-by-Step Guide to Writing Unreadable Code (WIP) #](#1-手把手教你写出不可读的代码(WIP)#)
  - [Indentation](#11-缩进)
  - [Variables](#12-变量)
  - [Comments](#13-注释)
  - [Tests](#14-测试)

<!-- /TOC -->



<a id="toc_anchor" name="#1-手把手教你写出不可读的代码(WIP)#"></a>

# 1. A Step-by-Step Guide to Writing Unreadable Code (WIP) #
> The programming industry has a very high turnover rate. If everyone can understand the code you write, your replaceability will be extremely high, which is undoubtedly a major career drawback. This article provides some practical tips to guide you step-by-step in writing unreadable code (without using obfuscation), which can effectively boost your workplace competitiveness.

> 💚 Sharing is a virtue. If you find this helpful, please share it with your friends & colleagues. Good ideas are welcome via issues & PRs.



<a id="toc_anchor" name="#11-缩进"></a>

## 1.1. Indentation
+ **Irregular indentation is the most important.** For example, let's write a simple function to compare two version numbers:
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
This code has many problems. First, the indentation is too monotonous and fails to show any personality. Let's tweak it slightly:

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

## 1.2. Variables
+ **Variable naming should have some randomness, with a mix of long and short names.**
+ **Try to use global variables as much as possible.**
```js
function fxd(asdkg, sdgoie){
    // ...
    ghpeks = Math.max(jsklfwoer, oto349kd);
}
```

<a id="toc_anchor" name="#13-注释"></a>

## 1.3. Comments
Many people have already developed the bad habit of writing comments, which might be hard to break at first. **Actually, compared to not writing comments at all, writing misleading comments yields even better results.**
```js
// Returns the larger number between va and vb.
function compareVersion (va, vb){
    // ...
}
```

<a id="toc_anchor" name="#14-测试"></a>

## 1.4. Tests
Once tests are in place, others will know exactly what your code does. This way, they can reimplement the functionality without even needing to understand your code.

**Therefore, under no circumstances should you write tests.**
