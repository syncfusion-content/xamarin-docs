---
layout : post
title : Suggestion box item properties in Syncfusion AutoComplete Control for Xamarin.Forms
description : Learn how to modify Suggestion box item properties
platform : Xamarin
control : AutoComplete
documentation : ug
---

# How to modify Suggestion box item properties

Suggestion box item properties can be modified using `DrawCell` event in SfAutoComplete.

{% highlight c# %}
	
sfAutoComplete.DrawCell += (object sender, DrawCellEventArgs e) =>
{
SfAutoComplete sfAutoComplete = (SfAutoComplete)e.AutoComplete;

sfAutoComplete .DropDownTextSize = 34;

sfAutoComplete .DropDownTextColor = Color.Fuchsia;
};
	 
{% endhighlight %}


Item Height and TextColor can be modified using `DropDownItemHeight` and `DropDownItemTextColor` properties in SfAutoComplete control.�

{% tabs %}

{% highlight c# %}
	
SfAutoComplete sfAutoComplete = new SfAutoComplete();

sfAutoComplete.DropDownItemHeight = 300;

sfAutoComplete.DropDownTextColor = Color.Blue;
	 
{% endhighlight %}

{% highlight xaml %}

  		<autocomplete:SfAutoComplete x:Name="countryAutoComplete"  DropDownItemHeight="300" DropDownTextColor = "Blue"/>

{% endhighlight %}

{% endtabs %}


![](images/itemheight.png)
