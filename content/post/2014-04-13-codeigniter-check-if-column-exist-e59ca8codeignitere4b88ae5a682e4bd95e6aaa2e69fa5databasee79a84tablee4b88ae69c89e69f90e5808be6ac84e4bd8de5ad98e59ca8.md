---
id: 3145
title: 'Codeigniter check if column exist &#8211; 在Codeigniter上如何檢查Database的Table上有某個欄位存在'
date: 2014-04-13T00:00:10+08:00
author: ShareChiWai
layout: post
guid: http://blog.sharechiwai.com/?p=3145
permalink: '/2014/04/codeigniter-check-if-column-exist-%e5%9c%a8codeigniter%e4%b8%8a%e5%a6%82%e4%bd%95%e6%aa%a2%e6%9f%a5database%e7%9a%84table%e4%b8%8a%e6%9c%89%e6%9f%90%e5%80%8b%e6%ac%84%e4%bd%8d%e5%ad%98%e5%9c%a8/'
categories:
  - Codeingter
---
在**Codeigniter**上如何檢查**Database**的**Table**上有某個欄位存在  
我們可以使用 **$this->db->field_exists**  
當這個欄位在表上不存在時會 <span style="color: #ff0000;"><strong>return false</strong></span>

[php]  
if ($this->db->field\_exists(&#8216;field\_name&#8217;, &#8216;table_name&#8217;))  
{

}  
[/php]

詳情可以參考以下網址  
<a title="Codeigniter Field User Guide" href="http://ellislab.com/codeigniter/user-guide/database/fields.html" target="_blank">http://ellislab.com/codeigniter/user-guide/database/fields.html</a>

Hope you find it useful