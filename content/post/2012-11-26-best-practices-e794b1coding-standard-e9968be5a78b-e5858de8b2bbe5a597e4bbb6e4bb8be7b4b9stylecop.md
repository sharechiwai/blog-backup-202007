---
id: 2614
title: Best Practices 由Coding Standard 開始 免費套件介紹StyleCop
date: 2012-11-26T00:00:35+08:00
author: ShareChiWai
layout: post
guid: http://blog.sharechiwai.com/?p=2614
permalink: '/2012/11/best-practices-%e7%94%b1coding-standard-%e9%96%8b%e5%a7%8b-%e5%85%8d%e8%b2%bb%e5%a5%97%e4%bb%b6%e4%bb%8b%e7%b4%b9stylecop/'
categories:
  - StyleCop
tags:
  - StyleCop
---
早前上了一個有關**SQL**的Talk上聽了一個很有道理的理論..  
怎樣可以增加自己的工作效能/Efficienct呢?

能夠很快捷地寫完一個程式?  
[這可能只有一些自己感到舒服的Coding方法[除心所欲]&#8230;  
E.G. 沒有Code寫上Comment或好好的Indent好  
或者沒有一個**Coding Standard**的做法]

其實這種寫Code 的模式雖然可以很快地把程式或功能完成  
但是長遠來看..這會增力寫程式維護/和寫更多功能時的時間  
以下是一些原因[如果大家大更多的原因&#8230;歡迎留言和大家分享]  
&#8211; 使程式碼更容易閱讀 E.G. 如果好好的把程式碼分開格式化/Format Code 這可以增加程式碼的可讀性

  * <span style="line-height: 1.714285714; font-size: 1rem;">增加程式的效能</span>
  * <span style="line-height: 1.714285714; font-size: 1rem;">令到其他Teammate可以更容易學習到你的程式碼&#8230;當Teammate要接手Enhance你的程式碼時..由於大家都是以同一個<strong>Coding Standard</strong>來寫程式的關係..所以便很容易可以明白了</span>

**StyleCop** 是一**個Visual Studio**的 **Extension**  
他可以幫你檢查你的程式碼..看看他們合乎不合乎他們的**Coding Standard**  
當然有些Rule我們是可以在**StyleCop**的設定上開啟或關閉的  
所以大家可以以自己各得的重要性來選擇那一些可以不使用&#8230;Etc

StyleCop的另一個有用的地方就是可以Integrate 到 TFS &#8211; Build Service上.  
當大家把完成了的程式碼Check-In到**TFS** 上時&#8230;TFS 可以執行**StyleCop**去確定  
你的程式碼以合乎要求才可以Check-In  
和即使Check-In了 當**TFS Build Service** 發現有些Code不合乎要求也會 Fail to Build

有興趣的朋友可以到以下網址找到更多有關StyleCop 的資訊

有時間我會更新更多有關StyleCop的文章

[http://stylecop.codeplex.com/](http://stylecop.codeplex.com/ "StyleCop")

Hope you find it useful