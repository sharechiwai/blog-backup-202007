---
id: 364
title: MSSQL 2008 Saving changes is not permitted. THe changes you have made require the following table to be dropped and re-created.
date: 2009-09-16T09:16:00+08:00
author: ShareChiWai
layout: post
guid: http://sharechiwai.wordpress.com/2009/09/16/mssql-2008-saving-changes-is-not-permitted-the-changes-you-have-made-require-the-following-table-to-be-dropped-and-re-created
permalink: /2009/09/mssql-2008-saving-changes-is-not-permitted-the-changes-you-have-made-require-the-following-table-to-be-dropped-and-re-created/
blogger_blog:
  - sharechiwai.blogspot.com
blogger_author:
  - 智/Chi
blogger_242190872ae71f6d0f1f8731ec21ccf3_permalink:
  - "4655360349527081291"
categories:
  - MSSQL Tips and Tricks
---
<span class="Apple-style-span" style="font-family:Verdana;font-size:7px;"><span class="Apple-style-span" style="font-size:48px;"><span class="Apple-style-span" style="font-family:'Times New Roman';font-size:16px;"></p> 

<div style="font-family:Verdana;font-size:10pt;background-color:rgb(255,255,255);min-height:1100px;counter-reset:__goog_page__ 0;line-height:normal;margin:6px;padding:0;">
  <div style="margin-top:0;margin-bottom:0;">
    When I try to update the schema of a table I have received a error below.<br /><img src="http://api.photoshop.com/home_453edadf42c44e2bba351fb5d2dfaeb1/adobe-px-assets/8c0a92649bd94451ba1cb49f997b1ef3" width="380" height="300" /><br />&#8220;<span style="color:rgb(255,0,0);">Saving changes is not permitted. THe changes you have made require the following table to be dropped and re-created. You have either made changes to a table that can&#8217;t be re-created or enabled the option Prevent saving changes that require the table to be re-created.</span>&#8220;</p> 
    
    <div style="margin-top:0;margin-bottom:0;">
    </div>
    
    <p>
      Finally I knew what is wrong on my Management studio, I have &#8220;<b>Prevent saving changes that require the table to be re-creation</b>.&#8221; option set.<br />It is very easy to solve this problem.<br />1) On <b>SQL Server Management Studio</b><br />2) Click on &#8220;<b>Tools</b>&#8221; then select &#8220;<b>Options&#8230;</b>&#8220;<br />3) You will then see the screen below popped up.<br /><img src="http://api.photoshop.com/home_453edadf42c44e2bba351fb5d2dfaeb1/adobe-px-assets/2936e9b2f227488aab08ff6c2c16ba5e" width="557" height="338" /><br />4) Click on the &#8220;<b>Designer</b>&#8221; tab<br />5) Untick the check box which said &#8220;<b>Prevent saving changes that require the table to be re-creation.</b>&#8220;<br />6) Click &#8220;<b>OK</b>&#8221; and try again.
    </p>
    
    <p>
      It should allow you to update the table schema.
    </p>
    
    <p>
      Good luck</div> </div> 
      
      <p>
        </span></span></span>
      </p>