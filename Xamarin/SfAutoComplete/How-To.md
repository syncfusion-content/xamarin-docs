---
layout : post
title : DropDown box height in Syncfusion AutoComplete Control for Xamarin.Forms
description : Learn how to modify DropDown box height
platform : Xamarin
control : AutoComplete
documentation : ug
---

## How to Modify DropDown Box Height?

Inorder to vary the number of items in the view or to make the list to fit your layout, the dropdown height of the suggestion box can be varied using the `MaximumDropDownHeight` property.

N> The `MaximumDropDownHeight` value can be any positive integer value.	

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

The suggestion list item's look can be customised with some of the basic options like item's height, text color and text size are available with autocomplete component.

{% tabs %}

{% highlight c# %}
	
SfAutoComplete sfAutoComplete = new SfAutoComplete();

sfAutoComplete.DropDownItemHeight = 300;

sfAutoComplete.DropDownTextColor = Color.Blue;

sfAutoComplete .DropDownTextSize = 34;
	 
{% endhighlight %}

{% highlight xaml %}

  		<autocomplete:SfAutoComplete x:Name="countryAutoComplete" DropDownTextSize="34"  DropDownItemHeight="300" DropDownTextColor="Blue"/>

{% endhighlight %}

{% endtabs %}


![](images/itemheight.png)