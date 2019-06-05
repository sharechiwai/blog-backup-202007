---
id: 2536
title: '.net get file extension from string &#8212; 在.Net上如何在字串上找到文件擴展名'
date: 2012-08-11T00:00:42+08:00
author: ShareChiWai
layout: post
guid: http://blog.sharechiwai.com/?p=2536
permalink: '/2012/08/net-get-file-extension-from-string-%e5%9c%a8-net%e4%b8%8a%e5%a6%82%e4%bd%95%e5%9c%a8%e5%ad%97%e4%b8%b2%e4%b8%8a%e6%89%be%e5%88%b0%e6%96%87%e4%bb%b6%e6%93%b4%e5%b1%95%e5%90%8d/'
categories:
  - .Net Tips And Tricks
---
在最近寫的**ASP.Net MVC Application** 上終於寫到了給客戶D**ownload Report**的功能了  
為了令到Download時可以Browser可以明白他們是什麼的檔案格式..  
所以我便寫了一個取得**MIME TYPE** 的功能了..  
但是這個功能要需要輸入**File Extension** / **文件擴展名**才可以以使用的.

所以我便嘗試自己寫另一個功能來取後**File Extension** 了

以下是我的小小功能  
做法十分愚蠢&#8230;就是嘗試找到取後一個&#8221;**.**&#8220;的位置..之後使用**SubString**取得他的值..  
E.G.

[csharp]  
public string GetFileExtension(string filename){  
return Filename.Substring(Filename.LastIndexOf(".") + 1, Filename.Length &#8211; Filename.LastIndexOf(".") &#8211; 1);  
}

string FileExtension = GetFileExtension("sharechiwai.txt");  
//結果: FileExtension = ".txt";  
[/csharp]

誰不知..原來.**Net Framework**一有一個功能方便大家從String/字串上 取得File Extension.

**Path.GetExtension**(**檔案名稱**)

E.G.

[csharp]  
string FileExtenstion = Path.GetExtension("sharechiwai.txt");  
//結果: FileExtension = ".txt";  
[/csharp]

Hope you find it useful