---
id: 356
title: Set up MSSQL Server 2008 Management Studio SSMS2008
date: 2009-09-27T09:27:00+08:00
author: ShareChiWai
layout: post
guid: http://sharechiwai.wordpress.com/2009/09/27/set-up-mssql-server-2008-management-studio-ssms2008
permalink: /2009/09/set-up-mssql-server-2008-management-studio-ssms2008/
blogger_blog:
  - sharechiwai.blogspot.com
blogger_author:
  - 智/Chi
blogger_242190872ae71f6d0f1f8731ec21ccf3_permalink:
  - "8474076218013468102"
categories:
  - MSSQL Tips and Tricks
---
It is quite convenient to use a GUI tools to manage the database. E.g. SQL Server Management Studio.

If you have installed SQL Server 2008 when you try to connect it with &#8220;SQL 2000 Enterprise Manager&#8221; You may receive a message to ask you to use Management Studio&#8230;etc.

When you search for MS SQL Management Studio 2008, you may be able to find a link for you to download Management Studio 2005  
<a href="http://www.microsoft.com/downloads/details.aspx?displaylang=en&FamilyID=c243a5ae-4bd1-4e3d-94b8-5a0f62bf7796" target="_blank" title="SQL Server Management Studio 2005">http://www.microsoft.com/downloads/details.aspx?displaylang=en&FamilyID=c243a5ae-4bd1-4e3d-94b8-5a0f62bf7796</a>

If you want to use MS SQL Server 2008 Management Studio. You would need to download &#8220;SQL Server 2008 Express with tools&#8221; or **&#8220;SQL Server 2008 Express with Advanced Services&#8221;**. Or if you have a copy of SQL Server 2008 (Not the express edition), you can install it there.

You can go to the following URL to download **SQL Server 2008 Express Edition**  
<a href="http://www.microsoft.com/express/sql/download/" target="_blank" title="Download SQL Server 2008 Express Edition">http://www.microsoft.com/express/sql/download/</a>

After you download **SQL Server 2008 Express with Tools or Advanced Services**.

You can go throught the installation process.

  1. Run the **&#8220;.exe&#8221;** file
  2. Then click on Installation on the Left hand side menu.
  3. Select &#8220;New SQL Server stand-alone installation or add features to an existing installation&#8221;  
    [<img alt="" height="300" src="http://api.photoshop.com/home_453edadf42c44e2bba351fb5d2dfaeb1/adobe-px-assets/8de4e68c053a4203955e613f3056c5b7" title="SQL Server 2008 Installation Centre" width="400" />](http://api.photoshop.com/home_453edadf42c44e2bba351fb5d2dfaeb1/adobe-px-assets/8de4e68c053a4203955e613f3056c5b7)
  4. Then run throught the process to install the setup file and finish all the checking&#8230;etc
  5. (E.g. Click &#8220;Next&#8221;, &#8220;Next&#8221;, &#8220;Next&#8221;,&#8230;etc)
  6. Then you will see the **&#8220;Installation Type&#8221;** screen as below.  
    [<img alt="" height="315" src="http://api.photoshop.com/home_453edadf42c44e2bba351fb5d2dfaeb1/adobe-px-assets/8beb14ab30fd4c8a851985ee7a9af9ab" title="Install Type" width="420" />](http://api.photoshop.com/home_453edadf42c44e2bba351fb5d2dfaeb1/adobe-px-assets/8beb14ab30fd4c8a851985ee7a9af9ab)
  7. Select **&#8220;Add features to an existing instance of SQL Server 2008&#8221;** (if you already installed SQL 2008) Or **&#8220;Perform a new installation of SQL Server 2008&#8221;** if you just want to use the tools
  8. If you selected **&#8220;Perform a new installation of SQL Server 2008&#8221;** you will see another screen about **License Agreement**
  9. After you agree the license you will see the following screen.  
    [<img alt="" height="315" src="http://api.photoshop.com/home_453edadf42c44e2bba351fb5d2dfaeb1/adobe-px-assets/a73a940a718c4e2f8e1b54e1ce3c8b70" title="Feature Selection" width="420" />](http://api.photoshop.com/home_453edadf42c44e2bba351fb5d2dfaeb1/adobe-px-assets/a73a940a718c4e2f8e1b54e1ce3c8b70)
 10. Select **&#8220;Shared Feature&#8221;** -> **&#8220;Management Tools &#8211; Basic&#8221;**
 11. If will carry on ask you several question about when do you want to install to &#8230;etc.
 12. After gone through all the &#8220;Next&#8221;, &#8220;Next&#8221;, &#8220;Next&#8221;.

&#8211;>**&#8220;Disk Space Requirement&#8221;**

<div>
  &#8211;><b>&#8220;Server Configuation&#8221;</b><br />&#8211;><b>&#8220;Error and Usage Reporting&#8221;</b><br /><b>&#8211;></b><b>&#8220;Installation Rules&#8221;</b></p> 
  
  <p>
    13. Then you will come to a screen about <b>&#8220;Ready to Install&#8221;</b><br />14. After you click on Install. It will process the installation.<br />15. Finally, you will see Management Studio on you<b> &#8220;Start Menu&#8221;</b></div> 
    
    <p>
      Have fun.
    </p>