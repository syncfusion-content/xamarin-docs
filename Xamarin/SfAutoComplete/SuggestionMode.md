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
	
{% tabs %}	
	
{% highlight c# %}
	
	countryAutoComplete.SuggestionMode = SuggestionMode.StartsWith;
	 
{% endhighlight %}

{% highlight xaml %}

  		<autocomplete:SfAutoComplete  x:Name="countryAutoComplete" SuggestionMode="StartsWith" />

{% endhighlight %}

{% endtabs %}

![](images/startswith.png)

## StartsWithCaseSensitive

Display the list of suggestions based on starting letter with case sensitive.

{% tabs %}

{% highlight c# %}
	
	countryAutoComplete.SuggestionMode = SuggestionMode.StartsWithCaseSensitive;
	 
{% endhighlight %}

{% highlight xaml %}

  		<autocomplete:SfAutoComplete  x:Name="countryAutoComplete" SuggestionMode="StartsWithCaseSensitive" />

{% endhighlight %}

{% endtabs %}

![](images/startswithcasesensitive.png)

## Contains

Display the list of suggestions, if autocomplete list contains that words.
	
{% tabs %}

{% highlight c# %}
	
	countryAutoComplete.SuggestionMode = SuggestionMode.Contains;
	 
{% endhighlight %}

{% highlight xaml %}

  		<autocomplete:SfAutoComplete  x:Name="countryAutoComplete" SuggestionMode="Contains" />

{% endhighlight %}

{% endtabs %}

![](images/contains.png)

## ContainsWithCaseSensitive

Display the list of suggestions, if autoComplete list contains that words with case sensitive.

{% tabs %}

{% highlight c# %}
	
	countryAutoComplete.SuggestionMode = SuggestionMode.ContainsWithCaseSensitive;
	 
{% endhighlight %}

{% highlight xaml %}

  		<autocomplete:SfAutoComplete  x:Name="countryAutoComplete" SuggestionMode="ContainsWithCaseSensitive" />

{% endhighlight %}

{% endtabs %}

![](images/containswithcasesensitive.png)

## Equals

Displays the word that matches.
	
{% tabs %}

{% highlight c# %}
	
	countryAutoComplete.SuggestionMode = SuggestionMode.Equals;
	 
{% endhighlight %}

{% highlight xaml %}

  		<autocomplete:SfAutoComplete  x:Name="countryAutoComplete" SuggestionMode="Equals" />

{% endhighlight %}

{% endtabs %}

![](images/equals.png)

## EqualsWithCaseSensitive

Displays the word that matches with case sensitive.
	
{% tabs %}

{% highlight c# %}
	
	countryAutoComplete.SuggestionMode = SuggestionMode.EqualsWithCaseSensitive;
	 
{% endhighlight %}

{% highlight xaml %}

  		<autocomplete:SfAutoComplete  x:Name="countryAutoComplete" SuggestionMode="EqualsWithCaseSensitive" />

{% endhighlight %}

{% endtabs %}

![](images/equalswithcasesensitive.png)

## EndsWith

Display the list of suggestions based on ending word.

{% tabs %}
	
{% highlight c# %}
	
	countryAutoComplete.SuggestionMode = SuggestionMode.EndsWith;
	 
{% endhighlight %}

{% highlight xaml %}

  		<autocomplete:SfAutoComplete  x:Name="countryAutoComplete" SuggestionMode="EndsWith" />

{% endhighlight %}

{% endtabs %}

![](images/endswith.png)

## EndsWithCaseSensitive

Display the list of suggestions based on the ending word with case sensitive.
	
{% tabs %}

{% highlight c# %}
	
	countryAutoComplete.SuggestionMode = SuggestionMode.EndsWithCaseSensitive;
	 
{% endhighlight %}

{% highlight xaml %}

  		<autocomplete:SfAutoComplete  x:Name="countryAutoComplete" SuggestionMode="EndsWithCaseSensitive" />

{% endhighlight %}

{% endtabs %}

![](images/endswithcasesensitive.png)



