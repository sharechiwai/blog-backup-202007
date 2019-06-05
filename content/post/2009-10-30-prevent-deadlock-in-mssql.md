---
id: 348
title: Prevent Deadlock in MSSQL
date: 2009-10-30T22:30:00+08:00
author: ShareChiWai
layout: post
guid: http://sharechiwai.wordpress.com/2009/10/30/prevent-deadlock-in-mssql
permalink: /2009/10/prevent-deadlock-in-mssql/
blogger_blog:
  - sharechiwai.blogspot.com
blogger_author:
  - 智/Chi
blogger_242190872ae71f6d0f1f8731ec21ccf3_permalink:
  - "5649735701552134794"
categories:
  - MSSQL Tips and Tricks
---
I am having several problems on the application that I developed a year ago.

I need to process about 200,000 records from one database to another. The process also needs to delete and re-compute the statistic on the data then insert back to the database. It will have lots of IO/ Delete/Insert actions.

When the process started to run. It used up about 70% of CPU on the database server, and sometime it create deadlock on the database. = (

I have sent the deadlock problem to the DBA. He helped me to investigate about the problem. The way that I construct the query is fine.

At the end, he found that I have not created any index on the table that I do a lot of Delete and Insert. He thinks that is where it causes the error. We applied the index to the table. It seems to work fine again.

If you have deadlock on your database, I guess you can try to create index for the table which cause deadlock. Hope your find it useful.