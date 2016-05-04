---
layout : post
title : WaterMark in Syncfusion AutoComplete Control for Xamarin.Forms
description : Learn how to set the Watermark in AutoComplete
platform : Xamarin
control : AutoComplete
documentation : ug
---

# Watermark

The `Watermark` property is used to provide a hint to start with input. 
	
{% tabs %}	
	
{% highlight c# %}
	
	countryAutoComplete.Watermark = "Enter a country name";	 

{% endhighlight %}

{% highlight xaml %}

  		<autocomplete:SfAutoComplete  x:Name="countryAutoComplete" Watermark="Enter a country name" />

{% endhighlight %}

{% endtabs %}

![](images/watermark.png)
