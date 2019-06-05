---
id: 363
title: List VS String()
date: 2009-09-17T09:17:00+08:00
author: ShareChiWai
layout: post
guid: http://sharechiwai.wordpress.com/2009/09/17/list-vs-string
permalink: /2009/09/list-vs-string/
blogger_blog:
  - sharechiwai.blogspot.com
blogger_author:
  - 智/Chi
blogger_242190872ae71f6d0f1f8731ec21ccf3_permalink:
  - "3113053693159617702"
categories:
  - .Net Tips And Tricks
---
<span class="Apple-style-span" style="font-family:'Times New Roman';"></p> 

<div style="width:auto;font:normal normal normal 100%/normal Georgia, serif;text-align:left;border-color:initial;border-style:initial;border-width:0;margin:0;padding:3px;">
  My friend has asked an interesting question. He asked about what is the different of <span style="font-weight:bold;">List and String() [String array]</span>.<br />Um&#8230; I cannot see much different, as both of them store a list/array of string.<br />But actually if I have a choice, I would choose to use List rather than String array.<br />Because&#8230;</p> 
  
  <p>
    If we just treat it as general.<br /><span style="font-weight:bold;">List VS Array.</span><br />You need to know the size of the array that you are going to create, once the array has been created, you cannot modify the size<br />of that array again.<br />If you use Generic List, you will not have that problem. Because it provides you a lot of useful method, E.g. Add, Remove, Insert,<br />Find, Sort&#8230;etc. and the code seems easier to ready as well.
  </p>
  
  <p>
    Instead of having to know which slot of the array I need to assign the value to.<br />E.g.<br /><span style="color:rgb(0,153,0);font-size:85%;">//Array<br />Array[0]=&#8221;abc&#8221;</span>
  </p>
  
  <p>
    You can use the following code to perform Add. In this case you can add as much value as you like by using .Add method<br /><span style="color:rgb(0,153,0);font-size:85%;">list.Add(&#8220;abc&#8221;)<br /></span><br />Do you think it does looks better?
  </p>
  
  <p>
    Hope you find this useful.<br />Please correct me if you find my concept is wrong.</div> 
    
    <p>
      </span>
    </p>