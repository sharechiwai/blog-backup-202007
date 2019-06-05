---
id: 2852
title: '.Net Convert  Windows.Devices.Geolocation.Geocoordinate to System.Device.Location.GeoCoordinate'
date: 2013-05-08T00:00:42+08:00
author: ShareChiWai
layout: post
guid: http://blog.sharechiwai.com/?p=2852
permalink: /2013/05/net-convert-windows-devices-geolocation-geocoordinate-to-system-device-location-geocoordinate/
categories:
  - .Net Tips And Tricks
---
今天寫的其中一個功能需要把 **<span style="color: #008000;">Windows.Devices.Geolocation.Geocoordinate</span>** 轉換成 <span style="color: #008000;"><strong>System.Device.Location.GeoCoordinate</strong></span>

以下便是這個功能了

[csharp]

/// <summary>  
/// This function convert the Windows.Devices.Geolocation.Geocoordinate to  
/// System.Device.Location.GeoCoordinate  
/// </summary>  
/// <param name="geocoordinate">Geocoordinate in type Windows.Devices.Geolocation.Geocoordinate </param>  
/// <returns>GeoCoordinate in type System.Device.Location.GeoCoordinate</returns>  
private static GeoCoordinate ConvertGeocoordinate(Geocoordinate geocoordinate)  
{  
return new GeoCoordinate(  
geocoordinate.Latitude,  
geocoordinate.Longitude,  
geocoordinate.Altitude ?? double.NaN,  
geocoordinate.Accuracy,  
geocoordinate.AltitudeAccuracy ?? double.NaN,  
geocoordinate.Speed ?? double.NaN,  
geocoordinate.Heading ?? double.NaN);  
}  
[/csharp]

Hope you find it useful