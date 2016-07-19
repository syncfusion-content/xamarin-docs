---
layout : post
title : MinimumPrefixCharacter for Syncfusion AutoComplete Control in Xamarin.Forms
description : Learn how to set the MinimumPrefixCharacter in AutoComplete
platform : Xamarin
control : AutoComplete
documentation : ug
---


# Customizing Suggestion Box Behaviour

## Set Minimum Prefix Character

The minimum number of characters to be entered in the text box before the autocomplete suggestion box displays possible matches. 

N> The default property value is 1.
	
{% tabs %}	
	
{% highlight c# %}
	
	countryAutoComplete.MinimumPrefixCharacters = 4
	 
{% endhighlight %}

{% highlight xaml %}

  		<autocomplete:SfAutoComplete x:Name="countryAutoComplete"  MinimumPrefixCharacters="4" />

{% endhighlight %}

{% endtabs %}
	
![](images/minimumprefixcharacter.png)

## Set Popup Opening Delay

We can delay the time taken to display the dropdown with suggestion list based on the text entered by using the `PopUpDelay` property in SfAutoComplete .

N> The default value is 0. The property value should be in milliseconds.

{% tabs %}

{% highlight c# %}
	
	sfAutoComplete.PopUpDelay = 100;
	 
{% endhighlight %}

{% highlight xaml %}

  		<autocomplete:SfAutoComplete x:Name="countryAutoComplete" PopUpDelay="100" />

{% endhighlight %}

{% endtabs %}
	
