---
id: 1281
title: 'Fatal error: Call to undefined method CI_Model::CI_Model() in D:xampphtdocscodeigniterapplicationcoreMY_Model.php on line 8'
date: 2011-02-13T00:00:22+08:00
author: ShareChiWai
layout: post
guid: http://oldblog.sharechiwai.com/?p=1281
permalink: /2011/02/fatal-error-call-to-undefined-method-ci_modelci_model-in-dxampphtdocscodeigniterapplicationcoremy_model-php-on-line-8/
categories:
  - Codeingter
---
又遇到另一個問題了&#8230;  
我嘗試 extends **CI_Model** 這一個**Class**  
把一些在**model** 上 經常用到的 功能放在這裡&#8230;  
但是又出現了這個問題  
[<img class="alignnone" title="Fatal error: Call to undefined method CI_Model::CI_Model()" src="https://i1.wp.com/farm5.static.flickr.com/4104/5441669281_c788042422.jpg?resize=500%2C246" alt="Fatal error: Call to undefined method CI_Model::CI_Model()" width="500" height="246" data-recalc-dims="1" />](https://i1.wp.com/farm5.static.flickr.com/4104/5441669281_c788042422.jpg)

&#8220;<span style="color: #ff0000;"><strong>Fatal error: Call to undefined method CI_Model::CI_Model() in D:xampphtdocscodeigniterapplicationcoreMY_Model.php on line 8</strong></span>&#8221;

[php]  
class MY\_Model extends CI\_Model  
{

function MY_Model()  
{  
parent::CI_Model();  
}

}  
[/php]

之後終於找到了**解決方法**  
只要除去 **parent::CI_Model();** 便可

[php]  
class MY\_Model extends CI\_Model  
{

function MY_Model()  
{

}  
}  
[/php]

真是要好好學習Codeigniter 才可&#8230;  
不可以再犯這些錯&#8230;

Hope you find it useful.