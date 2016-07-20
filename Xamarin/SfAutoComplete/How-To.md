---
layout : post
title : DropDown box height in Syncfusion AutoComplete Control for Xamarin.Forms
description : Learn how to modify DropDown box height
platform : Xamarin
control : AutoComplete
documentation : ug
---

## How to Modify DropDown Box Height?

To set the maximum height of the drop-down portion of the SfAutocomplete control `MaximumDropDownHeight` property can be used. 

N> The `MaximumDropDownHeight` value can be any integer value.	

{% tabs %}

{% highlight c# %}
	
	countryAutoComplete.MaximumDropDownHeight = 300;
	 
{% endhighlight %}

{% highlight xaml %}

  		<autocomplete:SfAutoComplete x:Name="countryAutoComplete"  MaximumDropDownHeight="300" />

{% endhighlight %}

{% endtabs %}
 
![](images/maximumdropdownheight.png)


## How to Modify Suggestion Box Item Properties?

Suggestion box item properties can be modified using `DrawCell` event in SfAutoComplete.

{% highlight c# %}
	
sfAutoComplete.DrawCell += (object sender, DrawCellEventArgs e) =>
{
SfAutoComplete sfAutoComplete = (SfAutoComplete)e.AutoComplete;

sfAutoComplete .DropDownTextSize = 34;

sfAutoComplete .DropDownTextColor = Color.Fuchsia;
};
	 
{% endhighlight %}

Item Height and TextColor can be modified using `DropDownItemHeight` and `DropDownItemTextColor` properties in SfAutoComplete control.

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