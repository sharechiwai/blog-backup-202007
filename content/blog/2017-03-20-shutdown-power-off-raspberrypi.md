---
id: 3927
title: 'Shutdown / power off RaspberryPi - RaspberryPi 如何安全關機?'
date: 2017-03-20T00:00:52+08:00
author: ShareChiWai
layout: post
categories:
  - RaspberryPi
tags:
  - RaspberryPi
  - RaspberryPi Troubleshooting
---

最近常常使用**RaspberryPi**
由于是用**SSH** 去連接"
通常都是**unplug power cable**來關機
所以不知道怎樣正確地關機

做了一會 research 後發現 解決方法十分簡單

**解決方法**

我們可以使用 **linux** 的關機 <span style="color: #008000;"><strong>shutdown</strong></span> command 來關機
<span style="color: #008000;"><strong>-h</strong> </span>是馬上關機
e.g.

```
sudo shutdown -h
```

之前我的做法是使用其他電腦去**Ping** 這個**RaspberryPi**
當他 **timeout**時便應該是已經關機了

其實當**RaspberryPi** 的燈關沒有再閃
或 如果你是使用**Powerbank** 時
**Raspberry Pi**的燈關掉了
便證明你的**RaspberryPi 安全關機**

Hope you find it useful
