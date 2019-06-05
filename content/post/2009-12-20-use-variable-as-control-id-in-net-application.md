---
id: 347
title: Use variable as Control ID in .Net Application
date: 2009-12-20T12:20:00+08:00
author: ShareChiWai
layout: post
guid: http://sharechiwai.wordpress.com/2009/12/20/use-variable-as-control-id-in-net-application
permalink: /2009/12/use-variable-as-control-id-in-net-application/
blogger_blog:
  - sharechiwai.blogspot.com
blogger_author:
  - 智/Chi
blogger_242190872ae71f6d0f1f8731ec21ccf3_permalink:
  - "4103058077985160532"
categories:
  - .Net Tips And Tricks
---
<div style="margin:0;">
  E.g. You have a a lot of checkbox, which you have used similar name for it. E.g. (CheckBox1, CheckBox2, CheckBox3).
</div>

<div style="margin:0;">
</div>

<div style="margin:0;">
  Last week my friend has asked if it is possible to convert a string to an Object. My first though is yes. It is quite simple and straight forward.
</div>

<div style="margin:0;">
</div>

<div style="margin:0;">
  Instead of using
</div>

<div style="margin:0;">
  string t = &#8220;&#8221;;
</div>

<div style="margin:0;">
  What you need to do is to assign a string as:
</div>

<div style="margin:0;">
  String t = &#8220;value&#8221;;
</div>

<div style="margin:0;">
</div>

<div style="margin:0;">
  Actually, that is not what he wants. HaHa. What he want to do is convert a string which is retrieved from a DataTable into a TextBox. Because my brain was on Holiday last few days. I think it is not simple to convert a string into an Obejct (Control). And also, I do not think you can do Array of Object like what you can do in VB6. E.g. You can Name a object with a bracket. Cannot remember it is [] or (). E.g. CheckBoxSample()..etc.
</div>

<div style="margin:0;">
</div>

<div style="margin:0;">
  My brain seems to work again today. I have worked out the solution to deal with it.
</div>

<div style="margin:0;">
</div>

<div style="margin:0;">
  In this example I am going to use DataTable, which has 2 columns &#8220;ControlID&#8221; and &#8220;CheckBoxValue&#8221;
</div>

<div style="margin:0;">
  I&#8217;ve Add a GroupBox named &#8220;gb_Container&#8221;, and create 10 CheckBoxes.
</div>

<div style="margin:0;">
  That all use the default name. E.g. CheckBox1 to CheckBox10.
</div>

<div style="margin:0;">
  Also I have create a Button to trigger the event.
</div>

<div style="margin:0;">
</div>

<div style="margin:0;">
  The solution seems quite simple.
</div>

<div style="margin:0;">
</div>

<div style="margin:0;">
  1) If you have read my previous post. You already know I prefer to use GroupBox or Panel as a container to group the controls together. It makes it easier to manage (From my point of view)
</div>

<div style="margin:0;">
</div>

<div style="margin:0;">
  2) Drag and name the controls into the Group Box. (Make sure the name of the Control is the same as the one on the Database or Array.)
</div>

<div style="margin:0;">
</div>

<div style="margin:0;">
  3) After you retreive the value (Control ID) variable which stored on the DataTable.
</div>

<div style="margin:0;">
  What you need to do is to convert it to string.
</div>

<div style="margin:0;">
</div>

<div style="margin:0;">
  4) Then you can create a CheckBox variable, and use the Control Properties from the Group Box to retrieve the Control from the variable. After that you assign this control into the CheckBox Variable that you just created.
</div>

<div style="margin:0;">
</div>

<div style="margin:0;">
  // CheckBox cb = (CheckBox) gb_Container.Control[&#8220;&#8221;]
</div>

<div style="margin:0;">
</div>

<div style="margin:0;">
  5) To ensure the control does exist. You may want to use an If statement to check if it is null.
</div>

<div style="margin:0;">
</div>

<div style="margin:0;">
  6) If it is not null, which mean it has assigned the control to the variable. Then you can just do whatever you like to do. E.g.
</div>

<div style="margin:0;">
  cb.Checked = (bool) tbl.Rows[RowID][CheckedValue]
</div>

<div style="margin:0;">
</div>

<div style="margin:0;">
  Here it is the sample code in VB.NET
</div>

<div style="margin:0;">
</div>

<div style="margin:0;">
  <span style="color:green;">&#8216;Step 1 retrive DataTable<br />For i As Integer = 0 To tbl.Rows.Count &#8211; 1<br />&#8216;Assign valur from DataTable field into string<br />Dim cbControlID As String = tbl.Rows(i)(&#8220;ControlID&#8221;)<br />&#8216;Assign the control to check box<br />Dim cbObject As CheckBox = DirectCast(groupBox1.Controls(cbControlID), CheckBox)<br />&#8216;Check if the checkBox exist from the groupBox1.Controls Statement<br />If cbObject IsNot Nothing Then<br />&#8216;Assign the value into the CheckBox<br />cbObject.Checked = CBool(tbl.Rows(i)(&#8220;CheckBoxValue&#8221;))<br />End If<br />Next<br /></span>
</div>

<div style="margin:0;">
</div>

<div style="margin:0;">
  Here it is the sample code in C#
</div>

<div style="margin:0;">
  /<span style="color:green;">/Step 1 retrive DataTable<br />for (int i = 0; i<tbl.Rows.Count; i++){<br />//Assign valur from DataTable field into string<br />string cbControlID = tbl.Rows[i][&#8220;ControlID&#8221;];<br />//Assign the control to check box<br />CheckBox cbObject = (CheckBox) groupBox1.Controls[cbControlID ];<br />//Check if the checkBox exist from the groupBox1.Controls Statement<br />if (cbObject != null)<br />{<br />//Assign the value into the CheckBox<br />cbObject.Checked = (bool) tbl.Rows[i][&#8220;CheckBoxValue&#8221;];<br />}<br />}</span>
</div>

<div style="margin:0;">
</div>

<div style="margin:0;">
  I knew the wording of this tricks and tips is crap, Hope you can still understand and find this post useful.
</div>