---
id: 103
title: 'The AcquireConnection method call to the connection manager &#8220;Excel Connection Manager&#8221; failed with error code 0xC00F9304'
date: 2010-06-03T00:00:00+08:00
author: ShareChiWai
layout: post
guid: http://sharechiwai.wordpress.com/2010/06/03/the-acquireconnection-method-call-to-the-connection-manager-excel-connection-manager-failed-with-error-code-0xc00f9304
permalink: /2010/06/the-acquireconnection-method-call-to-the-connection-manager-excel-connection-manager-failed-with-error-code-0xc00f9304/
blogger_blog:
  - sharechiwai.blogspot.com
blogger_author:
  - 智/Chi
blogger_242190872ae71f6d0f1f8731ec21ccf3_permalink:
  - "2499430741791124637"
categories:
  - SSIS
---
When I try to use **SSIS** to import data **from Excel to Database**, it has failed and return the error message below.

**&#8220;<span style="color: #38761d;">The AcquireConnection method call to the connection manager &#8220;Excel Connection Manager&#8221; failed with error code 0xC00F9304</span>&#8220;**

<div class="separator" style="clear: both; text-align: center;">
</div>

<div class="separator" style="clear: both; text-align: center;">
</div>

<span style="font-size: x-small;"><strong><span style="color: #cc0000;">SSIS package &#8220;ShareChiWai.dtsx&#8221; starting.</span><br style="color: #cc0000;" /><span style="color: #cc0000;">Information: 0x4004300A at Import So from Excel, SSIS.Pipeline: Validation phase is beginning.</span><br style="color: #cc0000;" /><span style="color: #cc0000;">Error: 0xC020801C at Import So from Excel, Standing Order Excel File [1]: SSIS Error Code DTS_E_CANNOTACQUIRECONNECTIONFROMCONNECTIONMANAGER.  The AcquireConnection method call to the connection manager &#8220;Excel Connection Manager&#8221; failed with error code 0xC00F9304.  There may be error messages posted before this with more information on why the AcquireConnection method call failed.</span><br style="color: #cc0000;" /><span style="color: #cc0000;">Error: 0xC0047017 at Import So from Excel, SSIS.Pipeline: component &#8220;ShareChiWai Excel File&#8221; (1) failed validation and returned error code 0xC020801C.</span><br style="color: #cc0000;" /><span style="color: #cc0000;">Error: 0xC004700C at Import So from Excel, SSIS.Pipeline: One or more component failed validation.</span><br style="color: #cc0000;" /><span style="color: #cc0000;">Error: 0xC0024107 at Import So from Excel: There were errors during task validation.</span><br style="color: #cc0000;" /><span style="color: #cc0000;">SSIS package &#8220;ShareChiWai.dtsx&#8221; finished: Success.</span><br style="color: #cc0000;" /><span style="color: #cc0000;">The program &#8216;[4972] ShareChiWai.dtsx: DTS&#8217; has exited with code 0 (0x0).</span></strong></span>

I have done some research related with the error code 0xC00F9304. It said:  
**&#8220;<span style="color: #38761d;">SSIS Error Code DTS_E_OLEDB_EXCEL_NOT_SUPPORTED: The Excel Connection Manager is not supported in the 64-bit version of SSIS, as no OLE DB provider is available.</span>&#8220;**

Fortunately, I have worked out how to solve this issue: [because I have similar issue before with Visual Studio after upgrading the operating system to 64bit&#8230;]

**Here it is my solution:**  
Right click on your **SSIS** project in your &#8220;**Solution Explorer**&#8221;  
Then Select &#8220;**Properties**&#8221;  
On the &#8220;**Property Pages**&#8221; click on &#8220;**Debugging**&#8221;  
and Under &#8220;**Debug Options**&#8221; ->&#8221;**Run64ButRuntime**&#8221;  
Switch it from &#8220;**True**&#8221; to &#8220;**False**&#8221;  
so that the project will not start 64 bit SSIS runtime, even 64 bit SSIS runtime is installed. [This mean it will use the 32 bit runtime]

<div class="separator" style="clear: both; text-align: center;">
  <img src="http://api.photoshop.com/v1.0/accounts/aa9037104a014abbb11ad4bd58324b91/assets/3cf6a0e578da44ce880994565fcbf203" width="716" height="439" />
</div>

Hope you find it useful