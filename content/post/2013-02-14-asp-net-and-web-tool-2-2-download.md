---
id: 2628
title: ASP.Net and Web Tool 2.2 Download
date: 2013-02-14T00:00:51+08:00
author: ShareChiWai
layout: post
guid: http://blog.sharechiwai.com/?p=2628
permalink: /2013/02/asp-net-and-web-tool-2-2-download/
categories:
  - ASP.Net MVC
tags:
  - Visual Studio 2012
---
**ASP.Net and Web Tool 2.2** 終於Release 了

大家可以到以下網址下載/安裝  
<a title="Download ASP.Net and Web Tool 2.2" href="http://go.microsoft.com/fwlink/?LinkID=275131" target="_blank"><span style="line-height: 1.714285714; font-size: 1rem;">http://go.microsoft.com/fwlink/?LinkID=275131</span></a>

**新功能包括:**

> ### Tooling
> 
>   * Page Inspector 
>       * Support JavaScript selection mapping allowing Page Inspector to map items that were dynamically added to the page back to the corresponding JavaScript code.
>       * The ability to see CSS updates in real-time.
>       * For more information, read [CSS Auto-Sync and JavaScript Selection Mapping in Page Inspector](http://blogs.msdn.com/b/webdev/archive/2012/12/14/css-auto-sync-and-javascript-selection-mapping-in-page-inspector.aspx).
>   * Editor 
>       * Support syntax highlighting for CoffeeScript, Mustache, Handlebars, and JsRender.
>       * The HTML editor provides Intellisense for Knockout bindings.
>       * LESS editing and compiler support to enable building dynamic CSS using LESS.
>       * Paste JSON as a .NET class. Using this Special Paste command to paste JSON into a C# or VB.NET code file, and Visual Studio will automatically generate .NET classes inferred from the JSON.
>   * Mobile Emulator support adds extensibility hooks so that third-party emulators can be installed as a VSIX. The installed emulators will show up in the F5 dropdown, so that developers can preview their websites on a variety of mobile devices. Read more about this feature in Scott Hanselman’s blog entry on [the new BrowserStack integration with Visual Studio](http://www.hanselman.com/blog/CrossBrowserDebuggingIntegratedIntoVisualStudioWithBrowserStack.aspx).
> 
> ### Web Publishing
> 
>   * Web site projects now have the same publishing experience as Web Application projects including publishing to Windows Azure Web Sites.
>   * Selective publish – for one or more files you can perform the following actions (after publishing to a Web Deploy endpoint): 
>       * Publish selected files.
>       * See the difference between a local file and a remote file.
>       * Update the local file with the remote file or update the remote file with the local file.
> 
> ### ASP.NET MVC Templates
> 
>   * The new Facebook Application template makes writing Facebook Canvas applications easy. In a few simple steps, you can create a Facebook application that gets data from a logged in user and integrates with their friends. The template includes a new library to take care of all the plumbing involved in building a Facebook app, including authentication, permissions, accessing Facebook data and more. For more information on using the Facebook Application template see <http://go.microsoft.com/fwlink/?LinkID=269921>.
>   * A new Single Page Application MVC template allows developers to build interactive client-side web apps using HTML 5, CSS 3, and the popular Knockout and jQuery JavaScript libraries, on top of ASP.NET Web API. The template includes a “todo” list application that demonstrates common practices for building a JavaScript HTML5 application that uses a RESTful server API. You can read more at <http://www.asp.net/single-page-application>.
>   * You can now create a VSIX that adds new templates to the ASP.NET MVC New Project dialog. Learn how here:<http://go.microsoft.com/fwlink/?LinkId=275019>
>   * FixedDisplayModes package – MVC project templates have been updated to include the new ‘FixedDisplayModes’ NuGet package, which contains a workaround for a bug in MVC 4. For more information on the fix contained in the package, refer to this blog post (<http://blogs.msdn.com/b/rickandy/archive/2012/09/17/asp-net-mvc-4-mobile-caching-bug-fixed.aspx>) from the MVC team.
> 
> ### ASP.NET Web API
> 
> ASP.NET Web API has been enhanced with several new features:
> 
>   * ASP.NET Web API OData
>   * ASP.NET Web API Tracing
>   * ASP.NET Web API Help Page
> 
> #### ASP.NET Web API OData
> 
> ASP.NET Web API OData gives you the flexibility you need to build OData endpoints with rich business logic over any data source. With ASP.NET Web API OData you control the amount of OData semantics that you want to expose. ASP.NET Web API OData is included with the ASP.NET MVC 4 project templates and is also available from NuGet (<http://www.nuget.org/packages/microsoft.aspnet.webapi.odata>).
> 
> ASP.NET Web API OData currently supports the following features:
> 
>   * Enable OData query semantics by applying the [Queryable] attribute.
>   * Easily validate OData queries and restrict the set of supported query options, operators and functions.
>   * Parameter bind to ODataQueryOptions directly to get an abstract syntax tree representation of the query that can then be validated and applied to an IQueryable or IEnumerable.
>   * Enable service-driven paging and next page link generation by specifying result limits on [Queryable] attribute.
>   * Request an inlined count of the total number of matching resources using $inlinecount.
>   * Control null propagation.
>   * Any/All operators in $filter.
>   * Infer an entity data model by convention or explicitly customize a model in a manner similar to Entity Framework Code-First.
>   * Expose entity sets by deriving from EntitySetController.
>   * Simple, customizable conventions for exposing navigation properties, manipulating links and implementing OData actions.
>   * Simplified routing using the MapODataRoute extension method.
>   * Support for versioning by exposing multiple EDM models.
>   * Expose service document and $metadata so you can generate clients (.NET, Windows Phone, Windows Store, etc.) for your Web API.
>   * Support for the OData Atom, JSON, and JSON verbose formats.
>   * Create, update, partially update (PATCH) and delete entities.
>   * Query and manipulate relationships between entities.
>   * Create relationship links that wire up to your routes.
>   * Complex types.
>   * Entity Type Inheritance.
>   * Collection properties.
>   * Enums.
>   * OData actions.
>   * Built upon the same foundation as WCF Data Services, namely ODataLib (<http://www.nuget.org/packages/microsoft.data.odata>).
> 
> For more information on ASP.NET Web API OData see <http://go.microsoft.com/fwlink/?LinkId=271141>.
> 
> #### ASP.NET Web API Tracing
> 
> ASP.NET Web API Tracing integrates tracing data from your web APIs with .NET Tracing. It is now enabled by default in the Web API project template. Tracing data for your web APIs is sent to the Output window and is made available through IntelliTrace. ASP.NET Web API Tracing enables you to trace information about your Web API when hosted on Windows Azure through integration with [Windows Azure Diagnostics](http://msdn.microsoft.com/en-us/library/windowsazure/hh411529.aspx). You can also install and enable ASP.NET Web API Tracing in any application using the ASP.NET Web API Tracing NuGet package (<http://www.nuget.org/packages/microsoft.aspnet.webapi.tracing>).
> 
> For more information on configuring and using ASP.NET Web API Tracing see <http://go.microsoft.com/fwlink/?LinkID=269874>.
> 
> #### ASP.NET Web API Help Page
> 
> The ASP.NET Web API Help Page is now included by default in the Web API project template. The ASP.NET Web API Help Page automatically generates documentation for web APIs including the HTTP endpoints, the supported HTTP methods, parameters and example request and response message payloads. Documentation is automatically pulled from comments in your code. You can also add the ASP.NET Web API Help Page to any application using the ASP.NET Web API Help Page NuGet package (<http://www.nuget.org/packages/microsoft.aspnet.webapi.helppage>).
> 
> For more information on setting up and customizing the ASP.NET Web API Help Page see<http://go.microsoft.com/fwlink/?LinkId=271140>.
> 
> ### ASP.NET SignalR
> 
> ASP.NET SignalR makes it simple to add real-time web capabilities to your ASP.NET application, using WebSockets if available and automatically falling back to other techniques when it isn’t.
> 
> For more information on using ASP.NET SignalR see <http://go.microsoft.com/fwlink/?LinkId=271271>.
> 
> ### ASP.NET Friendly URLs
> 
> ASP.NET FriendlyURLs makes it very easy for web forms developers to generate cleaner looking URLs(without the .aspx extension). It requires little to no configuration and can be used with existing ASP.NET v4.0 applications. The FriendlyURLs feature also makes it easier for developers to add mobile support to their applications, by supporting switching between desktop and mobile views.
> 
> For more information on installing and using ASP.NET Friendly URLs see[http://www.hanselman.com/blog/IntroducingASPNETFriendlyUrlsCleanerURLsEasierRoutingAndMobileViewsForASPNET](http://www.hanselman.com/blog/IntroducingASPNETFriendlyUrlsCleanerURLsEasierRoutingAndMobileViewsForASPNETWebForms.aspx)

有關新功能可以到以下URL 參考

<http://www.asp.net/vnext/overview/fall-2012-update/aspnet-and-web-tools-20122-release-notes-rtw>

Hope you find it useful