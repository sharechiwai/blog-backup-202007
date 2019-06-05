---
id: 2116
title: '.Net Consume RESTFUL Services &#8211; Make Restful Services Call and Handle JSON reponse'
date: 2011-09-30T00:00:49+08:00
author: ShareChiWai
layout: post
guid: http://blog.sharechiwai.com/?p=2116
permalink: /2011/09/net-make-restful-services-call-and-handle-json-reponse/
categories:
  - .Net Tips And Tricks
tags:
  - API
  - JSON
  - Restful Services
  - WebClient
---
過2星期又有一個**Charity Hack Day**  
所以希望好好用這兩個星期 去好好練習自己的Programming  
很多時候**Hack Day**都是會用到其他公司的**API**  
現在有很多時候都會是使用**RESTFUL services**的&#8230;

今天用的Example使用了**Twitter API** 的**Geo Search** ..  
因為他不用使用**API Key**的  
這樣我們便可以更方便的示範怎樣可以在.Net 上 使用**WebClient** 去 Call一個**Restful Service**  
和當**Restful Service** 回覆**JSON** 的資料是怎樣把他們轉換成**Object** 令到更容易使用

我們會用到這個URL  
 <a title="Twitter GeoSeach API Restful Call" href="https://api.twitter.com/1/geo/search.json?query=hong%20kong" target="_blank">https://api.twitter.com/1/geo/search.json?query=hong%20kong</a>  
在瀏覽器上輸入了這個URL 之後便會出現和下面相似的結果

<pre>{"result":{"places":[{"contained_within":[],"name":"Hong Kong","full_name":"Hong Kong","attributes":{},"bounding_box":null,"url":"http:\/

\/api.twitter.com\/1\/geo\/id\/35fd5bacecc4c6e5.json","place_type":"country","id":"35fd5bacecc4c6e5","country_code":"HK","country":"Hong 

Kong"}]},"query":{"type":"search","params":{"autocomplete":false,"query":"hong 

kong","granularity":"neighborhood","accuracy":0,"trim_place":false},"url":"http:\/\/api.twitter.com\/1\/geo\/search.json?

autocomplete=false&query=hong+kong&accuracy=0&granularity=neighborhood&trim_place=false"}}</pre>

**在.Net上怎樣可以把以上的結果轉成Object呢 和怎樣呼叫這個RestFul services**

**解決方法**:

我們可以使用**WebClient**這個類  
在我們的Project上可以建立一個新的**WebClient Object**

E.G.  
之後設定**OpenReadCompletedEventHandler** //這個是當**Web Server**有回覆時會呼叫的功能  
傳回來的資料會以**Stream** 的方式存在

我們要以上邊的**JSON Response** 建立一些Object方便我們之後取資料時使用  
由於這個**Restful Service**回的是**JSON** 所以我們會使用到**DataContractJsonSerializer** 把這個**Stream 轉換成Object**

以下是

**Sample Code**  
**Twitter Object**  
以下是我以上面的 **JSON Result**而建立的 **Twitter Reponse Object**..  
為了方便..我沒有填上所有的**Properties**.. 當大家有不明的的時候歡迎留言給我

[csharp]  
public class TwitterResponse  
{  
public TwitterGeoSearchResult result { get; set; }  
}

public class TwitterGeoSearchResult  
{  
public List<TwitterPlace> places { get; set; }  
}

public class TwitterPlace  
{  
public string name { get; set; }  
public string full_name { get; set; }  
public string attributes { get; set; }  
public string bounding_box { get; set; }  
public string place_type { get; set; }  
public string id { get; set; }  
public string country_code { get; set; }  
public string country { get; set; }

}

public class TwitterSearchQuery  
{  
public string type { get; set; }  
public string url { get; set; }  
}  
[/csharp]

**定義一個WebClient的Object**

[csharp]  
private WebClient wc;  
[/csharp]

**建立一個方法用來執行這個 Restful Service Call**

[csharp]  
private void GetTwitterGeoSearchResult{  
wc = new WebClient();  
//定義OpenReadCompletedEventHandler 用來處理 Restful Service 的Response  
wc.OpenReadCompleted += new OpenReadCompletedEventHandler(wc_OpenReadCompleted);  
我們可以使用 OpenReadAsync 來執行這個Restful Service Call  
wc.OpenReadAsync(new Uri("https://api.twitter.com/1/geo/search.json?query=hong%20kong"));  
}

void wc_OpenReadCompleted(object sender, OpenReadCompletedEventArgs e)  
{  
//先檢查有沒有錯誤信息..當錯誤信是Null是我們繼續  
if (e.Error == null)  
{

//我們需要建立一個DataContractJsonSerializer 用來打這個 Stream轉換成我們的Object  
DataContractJsonSerializer data = new DataContractJsonSerializer(typeof(TwitterResponse));  
使用ReadObject這個功能轉換 Stream到之前定義好的Object  
TwitterResponse response = (TwitterResponse)data.ReadObject(e.Result);  
//之後我們便可以用這個Object取資料了  
MessageBox.Show(response.result.places[0].country);  
}  
}  
[/csharp]

**請注意:**  
當使用**DataContractJsonSerializer** 的時候我們需要加入

[csharp]  
using System.Runtime.Serialization.Json;  
[/csharp]

這個Namespace的  
如果在你的Project上找不到的話..  
你可能需要加入 **System.ServiceModel** 這個DLL

Hope you find it useful