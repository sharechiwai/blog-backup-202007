---
id: 3440
title: '.Net Wildcard Pattern Matching &#8211; 在.Net上如果使用Wildcard的Pattern matching呢?'
date: 2015-07-13T00:00:30+08:00
author: ShareChiWai
layout: post
guid: http://blog.sharechiwai.com/?p=3440
permalink: '/2015/07/net-wildcard-pattern-matching-%e5%9c%a8-net%e4%b8%8a%e5%a6%82%e6%9e%9c%e4%bd%bf%e7%94%a8wildcard%e7%9a%84pattern-matching%e5%91%a2/'
categories:
  - .Net Tips And Tricks
tags:
  - .Net Troubleshooting
  - Pattern Matching
  - Regex
  - Regular Expression
  - VB to CSharp
  - Wildcard
---
現在寫程式時..很多人會使用**Regular Expression** 來做**Pattern Matching**  
來檢查字串的值符合 **pattern** 所包含的模式嗎.  
<a href="http://msdn.microsoft.com/zh-tw/library/swf8kaxw.aspx" target="_blank">http://msdn.microsoft.com/zh-tw/library/swf8kaxw.aspx</a>

在**VB.Net**上 他有一個 **LIKE**的 **Operator**/運算子  
可以做到這個動作

可惜如果你是使用**C Sharp**的話  
你便要自己寫一些功能去把這些**Wildcard** 轉換成**Regular Expression**的**Pattern**了

以下是我寫的功能

<pre>/// This static function is used to replace the regular wild card search text pattern to Regular Express pattern
        public static string WildCardToRegexPattern(string pattern)
        {
            return "^" + Regex.Escape(pattern).Replace("\\*", ".*").Replace("\\?", ".") + "$";
        }     

        /// This function is used to execute the wild card match which is similar to VB's LIKE function
        public static bool WildCardMatch(string input, string pattern)
        {
            // Execute pattern matching against the wild card after convert the wild card to Regular Expression pattern via WildCardToRegexPattern function
            return Regex.IsMatch(input, WildCardToRegexPattern(pattern));
        }

</pre>

**使用方法**:

<pre>string input = "abc111";
string pattern = "*11*";

Console.WriteLine(WildCardMatch(input, pattern));
</pre>

Hope you find it useful