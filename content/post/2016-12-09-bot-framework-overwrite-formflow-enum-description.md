---
id: 3783
title: Bot Framework Overwrite FormFlow Enum Description
date: 2016-12-09T00:00:39+08:00
author: ShareChiWai
layout: post
guid: http://blog.sharechiwai.com/?p=3783
permalink: /2016/12/bot-framework-overwrite-formflow-enum-description/
categories:
  - Bot Framework
tags:
  - Bot Framework
  - ChatBot
  - FormFlow
  - Microsoft Bot Framework
---
最近開始研究 **Bot Framework** &#8211; **Microsoft 的 Bot Framework**  
(主要原因是.他感覺上比賽容易學.. 很快便可以做到一個簡單的**ChatBot**)  
十分有趣的是&#8230; 雖然他是Microsoft 產品.. 但是多數的Sample code/ Tutorial都是用 NodeJs寫的

如果想用C#去做相同的事比較難學習  
但是因為他的SDK 比較完善的關係..所以都值得花點時間來看看  
**C# SDK** 上有一個 叫**FormFlow** 的東西  
只需要好好的Define一個class 之後他便會自動 popular一個像dialog的flow..  
十分方便..  
<img class="alignnone size-large wp-image-3786" src="https://i0.wp.com/blog.sharechiwai.com/wp-content/uploads/2016/12/OriginalSample.png?resize=625%2C170" alt="" width="625" height="170" srcset="https://i0.wp.com/blog.sharechiwai.com/wp-content/uploads/2016/12/OriginalSample.png?w=962 962w, https://i0.wp.com/blog.sharechiwai.com/wp-content/uploads/2016/12/OriginalSample.png?resize=300%2C82 300w, https://i0.wp.com/blog.sharechiwai.com/wp-content/uploads/2016/12/OriginalSample.png?resize=768%2C209 768w, https://i0.wp.com/blog.sharechiwai.com/wp-content/uploads/2016/12/OriginalSample.png?resize=624%2C170 624w" sizes="(max-width: 625px) 100vw, 625px" data-recalc-dims="1" />  
太automate都會有一點煩惱..就是當你建主了一些option給用戶選擇時 他的default message是 &#8220;**Please select a** &#8221; 有時感覺不太性化..  
<img class="alignnone size-large wp-image-3788" src="https://i2.wp.com/blog.sharechiwai.com/wp-content/uploads/2016/12/DefaultMsg.png?resize=625%2C220" alt="Bot Framework FormFlow Default Description Message" width="625" height="220" srcset="https://i2.wp.com/blog.sharechiwai.com/wp-content/uploads/2016/12/DefaultMsg.png?resize=1024%2C361 1024w, https://i2.wp.com/blog.sharechiwai.com/wp-content/uploads/2016/12/DefaultMsg.png?resize=300%2C106 300w, https://i2.wp.com/blog.sharechiwai.com/wp-content/uploads/2016/12/DefaultMsg.png?resize=768%2C271 768w, https://i2.wp.com/blog.sharechiwai.com/wp-content/uploads/2016/12/DefaultMsg.png?resize=624%2C220 624w, https://i2.wp.com/blog.sharechiwai.com/wp-content/uploads/2016/12/DefaultMsg.png?w=1250 1250w, https://i2.wp.com/blog.sharechiwai.com/wp-content/uploads/2016/12/DefaultMsg.png?w=1875 1875w" sizes="(max-width: 625px) 100vw, 625px" data-recalc-dims="1" /> 

那裡有什麼方法可以customise 這個**default message per field** 呢?  
<img class="alignnone size-large wp-image-3787" src="https://i1.wp.com/blog.sharechiwai.com/wp-content/uploads/2016/12/DefaultMsg2.png?resize=625%2C126" alt="" width="625" height="126" srcset="https://i1.wp.com/blog.sharechiwai.com/wp-content/uploads/2016/12/DefaultMsg2.png?resize=1024%2C206 1024w, https://i1.wp.com/blog.sharechiwai.com/wp-content/uploads/2016/12/DefaultMsg2.png?resize=300%2C60 300w, https://i1.wp.com/blog.sharechiwai.com/wp-content/uploads/2016/12/DefaultMsg2.png?resize=768%2C155 768w, https://i1.wp.com/blog.sharechiwai.com/wp-content/uploads/2016/12/DefaultMsg2.png?resize=624%2C126 624w, https://i1.wp.com/blog.sharechiwai.com/wp-content/uploads/2016/12/DefaultMsg2.png?w=1250 1250w, https://i1.wp.com/blog.sharechiwai.com/wp-content/uploads/2016/12/DefaultMsg2.png?w=1875 1875w" sizes="(max-width: 625px) 100vw, 625px" data-recalc-dims="1" /> 

解決方法十分簡單.. 我們只需要在 field上加上 **Prompt** 這個**annotation**便可以了..

[<span style="color: #008000;"><strong>Prompt</strong></span>(&#8220;Your Text <span style="color: #008000;"><strong>{||}</strong></span>&#8220;)]  
<img class="alignnone size-large wp-image-3785" src="https://i1.wp.com/blog.sharechiwai.com/wp-content/uploads/2016/12/UpdatedClass.png?resize=625%2C172" alt="" width="625" height="172" srcset="https://i1.wp.com/blog.sharechiwai.com/wp-content/uploads/2016/12/UpdatedClass.png?w=996 996w, https://i1.wp.com/blog.sharechiwai.com/wp-content/uploads/2016/12/UpdatedClass.png?resize=300%2C83 300w, https://i1.wp.com/blog.sharechiwai.com/wp-content/uploads/2016/12/UpdatedClass.png?resize=768%2C211 768w, https://i1.wp.com/blog.sharechiwai.com/wp-content/uploads/2016/12/UpdatedClass.png?resize=624%2C172 624w" sizes="(max-width: 625px) 100vw, 625px" data-recalc-dims="1" />  
E.G.

<pre>public class SandwichOrder
    {
        [Prompt("What sandwich would you like? {||}")]
        public SandwichOptions? Sandwich;
        public LengthOptions? Length;
  }
</pre>

<img class="alignnone size-large wp-image-3784" src="https://i0.wp.com/blog.sharechiwai.com/wp-content/uploads/2016/12/UpdatedResult.png?resize=625%2C161" alt="" width="625" height="161" srcset="https://i0.wp.com/blog.sharechiwai.com/wp-content/uploads/2016/12/UpdatedResult.png?resize=1024%2C263 1024w, https://i0.wp.com/blog.sharechiwai.com/wp-content/uploads/2016/12/UpdatedResult.png?resize=300%2C77 300w, https://i0.wp.com/blog.sharechiwai.com/wp-content/uploads/2016/12/UpdatedResult.png?resize=768%2C198 768w, https://i0.wp.com/blog.sharechiwai.com/wp-content/uploads/2016/12/UpdatedResult.png?resize=624%2C161 624w, https://i0.wp.com/blog.sharechiwai.com/wp-content/uploads/2016/12/UpdatedResult.png?w=1250 1250w" sizes="(max-width: 625px) 100vw, 625px" data-recalc-dims="1" />  
hope you find it useful

記住要在annotation的尾段要加上 &#8220;{||}&#8221; 不然..這個enum的選項便不會出現了