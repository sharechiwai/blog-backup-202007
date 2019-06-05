---
id: 2189
title: Assign Enum to ComboBox / Drop Down List
date: 2011-11-16T00:00:55+08:00
author: ShareChiWai
layout: post
guid: http://blog.sharechiwai.com/?p=2189
permalink: /2011/11/assign-enum-to-combobox-drop-down-list/
categories:
  - .Net Tips And Tricks
---
今天繼續學習**WPF**  
突然間想到在這個程式中 我需要用到一個**ComboBox**, 給用戶選擇會一些設定  
由於不想每次開啟程式時都要到資料庫取資料..  
所以便想到用**Enum** 了..

因為之前沒有用過這個方法既關係..  
在開始時也不知怎樣可以把**Enum** 轉成一個**Data Source**放在 **ComboBox**上使用

經過一段時間的research 終於明白了

**解決方法**:  
首先我建立了一個**Class** &#8220;**GlobalSettings**&#8221; 用來放一些 **Global**的code的  
之後在這裡寫我們的**Enum**

[csharp]  
//我的Enum 名是 ApplicationNames..  
//我沒有用Enum的Default value..而自己設定了每一個Enum入面的 選擇的Value  
//E.G. 當大家選擇 ShareChiWaiWeb 時他的數值會是 1  
//而選擇 LLuckyDip = 3  
//如果我們不設定 LLuckyDip = 3 時他們的值便會是自動遞增的..  
//E.g, ShareChiWaiWeb = 1 LLuckyDip = 2&#8230;etc  
public enum ApplicationNames { ShareChiWaiWeb = 1, LLuckyDip = 3 , LLuckyStick = 5 , LGeoIpInfo = 7, Damn = 9, DYVO = 11 }  
[/csharp]

之後我們在程式上寫**Assign** 我們的**Enum** 到**ComboBox**的**DataSource**上

[csharp]  
//我們可以使用Enum.GetValues(typeof(EnumVariable)) 來把我們的Enum轉成Array  
//我們可以使用以下的Code來 assign ApplicationNames Enum到 combobox的ItemsSource  
cmb_SampleComboBox.ItemsSource = Enum.GetValues(typeof(GlobalSettings.ApplicationNames));  
[/csharp]

之後執行我們的程式便可以看到 **Enum**的值已經在我們的**ComboBox**上了  
<img src="https://i1.wp.com/api.photoshop.com/v1.0/accounts/aa9037104a014abbb11ad4bd58324b91/assets/1afdab9dd91b4bf8999fde532226d5b1/renditions/fullsize.jpg?resize=530%2C356" width="530" height="356" alt="Enum content has been assigned to Combo Box" data-recalc-dims="1" />  
我們可以使用以下的Code去讀取已選擇的 **ComBoBox** **Item**

[csharp]  
//我會可以定義一個變數 用來儲存 ComBoBox的Selected Item 這個變數的類別需要和我們Enum 的類別一樣的

GlobalSettings.ApplicationNames SelectedValue = (GlobalSettings.ApplicationNames)cmb_SampleComboBox.SelectedItem;  
//我們可以用.ToString的方法輸出 我選擇的Enum的值MessageBox.Show(SelectedValue.ToString());  
//或 Cast了這個 變數為 Int來輸出 這個已選擇的Enum的相對數值  
MessageBox.Show(((int) SelectedValue).ToString());  
[/csharp]

Hope you find it useful