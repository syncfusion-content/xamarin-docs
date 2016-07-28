---
layout : post
title : MinimumPrefixCharacter for Syncfusion AutoComplete Control in Xamarin.Forms
description : Learn how to set the MinimumPrefixCharacter in AutoComplete
platform : Xamarin
control : AutoComplete
documentation : ug
---

# Customizing the Suggestion DropDown

The suggestion list displaying behaviour can be customised based on the entered text and delays in displaying the items.

## Set Minimum Prefix Character

Instead of displaying suggestion list on every text entry, the most possible match can be filtered and displayed after few text entries. This can be done by modifying `MinimumPrefixCharacters`.


N> The default property value is 1.
	
{% tabs %}	

{% highlight xaml %}

  	<autocomplete:SfAutoComplete x:Name="countryAutoComplete"  MinimumPrefixCharacters="4" />

{% endhighlight %}
	
{% highlight c# %}
	
	countryAutoComplete.MinimumPrefixCharacters = 4
	 
{% endhighlight %}

{% endtabs %}
	
![](images/minimumprefixcharacter.png)

## Set Popup Delay

We can delay the time taken to display the dropdown with suggestion list by using the `PopUpDelay` property in SfAutoComplete .

N> The default value is 0. The property value is maintained in milliseconds.

{% tabs %}

{% highlight xaml %}

  	<autocomplete:SfAutoComplete x:Name="countryAutoComplete" PopUpDelay="100" />

{% endhighlight %}

{% highlight c# %}
	
	sfAutoComplete.PopUpDelay = 100;
	 
{% endhighlight %}

{% endtabs %}
	
## Set Maximum Height to the DropDown

The height of the drop-down portion of the SfAutocomplete control can be varied using `MaximumDropDownHeight` property. 

N> The `MaximumDropDownHeight` value can be any positive integer value.	

{% tabs %}

{% highlight xaml %}

  		<autocomplete:SfAutoComplete x:Name="countryAutoComplete"  MaximumDropDownHeight="300" />

{% endhighlight %}

{% highlight c# %}
	
	countryAutoComplete.MaximumDropDownHeight = 300;
	 
{% endhighlight %}

{% endtabs %}
 
![](images/maximumdropdownheight.png)


## Customizing Suggestion Box Item

The suggestion list item's look can be customized with some of the basic options like item's height, text color and text size which are available with autocomplete component.

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
