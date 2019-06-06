---
id: 3838
title: Atom Terminal Plugin
date: 2017-02-20T07:10:53+08:00
author: ShareChiWai
layout: post
guid: http://blog.sharechiwai.com/?p=3838
permalink: /2017/02/atom-terminal-plugin/
categories:
  - 工作經驗/體驗/工作心得分享
tags:
  - Atom
  - Atom Plugins
  - IDE
  - Visual Studio Code
  - VSCode
---
最近多數做Web Front End 相關的工作  
所以 **IDE** 主要也是用**Text Editor**  
暫時還沒有決定好那一個**Text Editor** 比較好用  
**Visual Studio Code** 還是**Atom**

**VS Code**的好處是有**Built-in**的 **Terminal** ,  十分好用  
可以在同一個**VS Code Instance** 上執行多個**powershell** / **command prompt**  
但是個的版面分割(**split**) 功能就只可以分 &#8220;**上,下**&#8221; 或 &#8220;**左,右**&#8221; 有點美中不足  
[<img class="alignnone size-large wp-image-3879" src="https://i2.wp.com/blog.sharechiwai.com/wp-content/uploads/2017/02/vsCodeSplitScreen.png?resize=625%2C380" alt="Visual Studio Code Split Screen" width="625" height="380" srcset="https://i2.wp.com/blog.sharechiwai.com/wp-content/uploads/2017/02/vsCodeSplitScreen.png?resize=1024%2C623 1024w, https://i2.wp.com/blog.sharechiwai.com/wp-content/uploads/2017/02/vsCodeSplitScreen.png?resize=300%2C183 300w, https://i2.wp.com/blog.sharechiwai.com/wp-content/uploads/2017/02/vsCodeSplitScreen.png?resize=768%2C467 768w, https://i2.wp.com/blog.sharechiwai.com/wp-content/uploads/2017/02/vsCodeSplitScreen.png?resize=624%2C380 624w, https://i2.wp.com/blog.sharechiwai.com/wp-content/uploads/2017/02/vsCodeSplitScreen.png?w=1250 1250w, https://i2.wp.com/blog.sharechiwai.com/wp-content/uploads/2017/02/vsCodeSplitScreen.png?w=1875 1875w" sizes="(max-width: 625px) 100vw, 625px" data-recalc-dims="1" />](https://i2.wp.com/blog.sharechiwai.com/wp-content/uploads/2017/02/vsCodeSplitScreen.png)  
有時候想上下左右一起分割..但是不能了

還有由於暫時還沒有找到一個比較好用的**Code formatter plugin**..所以轉用了**Atom**

**Atom** 可以任你分頁。。還有他的**Atom-beautifier** 也十分好用。。為一一個大問題是。。**IDE** 有時會not respond..

繼續講 **Terminal plugin for Atom**

在網上安裝了幾個 **Terminal** / **Command Prompt**的**Atom Plugin**都不如理想  
安裝了 但是執行不到&#8230; 只有一個黑色的**Terminal** 畫面

最後終於找到了一個十分好用，可靠的**plugin** 了  
他就是&#8221;**platformio-ide-terminal**&#8221;  
<https://atom.io/packages/platformio-ide-terminal>  
[<img class="alignnone size-large wp-image-3871" src="https://i0.wp.com/blog.sharechiwai.com/wp-content/uploads/2017/02/platformio-ide-terminal.png?resize=625%2C292" alt="platformio-ide-terminal" width="625" height="292" srcset="https://i0.wp.com/blog.sharechiwai.com/wp-content/uploads/2017/02/platformio-ide-terminal.png?resize=1024%2C478 1024w, https://i0.wp.com/blog.sharechiwai.com/wp-content/uploads/2017/02/platformio-ide-terminal.png?resize=300%2C140 300w, https://i0.wp.com/blog.sharechiwai.com/wp-content/uploads/2017/02/platformio-ide-terminal.png?resize=768%2C358 768w, https://i0.wp.com/blog.sharechiwai.com/wp-content/uploads/2017/02/platformio-ide-terminal.png?resize=624%2C291 624w, https://i0.wp.com/blog.sharechiwai.com/wp-content/uploads/2017/02/platformio-ide-terminal.png?w=1250 1250w, https://i0.wp.com/blog.sharechiwai.com/wp-content/uploads/2017/02/platformio-ide-terminal.png?w=1875 1875w" sizes="(max-width: 625px) 100vw, 625px" data-recalc-dims="1" />](https://i0.wp.com/blog.sharechiwai.com/wp-content/uploads/2017/02/platformio-ide-terminal.png)

和**VScode** 差不多  
[<img class="alignnone size-large wp-image-3872" src="https://i0.wp.com/blog.sharechiwai.com/wp-content/uploads/2017/02/Terminal-panel.png?resize=625%2C252" alt="Atom Terminal panel" width="625" height="252" srcset="https://i0.wp.com/blog.sharechiwai.com/wp-content/uploads/2017/02/Terminal-panel.png?resize=1024%2C413 1024w, https://i0.wp.com/blog.sharechiwai.com/wp-content/uploads/2017/02/Terminal-panel.png?resize=300%2C121 300w, https://i0.wp.com/blog.sharechiwai.com/wp-content/uploads/2017/02/Terminal-panel.png?resize=768%2C310 768w, https://i0.wp.com/blog.sharechiwai.com/wp-content/uploads/2017/02/Terminal-panel.png?resize=624%2C252 624w, https://i0.wp.com/blog.sharechiwai.com/wp-content/uploads/2017/02/Terminal-panel.png?w=1250 1250w" sizes="(max-width: 625px) 100vw, 625px" data-recalc-dims="1" />](https://i0.wp.com/blog.sharechiwai.com/wp-content/uploads/2017/02/Terminal-panel.png)  
Hope you find it useful