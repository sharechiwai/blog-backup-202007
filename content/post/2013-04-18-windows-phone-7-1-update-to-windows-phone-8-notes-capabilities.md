---
id: 2767
title: 'Windows Phone 7.1 Update to Windows Phone 8 Notes &#8211; Capabilities'
date: 2013-04-18T00:00:56+08:00
author: ShareChiWai
layout: post
guid: http://blog.sharechiwai.com/?p=2767
permalink: /2013/04/windows-phone-7-1-update-to-windows-phone-8-notes-capabilities/
categories:
  - Window Phone Development
---
在寫**Windows Phone 8** 時 有關程式可能要設定 這個程式要有什麼權限..  
或安裝這個手機程式要什麼硬件要求都需要在[**WMAppManifest.xml**] 修改**XML**的&#8230;  
[<img class="alignnone size-full wp-image-2772" alt="Windows Phone WMAppManifest.xml Settings " src="https://i1.wp.com/blog.sharechiwai.com/wp-content/uploads/2013/05/WMAppMainiFest.png?resize=534%2C187" width="534" height="187" data-recalc-dims="1" />](https://i1.wp.com/blog.sharechiwai.com/wp-content/uploads/2013/05/WMAppMainiFest.png)

**Windows Phone 8** 的**SDK** 已經改進了  
大家可以在**Visual Studio**上的介面上修改.. 十分方便&#8230;

**解決方法**:  
在**Solution Explorer** 上 ..  
開始 Windows Phone Project上的 &#8220;**Properties** / **內容**&#8221; 資料夾  
開啟 &#8220;**WMAppManifest.xml**&#8221; 檔案..之後便會看到和這個**Windows Phone Project** 相關的資訊可以給大家修改  
**例如**:  
**Application UI**  
&#8211; 用來設定這個Windows Phone App的顯示資訊.. E,G, Application Icon, 支援的介紹大小, Tile 和 Tile 圖片  
[<img class="alignnone size-full wp-image-2768" alt="Windows Phone WMAppManifest.xml Settings - Application UI" src="https://i2.wp.com/blog.sharechiwai.com/wp-content/uploads/2013/05/WPAppUI.png?resize=625%2C388" width="625" height="388" data-recalc-dims="1" />](https://i2.wp.com/blog.sharechiwai.com/wp-content/uploads/2013/05/WPAppUI.png)  
**Capabilities**  
&#8211; 設定 介紹給使用者&#8230;這一個程式需要用到手機上的那些功能的資訊  
[<img class="alignnone size-full wp-image-2769" alt="Windows Phone WMAppManifest.xml Settings - Capabilities" src="https://i0.wp.com/blog.sharechiwai.com/wp-content/uploads/2013/05/WPCapabilities.png?resize=625%2C554" width="625" height="554" data-recalc-dims="1" />](https://i0.wp.com/blog.sharechiwai.com/wp-content/uploads/2013/05/WPCapabilities.png)

**Requirements**  
&#8211; 設定手機上有那些硬體要求..才可以安裝這個程式的資訊  
[<img class="alignnone size-full wp-image-2770" alt="Windows Phone WMAppManifest.xml Settings - Requirement" src="https://i0.wp.com/blog.sharechiwai.com/wp-content/uploads/2013/05/WPRequirement.png?resize=625%2C286" width="625" height="286" data-recalc-dims="1" />](https://i0.wp.com/blog.sharechiwai.com/wp-content/uploads/2013/05/WPRequirement.png)  
**Packaging**  
&#8211; 設定這個程式的 Packaging Information  
[<img class="alignnone size-full wp-image-2771" alt="Windows Phone WMAppManifest.xml Settings - Packaging" src="https://i2.wp.com/blog.sharechiwai.com/wp-content/uploads/2013/05/WPPackaging.png?resize=625%2C483" width="625" height="483" data-recalc-dims="1" />](https://i2.wp.com/blog.sharechiwai.com/wp-content/uploads/2013/05/WPPackaging.png)

Hope you find it useful