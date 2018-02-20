---
layout: post
title: Positioning of header 
description: Positioning of header in Syncfusion TabView control for Xamarin.Forms platform
platform: Xamarin.Forms
control: TabView
documentation: ug
---

## Positioning of header

Tab headers can be positioned either above the content or below the content, it can be done by setting TabHeaderPosition property of SfTabView.

{% tabs %}

{% highlight xaml %}

<tabView:SfTabView  TabHeaderPosition="Bottom" >
			
{% endhighlight %}

{% highlight C# %}

tabView.TabHeaderPosition = TabHeaderPosition.Bottom;
			
{% endhighlight %}

{% endtabs %}

When header is not needed we can set `DisplayMode` of `SfTabView` as `NoHeader`.
