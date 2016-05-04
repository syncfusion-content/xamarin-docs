---
layout : post
title : MaximumDropDownHeight for Syncfusion AutoComplete Control in Xamarin.Forms
description : Learn how to set the MaximumDropDownHeight in AutoComplete
platform : Xamarin
control : AutoComplete
documentation : ug
---

# MaximumDropDownHeight

To set the maximum height of the drop-down portion of the Autocomplete control. 

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
