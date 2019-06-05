---
id: 940
title: 'VB.Net Object Initializer &#8212;VB.Net在建立Object 的同時初始化這Object 的屬性'
date: 2010-11-13T00:00:42+08:00
author: ShareChiWai
layout: post
guid: http://oldblog.sharechiwai.com/?p=940
permalink: '/2010/11/vb-net-object-initializer-vb-net%e5%9c%a8%e5%bb%ba%e7%ab%8bobject-%e7%9a%84%e5%90%8c%e6%99%82%e5%88%9d%e5%a7%8b%e5%8c%96%e9%80%99object-%e7%9a%84%e5%b1%ac%e6%80%a7/'
categories:
  - .Net Tips And Tricks
---
<div id="_mcePaste">
  我有時候很喜歡用C#的
</div>

<div>
  可能是在網上有很多資源都是用C#寫的<br /> 其中一個我喜歡C Sharp 的原因是 在C#建立Object 的同時也可以初始化這Object 的屬性
</div>

<div>
  <p>
    E.G.
  </p>
  
  <p>
    [csharp]<br /> ShareChiWaiClass ShareChiWaiObj = new ShareChiWaiClass(){Blog_Author = "ShareChiWai",<br /> Blog_Content = "My content",<br /> Blog_ID = 1,<br /> Blog_Title = "Object Initializer Example"<br /> }<br /> [/csharp]
  </p>
  
  <p>
    VB.Net 卻要這樣寫
  </p>
  
  <p>
    [vb]<br /> Dim ShareChiWaiObj As New ShareChiWaiClass<br /> ShareChiWaiObj.Blog_Author = "ShareChiWai"<br /> ShareChiWaiObj.Blog_Content = "My content"<br /> ShareChiWaiObj.Blog_DateCreated = Now<br /> ShareChiWaiObj.Blog_ID = 1<br /> ShareChiWaiObj.Blog_Title = "Object Initializer Example"<br /> [/vb]
  </p>
</div>

<div>
  最近我終於發現了如何在VB.Net 中 在建立 Instance 的同時也初始化這Object/instance 的屬性<br /> 是這樣的<br /> [vb]<br /> Dim ShareChiWaiObj As New ShareChiWaiClass With<br /> {.Blog_Author = "ShareChiWai",<br /> .Blog_Content = "My content",<br /> .Blog_DateCreated = Now,<br /> .Blog_ID = 1,<br /> .Blog_Title = "Object Initializer Example"<br /> }<br /> [/vb]</p> 
  
  <p>
    需要使用With 這個關鍵字&#8230;<br /> 和在Assign 屬性時 需要加&#8221;.&#8221; 相對比C# 麻煩一點點&#8230;<br /> 但是和以前的做法對比一下卻方便很多了
  </p>
</div>

<div>
  Hope you find it useful
</div>