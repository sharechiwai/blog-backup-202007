---
id: 3773
title: 'React Native &#8211; SyntaxError: Use of const in strict mode'
date: 2016-12-01T17:57:39+08:00
author: ShareChiWai
layout: post
guid: http://blog.sharechiwai.com/?p=3773
permalink: /2016/12/react-native-syntaxerror-use-of-const-in-strict-mode/
categories:
  - React Native
tags:
  - React
  - React Native Troubleshooting
---
最近 **React** 十分popular..去了一些Hackathon / 和看 很多 Online 的 Job spec都用了React.  
所以便想花兩天看看難不難學習了

除不知一開始Follow  **React-Native** tutorial 時便出現了 NodeJS的問題..  
<https://facebook.github.io/react-native/docs/getting-started.html>

&#8220;<span style="color: #ff0000;"><strong>SyntaxError: Use of const in strict mode</strong></span>&#8221;  
[<img class="alignnone size-large wp-image-3774" src="https://i2.wp.com/blog.sharechiwai.com/wp-content/uploads/2016/12/UseOfConstInStrictModeReactNatve.png?resize=625%2C186" alt="Use of const in strict mode issue" width="625" height="186" srcset="https://i2.wp.com/blog.sharechiwai.com/wp-content/uploads/2016/12/UseOfConstInStrictModeReactNatve.png?resize=1024%2C304 1024w, https://i2.wp.com/blog.sharechiwai.com/wp-content/uploads/2016/12/UseOfConstInStrictModeReactNatve.png?resize=300%2C89 300w, https://i2.wp.com/blog.sharechiwai.com/wp-content/uploads/2016/12/UseOfConstInStrictModeReactNatve.png?resize=768%2C228 768w, https://i2.wp.com/blog.sharechiwai.com/wp-content/uploads/2016/12/UseOfConstInStrictModeReactNatve.png?resize=624%2C185 624w, https://i2.wp.com/blog.sharechiwai.com/wp-content/uploads/2016/12/UseOfConstInStrictModeReactNatve.png?w=1250 1250w" sizes="(max-width: 625px) 100vw, 625px" data-recalc-dims="1" />](https://i2.wp.com/blog.sharechiwai.com/wp-content/uploads/2016/12/UseOfConstInStrictModeReactNatve.png)

做了一會research之後發現**解決方法**十分簡單..>  
我們只需要更新了**NodeJS** 便可以了  
<img class="alignnone size-large wp-image-3775" src="https://i0.wp.com/blog.sharechiwai.com/wp-content/uploads/2016/12/solved-strict-with-constant-issue.png?resize=625%2C347" alt="Install latest NodeJs to solve Use of const in strict mode issue" width="625" height="347" srcset="https://i0.wp.com/blog.sharechiwai.com/wp-content/uploads/2016/12/solved-strict-with-constant-issue.png?resize=1024%2C568 1024w, https://i0.wp.com/blog.sharechiwai.com/wp-content/uploads/2016/12/solved-strict-with-constant-issue.png?resize=300%2C167 300w, https://i0.wp.com/blog.sharechiwai.com/wp-content/uploads/2016/12/solved-strict-with-constant-issue.png?resize=768%2C426 768w, https://i0.wp.com/blog.sharechiwai.com/wp-content/uploads/2016/12/solved-strict-with-constant-issue.png?resize=624%2C346 624w, https://i0.wp.com/blog.sharechiwai.com/wp-content/uploads/2016/12/solved-strict-with-constant-issue.png?w=1250 1250w" sizes="(max-width: 625px) 100vw, 625px" data-recalc-dims="1" /> 

Hope you find it useful