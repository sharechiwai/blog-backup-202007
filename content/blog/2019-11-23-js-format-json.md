---
title: "JS format JSON"
date: 2019-11-23T00:00:00+08:00
author: ShareChiWai
layout: post
categories:
  - Javascript
tags:
  - JSON
  - Javascript
---

如何用 `Javascript` format `JSON`  
**解決方法:**  
我們可以使用`JSON.stringify` 來 format  
**e.g.**

```javascript
var c = {a : "test", b:{ data: "asdada"}}

JSON.stringify(c, null, 4)
"{
    "a": "test",
    "b": {
        "data": "asdada"
    }
}"
```

Hope you find it useful


https://love2dev.com/blog/css-text-transform/#:~:targetText=The%20CSS%20text%2Dtransform%20Property,-The%20CSS%20text&targetText=lowercase%3A%20makes%20all%20of%20the,word%20in%20the%20selected%20text.