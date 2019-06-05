---
id: 551
title: 'VB.Net How to Add Image to Access Database &#8212; VB.Net 如何把圖片加入到Access資料庫上'
date: 2010-09-03T00:00:03+08:00
author: ShareChiWai
layout: post
guid: http://sharechiwai.wordpress.com/?p=551
permalink: '/2010/09/vb-net-how-to-add-image-to-access-database-vb-net-%e5%a6%82%e4%bd%95%e6%8a%8a%e5%9c%96%e7%89%87%e5%8a%a0%e5%85%a5%e5%88%b0access%e8%b3%87%e6%96%99%e5%ba%ab%e4%b8%8a/'
jabber_published:
  - "1283446065"
email_notification:
  - "1283446067"
delicious:
  - 's:78:"a:3:{s:5:"count";s:1:"0";s:9:"post_tags";s:0:"";s:4:"time";s:10:"1283982582";}";'
categories:
  - .Net Tips And Tricks
  - MSSQL Tips and Tricks
---
今天有朋友問到如何把圖片[**Image**] 放進資料庫上  
我想了很久..也不懂得怎樣回答&#8230;  
因為我沒有想過把圖片加進資料庫&#8230;  
可能是我做的程式都是會在公司內部用  
所以所有的圖片檔都是方進NAS Drive 的  
經過檔案路徑去找尋圖片檔案  
之後再用  
<span style="color: #0000ff;">Dim im as Image = Image.FromFile(Filepath 和 FileName) </span>&#8216;取出圖片的

今日希望可以和大家分享我把圖片放進資料庫上的Table  [**Access** 的]  
首先我們要建立一個Access Database

建立一個Table 叫 &#8220;**PictureDB**&#8221;  
入面有2個Field 分別是  
**ID -> AutoNumber**  
**PIC -> OLE Object** 用來儲存圖片的Byte Array 的

把資料庫設定好後我們便可以開始用Visual Studio 寫Code 了

我建立了一個Method 特別是用來把圖片放進資料庫的  
**AddImageToDataBase(圖片檔的Full Path)**

<span style="color: #008000;">&#8216;全段把圖片加進Database 的程式碼</span>  
[vb]  
Public Sub AddImageToDataBase(ByVal PicFileName As String)

&#8216;用File Stream 把這個圖片檔 打開成Stream  
Dim pic As New FileStream(PicFileName, FileMode.Open)  
&#8216;定義一個Byte Array來儲存 這個檔案的Byte  
Dim FileByteArray(pic.Length &#8211; 1) As Byte  
&#8216;把這個檔案的 資料寫進已定義的ByteArray 裡  
pic.Read(FileByteArray, 0, pic.Length)  
&#8216; 關掉這個圖片檔的Stream  
pic.Close()

&#8216;SQL 用來把這圖片加進 database 上  
Dim sql As String = "INSERT INTO pictureDB(PIC) values (@pic)"  
Dim objConn As New OleDbConnection  
Dim objComm As New OleDbCommand  
&#8216;設定這個SQL Connection 的SQL Connection string  
objConn.ConnectionString = ConStr &#8216;ConStr是 SQL Connection的字串

Try

&#8216;設定這個SQL Command 的SQL 查詢句子  
objComm.CommandText = sql  
&#8216;設定這個SQL Command的 Connection  
objComm.Connection = objConn  
&#8216;Assign SQL Variable 的內容  
objComm.Parameters.AddWithValue("@pic", pic)  
&#8216;打開SQL Connection  
objConn.Open()  
&#8216;執行這個SQL 指令  
objComm.ExecuteNonQuery()  
&#8216;完成後出現一個Pop Up Message 出  
MsgBox("OK")

Catch ex As Exception  
&#8216;當有錯誤發生時出現一個 Pop Up Message 說明錯誤  
MsgBox(ex.Message)  
Finally

objComm = Nothing  
&#8216;關閉SQL Connection  
objConn.Close()  
objConn = Nothing

End Try

End Sub  
[/vb]

相信在SQL Server 的做法也是大致上一樣的

Hope you find it useful

下一節的網誌會介紹如何把這圖片