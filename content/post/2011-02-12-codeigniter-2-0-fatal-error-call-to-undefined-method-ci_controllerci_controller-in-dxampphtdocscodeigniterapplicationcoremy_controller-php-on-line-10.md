---
id: 1264
title: 'CodeIgniter 2.0 Fatal error: Call to undefined method CI_Controller::CI_Controller() in D:xampphtdocsCodeIgniterapplicationcoreMY_Controller.php on line 10'
date: 2011-02-12T00:00:52+08:00
author: ShareChiWai
layout: post
guid: http://oldblog.sharechiwai.com/?p=1264
permalink: /2011/02/codeigniter-2-0-fatal-error-call-to-undefined-method-ci_controllerci_controller-in-dxampphtdocscodeigniterapplicationcoremy_controller-php-on-line-10/
categories:
  - Codeingter
---
今日嘗試在**Codengiter**  
寫一個override class去 replace 原有的 **Controller Class** 時出現了這個錯誤&#8230;

[<img class="alignnone" title="Call to undefined method CI_Controller::CI_Controller() " src="https://i1.wp.com/farm6.static.flickr.com/5179/5440772847_bd78c0802f.jpg?resize=500%2C246" alt="Call to undefined method CI_Controller::CI_Controller() " width="500" height="246" data-recalc-dims="1" />](https://i1.wp.com/farm6.static.flickr.com/5179/5440772847_bd78c0802f.jpg)  
&#8220;<span style="color: #ff0000;"><strong>Fatal error: Call to undefined method CI_Controller::CI_Controller() in D:xampphtdocsCodeIgniterapplicationcoreMY_Controller.php on line 10</strong></span>&#8221;

我已經檢查了&#8230;我這個Override class [**My_Controller**] 已經放中了正確的資料來內&#8230;  
**D:xampphtdocsCodeIgniterapplicationcoreMY_Controller.php**

最後發現原來我忘了 overload **__construct** 這個method&#8230;加了以下的code 便可&#8230;

[php]  
function __construct() {  
parent::__construct();  
}  
[/php]

在這個Class 入面的Code 變成了

[php]  
<?php  
class MY\_Controller extends CI\_Controller {

function __construct() {  
parent::__construct();  
}

function MY_Controller()  
{  
parent::CI_Controller();

}  
}  
[/php]

Hope you find it useful