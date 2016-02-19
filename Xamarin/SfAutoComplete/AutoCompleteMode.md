---
layout : post
title : AutoComplete mode for Syncfusion AutoComplete control in Xamarin.Forms
description : Learn how to change the AutoComplete mode in AutoComplete
platform : Xamarin
control : AutoComplete
documentation : ug
---

# AutoCompleteMode

The `AutocompleteMode` property is used to decide the suggestion pattern for displaying the filtered data according to the text entered. 

N> By default, three types of autocomplete mode such as `Append`, `Suggest` and `SuggestAppend` are provided.

## Append
Appends the first matching string with the entered character.
	
{% highlight C# %}
	
	countryAutoComplete.AutoCompleteMode = AutoCompleteMode.Append;
	 
{% endhighlight %}

![](images/autocompletemode.png)

## Suggest 
Displays the suggestion in the dropdown.

{% highlight C# %}
	
	countryAutoComplete.AutoCompleteMode = AutoCompleteMode.Suggest;
	 
{% endhighlight %}

![](images/autocompletesource.png)

## SuggestAppend
Displays the suggestion in the dropdown along with appending the first matching string.
	
{% highlight C# %}
	
	countryAutoComplete.AutoCompleteMode = AutoCompleteMode.SuggestAppend;
	 
{% endhighlight %}

![](images/suggestappend.png)
 
