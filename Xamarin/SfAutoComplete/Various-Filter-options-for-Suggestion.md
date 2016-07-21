---
layout : post
title : Suggestion mode for Syncfusion AutoComplete Control in Xamarin.Forms
description : Learn how to display suggestion mode in AutoComplete 
platform : Xamarin
control : AutoComplete
documentation : ug
---

# Various Filter Options for Suggestion

By default, the items that matches with the starting letter will be displayed as suggestion. This phenomenon can be changed using  `SuggestionMode` property, which provides various option to filter the data according to the text entered. There are eight types of suggestion modes and are described as follows

## Words that Starts with Input Text

Display the list of suggestions based on starting letter.
	
{% tabs %}	

{% highlight xaml %}

  	<autocomplete:SfAutoComplete  x:Name="countryAutoComplete" SuggestionMode="StartsWith" />

{% endhighlight %}
	
{% highlight c# %}
	
	countryAutoComplete.SuggestionMode = SuggestionMode.StartsWith;
	 
{% endhighlight %}

{% endtabs %}

![](images/startswith.png)

### Consider the Character Casing

Display the list of suggestions based on starting letter with case sensitive.

{% tabs %}

{% highlight xaml %}

  	<autocomplete:SfAutoComplete  x:Name="countryAutoComplete" SuggestionMode="StartsWithCaseSensitive" />

{% endhighlight %}

{% highlight c# %}
	
	countryAutoComplete.SuggestionMode = SuggestionMode.StartsWithCaseSensitive;
	 
{% endhighlight %}

{% endtabs %}

![](images/startswithcasesensitive.png)

## Words that Contains the Input Text

Display the list of suggestions, if autocomplete list contains that words.
	
{% tabs %}

{% highlight xaml %}

  	<autocomplete:SfAutoComplete  x:Name="countryAutoComplete" SuggestionMode="Contains" />

{% endhighlight %}

{% highlight c# %}
	
	countryAutoComplete.SuggestionMode = SuggestionMode.Contains;
	 
{% endhighlight %}

{% endtabs %}

![](images/contains.png)

### Consider the Character Casing

Display the list of suggestions, if autoComplete list contains that words with case sensitive.

{% tabs %}

{% highlight xaml %}

  	<autocomplete:SfAutoComplete  x:Name="countryAutoComplete" SuggestionMode="ContainsWithCaseSensitive" />

{% endhighlight %}

{% highlight c# %}
	
	countryAutoComplete.SuggestionMode = SuggestionMode.ContainsWithCaseSensitive;
	 
{% endhighlight %}

{% endtabs %}

![](images/containswithcasesensitive.png)

## Words that Equals to the Input Text

Displays the word that matches.
	
{% tabs %}

{% highlight xaml %}

  	<autocomplete:SfAutoComplete  x:Name="countryAutoComplete" SuggestionMode="Equals" />

{% endhighlight %}

{% highlight c# %}
	
	countryAutoComplete.SuggestionMode = SuggestionMode.Equals;
	 
{% endhighlight %}

{% endtabs %}

![](images/equals.png)

### Consider the Character Casing

Displays the word that matches with case sensitive.
	
{% tabs %}

{% highlight xaml %}

  	<autocomplete:SfAutoComplete  x:Name="countryAutoComplete" SuggestionMode="EqualsWithCaseSensitive" />

{% endhighlight %}

{% highlight c# %}
	
	countryAutoComplete.SuggestionMode = SuggestionMode.EqualsWithCaseSensitive;
	 
{% endhighlight %}

{% endtabs %}

![](images/equalswithcasesensitive.png)

## Words that Ends with Input Text

Display the list of suggestions based on ending word.

{% tabs %}
	
{% highlight xaml %}

  	<autocomplete:SfAutoComplete  x:Name="countryAutoComplete" SuggestionMode="EndsWith" />

{% endhighlight %}

{% highlight c# %}
	
	countryAutoComplete.SuggestionMode = SuggestionMode.EndsWith;
	 
{% endhighlight %}


{% endtabs %}

![](images/endswith.png)

### Consider the Character Casing

Display the list of suggestions based on the ending word with case sensitive.
	
{% tabs %}

{% highlight xaml %}

  	<autocomplete:SfAutoComplete  x:Name="countryAutoComplete" SuggestionMode="EndsWithCaseSensitive" />

{% endhighlight %}

{% highlight c# %}
	
	countryAutoComplete.SuggestionMode = SuggestionMode.EndsWithCaseSensitive;
	 
{% endhighlight %}

{% endtabs %}

![](images/endswithcasesensitive.png)



