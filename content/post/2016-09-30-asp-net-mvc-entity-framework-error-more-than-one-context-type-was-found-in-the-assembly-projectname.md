---
id: 3759
title: 'ASP.Net MVC Entity Framework Error &#8211; More than one context type was found in the assembly &#8216;ProjectName&#8217;.'
date: 2016-09-30T00:00:02+08:00
author: ShareChiWai
layout: post
guid: http://blog.sharechiwai.com/?p=3759
permalink: /2016/09/asp-net-mvc-entity-framework-error-more-than-one-context-type-was-found-in-the-assembly-projectname/
categories:
  - ASP.Net MVC
tags:
  - ApplicationDbContext
  - Entity Framework 筆記
---
最近愛上了使用**Entity Framework**..  
當我嘗試使用 &#8220;**enable-migrations**&#8221; 時出現以下的錯誤信息

<span style="color: #ff0000;"><strong>More than one context type was found in the assembly &#8216;LocalIssuesWeb&#8217;.</strong></span>  
<span style="color: #ff0000;"><strong> To enable migrations for &#8216;LocalIssuesWeb.Models.ApplicationDbContext&#8217;, use Enable-Migrations -ContextTypeName LocalIssuesWeb.Models.ApplicationDbContext.</strong></span>  
<span style="color: #ff0000;"><strong> To enable migrations for &#8216;LocalIssuesWeb.DAL.LocalIssuesContext&#8217;, use Enable-Migrations -ContextTypeName LocalIssuesWeb.DAL.LocalIssuesContext</strong></span>.  
[<img class="alignnone wp-image-3761 size-large" src="https://i1.wp.com/blog.sharechiwai.com/wp-content/uploads/2016/10/MoreThanOneContextFound.png?resize=625%2C159" alt="More than one context type was found in the assembly" width="625" height="159" srcset="https://i1.wp.com/blog.sharechiwai.com/wp-content/uploads/2016/10/MoreThanOneContextFound.png?resize=1024%2C261 1024w, https://i1.wp.com/blog.sharechiwai.com/wp-content/uploads/2016/10/MoreThanOneContextFound.png?resize=300%2C76 300w, https://i1.wp.com/blog.sharechiwai.com/wp-content/uploads/2016/10/MoreThanOneContextFound.png?resize=768%2C196 768w, https://i1.wp.com/blog.sharechiwai.com/wp-content/uploads/2016/10/MoreThanOneContextFound.png?resize=624%2C159 624w, https://i1.wp.com/blog.sharechiwai.com/wp-content/uploads/2016/10/MoreThanOneContextFound.png?w=1464 1464w, https://i1.wp.com/blog.sharechiwai.com/wp-content/uploads/2016/10/MoreThanOneContextFound.png?w=1250 1250w" sizes="(max-width: 625px) 100vw, 625px" data-recalc-dims="1" />](https://i1.wp.com/blog.sharechiwai.com/wp-content/uploads/2016/10/MoreThanOneContextFound.png)

做了一會research之後發現是由於 **ASP.Net Identity** 的 **ApplicationDbContext**和我自己定義給這個project的 **Database Context**不同所以出現的

**解決方法**十分簡單  
我們需要分別為 **ASP.Net Identity**的 **ApplicationDbContext**和自己定期的**Database context** 執行**migration**  
e.g.

**Enable migration** for ApplicationDBContext &#8211; create a folder inside migration folder named &#8220;**ApplicationDBContext**&#8221;  
<span style="color: #008000;"><strong>enable-migrations -ContextTypeName</strong></span><span style="color: #3366ff;"><strong> [Context Name]</strong> </span><span style="color: #008000;"><strong>-MigrationsDirectory</strong></span> <span style="color: #ff6600;"><strong>Migrations\[想建立的Context Folder Name]</strong></span>

<pre>enable-migrations -ContextTypeName ApplicationDBContext -MigrationsDirectory Migrations\ApplicationDBContext
</pre>

**<img class="alignnone wp-image-3760 size-large" src="https://i0.wp.com/blog.sharechiwai.com/wp-content/uploads/2016/10/EnabledMIgrationForAppContext.png?resize=625%2C67" alt="More than one context type was found in the assembly " width="625" height="67" srcset="https://i0.wp.com/blog.sharechiwai.com/wp-content/uploads/2016/10/EnabledMIgrationForAppContext.png?resize=1024%2C110 1024w, https://i0.wp.com/blog.sharechiwai.com/wp-content/uploads/2016/10/EnabledMIgrationForAppContext.png?resize=300%2C32 300w, https://i0.wp.com/blog.sharechiwai.com/wp-content/uploads/2016/10/EnabledMIgrationForAppContext.png?resize=768%2C83 768w, https://i0.wp.com/blog.sharechiwai.com/wp-content/uploads/2016/10/EnabledMIgrationForAppContext.png?resize=624%2C67 624w, https://i0.wp.com/blog.sharechiwai.com/wp-content/uploads/2016/10/EnabledMIgrationForAppContext.png?w=1521 1521w, https://i0.wp.com/blog.sharechiwai.com/wp-content/uploads/2016/10/EnabledMIgrationForAppContext.png?w=1250 1250w" sizes="(max-width: 625px) 100vw, 625px" data-recalc-dims="1" /></p> 

[<img class="alignnone size-medium wp-image-3762" src="https://i1.wp.com/blog.sharechiwai.com/wp-content/uploads/2016/10/ApplicationDBContextFolder.png?resize=300%2C86" alt="Entity Framework Migration Folder" width="300" height="86" srcset="https://i1.wp.com/blog.sharechiwai.com/wp-content/uploads/2016/10/ApplicationDBContextFolder.png?resize=300%2C86 300w, https://i1.wp.com/blog.sharechiwai.com/wp-content/uploads/2016/10/ApplicationDBContextFolder.png?w=477 477w" sizes="(max-width: 300px) 100vw, 300px" data-recalc-dims="1" />](https://i1.wp.com/blog.sharechiwai.com/wp-content/uploads/2016/10/ApplicationDBContextFolder.png)  
add-migration</strong>  
**<span style="color: #008000;">add-migration</span> &#8211;<span style="color: #008000;">ConfigurationTypeName </span><span style="color: #3366ff;">[Namespace e.g. LocalIssuesWeb.Migrations.ApplicationDBContext].Configuration</span> &#8220;<span style="color: #ff6600;">Init user database</span>&#8220;**

<pre>add-migration -ConfigurationTypeName LocalIssuesWeb.Migrations.ApplicationDBContext.Configuration "Init user database"
</pre>

**[<img class="alignnone wp-image-3763 size-large" src="https://i1.wp.com/blog.sharechiwai.com/wp-content/uploads/2016/10/addMiigrationAppContext.png?resize=625%2C115" alt="Add Migration" width="625" height="115" srcset="https://i1.wp.com/blog.sharechiwai.com/wp-content/uploads/2016/10/addMiigrationAppContext.png?resize=1024%2C189 1024w, https://i1.wp.com/blog.sharechiwai.com/wp-content/uploads/2016/10/addMiigrationAppContext.png?resize=300%2C55 300w, https://i1.wp.com/blog.sharechiwai.com/wp-content/uploads/2016/10/addMiigrationAppContext.png?resize=768%2C142 768w, https://i1.wp.com/blog.sharechiwai.com/wp-content/uploads/2016/10/addMiigrationAppContext.png?resize=624%2C115 624w, https://i1.wp.com/blog.sharechiwai.com/wp-content/uploads/2016/10/addMiigrationAppContext.png?w=1558 1558w, https://i1.wp.com/blog.sharechiwai.com/wp-content/uploads/2016/10/addMiigrationAppContext.png?w=1250 1250w" sizes="(max-width: 625px) 100vw, 625px" data-recalc-dims="1" />](https://i1.wp.com/blog.sharechiwai.com/wp-content/uploads/2016/10/addMiigrationAppContext.png)  
Update-database**  
**<span style="color: #008000;">update-database -ConfigurationTypeName</span> <span style="color: #3366ff;">[NameSpace].Configuration</span>**

<pre>update-database -ConfigurationTypeName LocalIssuesWeb.Migrations.ApplicationDBContext.Configuration
</pre>

[<img class="alignnone size-large wp-image-3764" src="https://i2.wp.com/blog.sharechiwai.com/wp-content/uploads/2016/10/updatedatabase_AppContext.png?resize=625%2C93" alt="Update Database" width="625" height="93" srcset="https://i2.wp.com/blog.sharechiwai.com/wp-content/uploads/2016/10/updatedatabase_AppContext.png?resize=1024%2C152 1024w, https://i2.wp.com/blog.sharechiwai.com/wp-content/uploads/2016/10/updatedatabase_AppContext.png?resize=300%2C45 300w, https://i2.wp.com/blog.sharechiwai.com/wp-content/uploads/2016/10/updatedatabase_AppContext.png?resize=768%2C114 768w, https://i2.wp.com/blog.sharechiwai.com/wp-content/uploads/2016/10/updatedatabase_AppContext.png?resize=624%2C93 624w, https://i2.wp.com/blog.sharechiwai.com/wp-content/uploads/2016/10/updatedatabase_AppContext.png?w=1427 1427w, https://i2.wp.com/blog.sharechiwai.com/wp-content/uploads/2016/10/updatedatabase_AppContext.png?w=1250 1250w" sizes="(max-width: 625px) 100vw, 625px" data-recalc-dims="1" />](https://i2.wp.com/blog.sharechiwai.com/wp-content/uploads/2016/10/updatedatabase_AppContext.png)  
現在**ApplicationDBContext**之後我們可以為自己建立的**Database Context進行migration**了  
和之前的指令差不多

<pre>enable-migrations -ContextTypeName LocalIssuesContext -MigrationsDirectory Migrations\LocalIssuesContext
</pre>

**add-migration**

<pre>add-migration -ConfigurationTypeName LocalIssuesWeb.Migrations.LocalIssuesContext.Configuration "Init"
</pre>

**Update-database**

<pre>update-database -ConfigurationTypeName LocalIssuesWeb.Migrations.LocalIssuesContext.Configuration
</pre>

之後每當我們有更改**ASP.Net Identity**的class 時都要執行 **ApplicationDbContext** 的 **Add-Migtration和Update-database**  
然而自己的**Database model更新了便要更新自己的Database context**.

Hope you find it useful