---
id: 118
title: .Net to Sort DataGridView Programmatically
date: 2010-05-25T00:00:00+08:00
author: ShareChiWai
layout: post
guid: http://sharechiwai.wordpress.com/2010/05/25/net-to-sort-datagridview-programmatically
permalink: /2010/05/net-to-sort-datagridview-programmatically/
blogger_blog:
  - sharechiwai.blogspot.com
blogger_author:
  - 智/Chi
blogger_242190872ae71f6d0f1f8731ec21ccf3_permalink:
  - "3202615807474188574"
categories:
  - .Net Tips And Tricks
  - ASP.Net Tips and Tricks
---
Today my friend has asked me a good question, he want to ensure the data on the **DataGridView** is in the correct sorting order. He is wondering how to achieve that. I still remember, I have tried something similar before. 

Here it is what you need to do:  
E.G. 

  1. We have a **DataGridView** called &#8220;**dgv_Membership**&#8220;
  2. This table contains &#8220;**Surname**&#8220;, &#8220;**First Name**&#8220;, &#8220;**DoB**&#8220;, &#8220;**Screen name**&#8220;
  3. We would like to sort the table by **DoB (Date Of Birth)** before we process that data.

What we need to do it to use the Sort method on the **DataGridView** control  
<span style="font-size:x-small;"><b>dgv_Membership.Sort(dgv_Membership.Columns(&#8220;Dob&#8221;),System.ComponentModel.ListSortDirection.Ascending )</b></span>

**Explanation**:  
**GridViewName.Sort(&#8220;GridViewColumn that you want to sort by&#8221;, &#8220;Sorting Direction&#8221;)**

Good Luck