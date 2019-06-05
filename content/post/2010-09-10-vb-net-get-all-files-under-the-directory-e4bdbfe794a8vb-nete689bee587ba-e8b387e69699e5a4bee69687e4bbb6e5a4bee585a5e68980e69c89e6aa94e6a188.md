---
id: 613
title: 'VB.Net Get All files under the directory &#8212;使用VB.Net找出 資料夾/文件夾入所有檔案'
date: 2010-09-10T05:00:13+08:00
author: ShareChiWai
layout: post
guid: http://sharechiwai.wordpress.com/?p=613
permalink: '/2010/09/vb-net-get-all-files-under-the-directory-%e4%bd%bf%e7%94%a8vb-net%e6%89%be%e5%87%ba-%e8%b3%87%e6%96%99%e5%a4%be%e6%96%87%e4%bb%b6%e5%a4%be%e5%85%a5%e6%89%80%e6%9c%89%e6%aa%94%e6%a1%88/'
jabber_published:
  - "1284066056"
delicious:
  - 's:78:"a:3:{s:5:"count";s:1:"0";s:9:"post_tags";s:0:"";s:4:"time";s:10:"1284381900";}";'
email_notification:
  - "1284066057"
categories:
  - .Net Tips And Tricks
---
最近有朋友問如果可以用**VB.Net** 找出 資料夾內有什麼檔案&#8230;  
我之前都用了一段時間去思考怎樣才做到  
因為首先要把資料夾內的 檔案找出&#8230;  
當遇到**資料夾內的資料夾**時&#8230;  
要繼續深入/向下找其他的檔案

最後回想到之前在大學&#8230;學的東西&#8230;  
[是用**Haskell** <&#8211; 一種**Functional Programming** 的語言]  
我十分喜歡的  
好像在 **Haskell** 中 不能用For **Loop/While Loop**  
所以用了一個技巧叫&#8221;**Recursion**&#8220;&#8230;  
是**Call 自己的Method 做到Loop 的效果**

今次我便用了這個技巧 寫了一個小小的功能幫助自己找出 資料夾/文件夾入所有檔案  
程式碼如下:  
<span style="color:#0000ff;"><br /> Public Function GetAllFilesOnTheDirectory(ByVal folderPath As String, ByVal includeSubdirectories As Boolean) As FileInfo()<br /> <span style="color:#008000;">&#8216;建立一個FileInfo Array可以用來查詢檔案的資料</span><br /> Dim FileLists As New List(Of FileInfo)<br /> <span style="color:#008000;">&#8216;建立一個DirectoryInfo Object 用來查詢這個Directory</span><br /> Dim dirInfo As New DirectoryInfo(folderPath)<br /> <span style="color:#008000;">&#8216;把DirectoryInfo.GetFiles找到的 FileInfo Object 加到Array 上</span><br /> FileLists.AddRange(dirInfo.GetFiles)<br /> <span style="color:#008000;">&#8216;如果想找出全部 [includeSubdirectories = True] 的話</span><br /> If includeSubdirectories Then<br /> <span style="color:#008000;">&#8216;找出所有在這個資料夾入的Sub資料夾</span><br /> Dim DirList() As DirectoryInfo = dirInfo.GetDirectories<br /> <span style="color:#008000;">&#8216;之後用For Loop 以Recursion 的方法[自己Call 自己的形式] 來找出所有的檔案</span><br /> For i As Integer = 0 To DirList.Length &#8211; 1<br /> <span style="color:#008000;">&#8216;之後把找到的檔案加到Array 上</span><br /> FileLists.AddRange(GetAllFilesOnTheDirectory(DirList(i).FullName, includeSubdirectories))<br /> Next<br /> End If<br /> Return FileLists.ToArray<br /> End Function</span>

將會把這個程式碼Compile 成一個DLL 放便大家使用 =P

Hope you find it useful