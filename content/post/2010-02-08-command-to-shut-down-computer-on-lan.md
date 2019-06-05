---
id: 321
title: Command to shut down computer on LAN.
date: 2010-02-08T02:08:00+08:00
author: ShareChiWai
layout: post
guid: http://sharechiwai.wordpress.com/2010/02/08/command-to-shut-down-computer-on-lan
permalink: /2010/02/command-to-shut-down-computer-on-lan/
blogger_blog:
  - sharechiwai.blogspot.com
blogger_author:
  - 智/Chi
blogger_242190872ae71f6d0f1f8731ec21ccf3_permalink:
  - "3906684704520866697"
categories:
  - 電腦小貼事 Computing Tips and Tricks
---
<div>
  Today, I find a command on Windows to trick my friend at work. What I did is to run a command to pretend to shut down his machines over the network.
</div>

<div>
</div>

<div>
  Here it is the command: 
</div>

<div>
  <span style="background-color:white;color:red;">>>></span><b>shutdown /s</b><span style="background-color:white;color:red;"> </span><b>/t </b><span style="background-color:white;color:red;">300 </span><b>/m</b><span style="background-color:white;color:red;"> \ComputerName </span><b>/c</b><span style="background-color:white;color:red;"> &#8220;Comment about what is happening&#8221;</span><br style="color:red;" /><br />The command above will Shut down the computer named &#8220;ComputerName&#8221; in 300 second [which is 5mins] and it will display a message on the screen saying &#8220;Comment about what is happening&#8221;. i.e.<b> shutdown /s[as action] /t [time in second] /m [\MachineName] /c [Comment]</b></p> 
  
  <p>
    If you would like the restart the computer rather than shut down the computer you can change &#8220;<b>/s</b>&#8221; to &#8220;<b>/r</b>&#8220;<br />As I just pretend to shutdown his computer I did cancel the shutdown command remotely.</div> 
    
    <div>
      To rescuse it what you need to do is run a command to abort the shut down.
    </div>
    
    <div style="color:red;">
      <b>> shutdown -a /m \ComputerName</b>
    </div>
    
    <div>
      -a = abort shut down
    </div>
    
    <div>
    </div>
    
    <div>
      You can make use of this command when you need to remote shutdown/restart computer when you need to, without having to go to each of the machine individually to shutdown/restart the machines.
    </div>
    
    <div>
    </div>
    
    <div>
      Have fun.
    </div>