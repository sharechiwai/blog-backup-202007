---
id: 2617
title: .Net Get All files under the directory Improved version—使用.Net找出 資料夾/文件夾入所有檔案改進版
date: 2012-11-27T00:00:22+08:00
author: ShareChiWai
layout: post
guid: http://blog.sharechiwai.com/?p=2617
permalink: '/2012/11/net-get-all-files-under-the-directory-improved-version-%e4%bd%bf%e7%94%a8-net%e6%89%be%e5%87%ba-%e8%b3%87%e6%96%99%e5%a4%be%e6%96%87%e4%bb%b6%e5%a4%be%e5%85%a5%e6%89%80%e6%9c%89%e6%aa%94/'
categories:
  - .Net Tips And Tricks
tags:
  - LINQ
---
很久之前寫過一個網誌是介紹如何找出 資料夾/文件夾入所有檔案

## <a title="Permalink to VB.Net Get All files under the directory —使用VB.Net找出 資料夾/文件夾入所有檔案" href="http://blog.sharechiwai.com/2010/09/vb-net-get-all-files-under-the-directory-%e4%bd%bf%e7%94%a8vb-net%e6%89%be%e5%87%ba-%e8%b3%87%e6%96%99%e5%a4%be%e6%96%87%e4%bb%b6%e5%a4%be%e5%85%a5%e6%89%80%e6%9c%89%e6%aa%94%e6%a1%88/" rel="bookmark">VB.Net Get All files under the directory —使用VB.Net找出 資料夾/文件夾入所有檔案</a>

<span style="line-height: 1.714285714; font-size: 1rem;">之前是用一個叫<strong>Recursion</strong> 的方法來取得資料夾裡面的資料夾內的檔案&#8230;</span>  
最近另外一個Project上又要做一個差不多的功能  
令使用者可以看到資料夾入有什麼檔案可以下載  
回看返之前的Blog 這個功能應該不用寫到那麼複雜的  
還有這個function的效能其實也不太好

所以便去做一下research看看有沒有更好的解決方法了

**解決方法**:  
原來我做可以使用DirectoryInfo中的GetFiles 方法  
我們還可以設定一些變數去選擇要找出資料夾入..那一類型的檔案等等

E.G.  
使用**DirectoryInfo** 的**GetFiles**功能  
<span style="color: #339966;"><strong>DirectoryInfo dirInfo = new DirectoryInfo(&#8220;資料夾路徑&#8221;);</strong></span>  
第一個變數是**Filter File Extension** &#8220;\*.\*&#8221; 是選擇所有檔案 而 &#8220;*.txt&#8221;則是只選擇 .txt  
<span style="color: #339966;"><strong>List FileInfoList = dirInfo.GetFiles(Extension Filter, SearchOption).ToList();</strong></span>  
**C#**

[csharp]

// Initialise DirectoryInfo 設定將要找出檔案的資料夾  
DirectoryInfo dirInfo = new DirectoryInfo(txt_Folder.Text.Trim());

// 使用DirectoryInfo 的GetFiles功能  
// 第一個變數是Filter File Extension "\*.\*" 是選擇所有檔案 而 "*.txt"則是只選擇 .txt  
// 第二個變數是SearchOption 有 AllDirectories 和 TopDirectoryOnly 2個選擇,  
// 我們想找出資料夾入所有的檔案..包括資料夾內的資料夾所以我們會用到AllDirectories  
List<FileInfo> fileInfoList = dirInfo.GetFiles("\*.\*", SearchOption.AllDirectories).ToList();

// 如果你只需要檔案名稱的話可以使用Directory Instead of Directory List.. 他會  
// List<String> fileInfoList = Directory.GetFiles(txt_Folder.Text.Trim(), "\*.\*", SearchOption.AllDirectories).ToList();

dgv_FileList.DataSource = fileInfoList;  
[/csharp]

Hope you find it useful