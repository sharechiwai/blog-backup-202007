---
id: 4117
title: 'C# Distinct List of Object'
date: 2019-02-16T12:14:51+08:00
author: ShareChiWai
layout: post
guid: https://blog.sharechiwai.com/?p=4117
permalink: /2019/02/c-distinct-list-of-object/
categories:
  - .Net Tips And Tricks
tags:
  - LINQ
---
今日在Code Review 同事的Code 時候發現了一個有趣的寫法  
他想做的是 Return 一個Distinct 左既 List Of Object  
  
好直接既想法是使用 Distinct

<pre class="wp-block-preformatted">List.Distinct();</pre>

之後發現Distinct 是不能 Distinct Object的  
同事的寫法是用了 List 加 GroupBy 和Select First()

<pre class="wp-block-preformatted">List.GrounBy(x=&gt; x.key).Select(x =&gt; x.First())

</pre>

之後發現.. 原來我們可以使用 GroupBy 加 First 來做到 Distinct Object的效果  
以下是我的 Code Sample  


<pre class="wp-block-syntaxhighlighter-code">void Main()
{
	var list = new List&lt;Example>();
	list.Add(new Example() {Id=1, Name="Example 1", Comment="Comment 1" });
	list.Add(new Example() {Id=1, Name="Example 1", Comment="Comment 1" });
	list.Add(new Example() {Id=1, Name="ExamplE 1", Comment="Comment 2" });
	list.Add(new Example() {Id=2, Name="Example 2", Comment="Comment 3" });
	list.Add(new Example() { Id = 2, Name = "example 2", Comment = "Comment 3" });
	list.Add(new Example() { Id = 3, Name = "Example 3", Comment = "Comment 3" });
	list.Add(new Example() { Id = 4, Name = "Example 4", Comment = "Comment 3" });
	list.Add(new Example() { Id = 5, Name = "Example 5", Comment = "Comment 3" });

	Console.WriteLine("Use List.Distinct()");
	list.Distinct().Dump();

	Console.WriteLine("Use Group By Fields");
	list.GroupBy(x => new {x.Id, Name=x.Name}).Select(x =>x.First()).Dump();

	Console.WriteLine("Use Group By and make it ignore case");
	list.GroupBy(x => new {x.Id, Name=x.Name.ToLower()}).Select(x =>x.First()).Dump();
}

public class Example
{
	public int Id { get; set; }
	public string Name { get; set; }
	public string Comment {get;set;}
}</pre>

Output:  
  
<figure class="wp-block-image">

<img src="https://i0.wp.com/blog.sharechiwai.com/wp-content/uploads/2019/02/image-1.png?w=625&#038;ssl=1" alt="" class="wp-image-4118" srcset="https://i0.wp.com/blog.sharechiwai.com/wp-content/uploads/2019/02/image-1.png?w=472 472w, https://i0.wp.com/blog.sharechiwai.com/wp-content/uploads/2019/02/image-1.png?resize=176%2C300 176w" sizes="(max-width: 472px) 100vw, 472px" data-recalc-dims="1" /> <figcaption>Hope you find it useful</figcaption></figure>