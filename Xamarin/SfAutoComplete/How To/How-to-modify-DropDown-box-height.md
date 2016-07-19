---
layout : post
title : DropDown box height in Syncfusion AutoComplete Control for Xamarin.Forms
description : Learn how to modify DropDown box height
platform : Xamarin
control : AutoComplete
documentation : ug
---

# How to modify DropDown box height?

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