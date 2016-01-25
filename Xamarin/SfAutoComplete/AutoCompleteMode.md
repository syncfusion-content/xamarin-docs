---
layout : post
title : AutoComplete mode for Syncfusion AutoComplete control in Xamarin.Forms
description : Learn how to change the AutoComplete mode in AutoComplete
platform : Xamarin.Forms
control : AutoComplete
documentation : ug
---

# AutoCompleteMode

The `AutocompleteMode` property is used to customize the behavior of the suggestions that are filtered according to the text entered. By default there are three AutoComplete modes provided. They are:

* `Append` - Appends the first matching string with the entered character.
	
{% highlight C# %}
	
	countryAutoComplete.AutoCompleteMode = AutoCompleteMode.Append;
	 
{% endhighlight %}


* `Suggest` - Displays the suggestion in the dropdown.
	
{% highlight C# %}
	
	countryAutoComplete.AutoCompleteMode = AutoCompleteMode.Suggest;
	 
{% endhighlight %}

* `SuggestAppend` - Displays the suggestion in the dropdown along with appending the first matching string.
	
{% highlight C# %}
	
	countryAutoComplete.AutoCompleteMode = AutoCompleteMode.SuggestAppend;
	 
{% endhighlight %}

![](images/autocompletemode.png)
 
