---
layout : post
title : MinimumPrefixCharacter for Syncfusion AutoComplete Control in Xamarin.Forms
description : Learn how to set the MinimumPrefixCharacter in AutoComplete
platform : Android
control : AutoComplete
documentation : ug
---

# MinimumPrefixCharacter

* The minimum number of characters to be entered in the text box before the Autocomplete Box displays possible matches. 

* To set `MinimumPrefixCharacter`to -1, the Autocomplete Box will not provide possible matches. There is no maximum value, but setting MinimumPrefixCharacter to value that is too large will prevent the Autocomplete Box from providing possible matches as well.

N> Population of the Autocomplete Box does not occur until the conditions specified by the MinimumPrefixCharacter property values are met.The default is 1.
	
{% highlight C# %}
	
	countryAutoComplete.MinimumPrefixCharacters = 4
	 
{% endhighlight %}
	
![](images/minimumprefixcharacter.png)
