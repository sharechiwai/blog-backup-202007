---
id: 260
title: 'MSSQL Query timeout expired &#8212; OLE DB provider &#8220;SQLNCLI10&#8221; for linked server &#8220;[Server Name]&#8221; returned message &#8220;Query timeout expired&#8221;'
date: 2010-03-20T03:20:00+08:00
author: ShareChiWai
layout: post
guid: http://sharechiwai.wordpress.com/2010/03/20/mssql-query-timeout-expired-ole-db-provider-sqlncli10-for-linked-server-server-name-returned-message-query-timeout-expired
permalink: /2010/03/mssql-query-timeout-expired-ole-db-provider-sqlncli10-for-linked-server-server-name-returned-message-query-timeout-expired/
blogger_blog:
  - sharechiwai.blogspot.com
blogger_author:
  - 智/Chi
blogger_242190872ae71f6d0f1f8731ec21ccf3_permalink:
  - "8578341713437301910"
categories:
  - MSSQL Tips and Tricks
---
When I try to transfer data from one database to another via linked server, I have received the following error.  
<span style="font-size:x-small;"><b><br />OLE DB provider &#8220;SQLNCLI10&#8221; for linked server &#8220;[Server Name]&#8221; returned message &#8220;Query timeout expired&#8221;.<br />Msg 7399, Level 16, State 1, Line 35<br />The OLE DB provider &#8220;SQLNCLI10&#8221; for linked server &#8220;[Server Name]&#8221; reported an error. Execution terminated by the provider because a resource limit was reached.<br />Msg 7421, Level 16, State 2, Line 35<br />Cannot fetch the rowset from OLE DB provider &#8220;SQLNCLI10&#8221; for linked server &#8220;[Server Name]&#8221;. .</b></span>

I have similar issue before [few months ago], but it has been fixed. I have tried several time, I still received the same error, not matter which computer I am running that query from. When I read the error message carefully. I realise it is something to do with the settings on the database.

**Here it is the solution.**  
1) Login to the linked server.[Ensure you have the right to edit the database server settings, otherwise you would need to contact your DBA/System Admin]  
2) Then run the following query  
<span style="font-size:x-small;"><b><span style="color:#6aa84f;">sp_configure &#8216;remote query timeout&#8217;, 0  &#8211;0 mean no timeout limit, if you would like to give a time limit you can modify the value 0 to something else. I guess it is second.</span><br style="color:#6aa84f;" /><span style="color:#6aa84f;">go</span></b></span>  
After that you will receive the similar message as below.  
<span style="font-size:x-small;"><b><span style="color:red;">DBCC execution completed. If DBCC printed error messages, contact your system administrator.</span><br style="color:red;" /><span style="color:red;">Configuration option &#8216;remote query timeout (s)&#8217; changed from 600 to 0. Run the RECONFIGURE statement to install.</span></b></span>  
3)Then you need to run the query below to apply the update.  
<span style="font-size:x-small;"><b><span style="color:#6aa84f;">reconfigure with override</span><br style="color:#6aa84f;" /><span style="color:#6aa84f;">go</span></b></span>  
[you can run the both query on the same statement like below]  
<span style="font-size:x-small;"><b><span style="color:#6aa84f;">sp_configure &#8216;remote query timeout&#8217;, 0  &#8211;0 mean no timeout limit, if you would like to give a time limit you can modify the value 0 to something else. I guess it is second.</span><br style="color:#6aa84f;" /><span style="color:#6aa84f;">go</span><br style="color:#6aa84f;" /><span style="color:#6aa84f;">reconfigure with override</span><br style="color:#6aa84f;" /><span style="color:#6aa84f;">go</span></b></span>

Finally, you can try to run the query again and see if it resolve the timeout issue.

Good luck!

Hope you find it useful!