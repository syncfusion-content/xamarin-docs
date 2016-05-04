---
layout : post
title : MinimumPrefixCharacter for Syncfusion AutoComplete Control in Xamarin.Forms
description : Learn how to set the MinimumPrefixCharacter in AutoComplete
platform : Xamarin
control : AutoComplete
documentation : ug
---

# MinimumPrefixCharacter

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
