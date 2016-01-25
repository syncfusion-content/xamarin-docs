---
layout : post
title : Suggestion mode for Syncfusion AutoComplete Control in Xamarin.Forms
description : Learn how to display suggestion mode in AutoComplete 
platform : Xamarin.Forms
control : AutoComplete
documentation : ug
---

# SuggestionMode

It is used to display which type of filtered list is show in the dropdown. They are,

* `StartsWith` - It begins to search with the starting letter.
	
{% highlight C# %}
	
	countryAutoComplete.SuggestionMode = SuggestionMode.StartsWith;
	 
{% endhighlight %}

![](images/startswith.png)

* `StartsWithCaseSensitive` - This mode is used to display the suggestions based on the starting letter with case sensitive in autocomplete.

{% highlight C# %}
	
	countryAutoComplete.SuggestionMode = SuggestionMode.StartsWithCaseSensitive;
	 
{% endhighlight %}

![](images/startswithcasesensitive.png)

* `Contains` - It displays Suggestion if AutoComplete contains that words.
	
{% highlight C# %}
	
	countryAutoComplete.SuggestionMode = SuggestionMode.Contains;
	 
{% endhighlight %}

![](images/contains.png)

* `ContainsWithCaseSensitive` - It displays the Suggestion if AutoComplete contains that Words with Case sensitive.

{% highlight C# %}
	
	countryAutoComplete.SuggestionMode = SuggestionMode.ContainsWithCaseSensitive;
	 
{% endhighlight %}

![](images/containswithcasesensitive.png)

* `Equals` - It displays the word that matches.
	
{% highlight C# %}
	
	countryAutoComplete.SuggestionMode = SuggestionMode.Equals;
	 
{% endhighlight %}

![](images/equals.png)

* `EqualsWithCaseSensitive` - It displays the word that matches.
	
{% highlight C# %}
	
	countryAutoComplete.SuggestionMode = SuggestionMode.EqualsWithCaseSensitive;
	 
{% endhighlight %}

![](images/equalswithcasesensitive.png)

* `EndsWith` - It displays the suggestion based on ending word in AutoComplete control.
	
{% highlight C# %}
	
	countryAutoComplete.SuggestionMode = SuggestionMode.EndsWith;
	 
{% endhighlight %}

![](images/endswith.png)

* `EndsWithCaseSensitive` - It Display the suggestion based on the ending words with case sensitive in AutoComplete Control.
	
{% highlight C# %}
	
	countryAutoComplete.SuggestionMode = SuggestionMode.EndsWithCaseSensitive;
	 
{% endhighlight %}

![](images/endswithcasesensitive.png)



