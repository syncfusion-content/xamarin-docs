---
layout : post
title : Suggestion mode for Syncfusion AutoComplete Control in Xamarin.Forms
description : Learn how to display suggestion mode in AutoComplete 
platform : Xamarin
control : AutoComplete
documentation : ug
---

# SuggestionMode

The `SuggestionMode` property is used to decide the filtered data to be displayed. 

N> By default, there are eight types of suggestion modes.

## StartsWith
Display the list of suggestions based on starting letter.
	
{% highlight C# %}
	
	countryAutoComplete.SuggestionMode = SuggestionMode.StartsWith;
	 
{% endhighlight %}

![](images/startswith.png)

## StartsWithCaseSensitive
Display the list of suggestions based on starting letter with case sensitive.

{% highlight C# %}
	
	countryAutoComplete.SuggestionMode = SuggestionMode.StartsWithCaseSensitive;
	 
{% endhighlight %}

![](images/startswithcasesensitive.png)

## Contains
Display the list of suggestions, if autocomplete list contains that words.
	
{% highlight C# %}
	
	countryAutoComplete.SuggestionMode = SuggestionMode.Contains;
	 
{% endhighlight %}

![](images/contains.png)

## ContainsWithCaseSensitive
Display the list of suggestions, if autoComplete list contains that words with case sensitive.

{% highlight C# %}
	
	countryAutoComplete.SuggestionMode = SuggestionMode.ContainsWithCaseSensitive;
	 
{% endhighlight %}

![](images/containswithcasesensitive.png)

## Equals
Displays the word that matches.
	
{% highlight C# %}
	
	countryAutoComplete.SuggestionMode = SuggestionMode.Equals;
	 
{% endhighlight %}

![](images/equals.png)

## EqualsWithCaseSensitive
Displays the word that matches with case sensitive.
	
{% highlight C# %}
	
	countryAutoComplete.SuggestionMode = SuggestionMode.EqualsWithCaseSensitive;
	 
{% endhighlight %}

![](images/equalswithcasesensitive.png)

## EndsWith
Display the list of suggestions based on ending word.
	
{% highlight C# %}
	
	countryAutoComplete.SuggestionMode = SuggestionMode.EndsWith;
	 
{% endhighlight %}

![](images/endswith.png)

## EndsWithCaseSensitive
Display the list of suggestions based on the ending word with case sensitive.
	
{% highlight C# %}
	
	countryAutoComplete.SuggestionMode = SuggestionMode.EndsWithCaseSensitive;
	 
{% endhighlight %}

![](images/endswithcasesensitive.png)



