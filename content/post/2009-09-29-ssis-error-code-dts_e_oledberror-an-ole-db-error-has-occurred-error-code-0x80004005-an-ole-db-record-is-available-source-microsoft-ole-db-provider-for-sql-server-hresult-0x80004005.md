---
id: 355
title: 'SSIS Error Code DTS_E_OLEDBERROR. An OLE DB error has occurred. Error code: 0x80004005. An OLE DB record is available. Source: &#8220;Microsoft OLE DB Provider for SQL Server&#8221; Hresult: 0x80004005 Description: &#8220;[DBNETLIB][ConnectionOpen (Connect()).]SQL Server does not exist or access denied.&#8221;'
date: 2009-09-29T09:29:00+08:00
author: ShareChiWai
layout: post
guid: http://sharechiwai.wordpress.com/2009/09/29/ssis-error-code-dts_e_oledberror-an-ole-db-error-has-occurred-error-code-0x80004005-an-ole-db-record-is-available-source-microsoft-ole-db-provider-for-sql-server-hresult-0x80004005
permalink: /2009/09/ssis-error-code-dts_e_oledberror-an-ole-db-error-has-occurred-error-code-0x80004005-an-ole-db-record-is-available-source-microsoft-ole-db-provider-for-sql-server-hresult-0x80004005/
blogger_blog:
  - sharechiwai.blogspot.com
blogger_author:
  - 智/Chi
blogger_242190872ae71f6d0f1f8731ec21ccf3_permalink:
  - "909347282396747564"
categories:
  - SSIS
---
When I open the SSIS project from I can see the following error from the &#8220;**Error List**&#8221; Panel

<span style="font-size:x-small;"><b>&#8216;Error    1    Validation error. Export Data Flow Task1: Package1: SSIS Error Code DTS_E_OLEDBERROR.  An OLE DB error has occurred. Error code: 0x80004005.  An OLE DB record is available.  Source: &#8220;Microsoft OLE DB Provider for SQL Server&#8221;  Hresult: 0x80004005  Description: &#8220;[DBNETLIB][ConnectionOpen (Connect()).]SQL Server does not exist or access denied.&#8221;.      Package1.dtsx    0    0    &#8216;<br /></b></span>  
I am wondering why SQL Server access denied, at the end, I realise the SQL service do not start automatically.

TO solve it I just need to  
&#8220;**Start**&#8221; -> &#8220;**Control Panel**&#8220;-> &#8220;**Administrative Tools**&#8220;-> &#8220;**Services**&#8220;  
Then select the SQL Server instance that you want to start up the service.  
Right click on it and select &#8220;**Start**&#8220;.

Then you may want to close down the project and re-open it again.  
The error message should disappear.