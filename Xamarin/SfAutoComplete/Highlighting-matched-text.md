---
layout: post
title: MatchHighlighting in Syncfusion SfAutoComplete control for Xamarin.Forms
description: Learn how to highlight the matched text in SfAutoComplete
platform: xamarin
control: SfAutoComplete
documentation: ug
---
# Highlighting matched text

Highlight matching characters in a suggestion list to pick an item with more clarity. There are two ways to highlight the matching text:


* FirstOccurrence

* MultipleOccurrence

## FirstOccurrence

{% tabs %}

{% highlight xaml %}

<StackLayout VerticalOptions="Start" HorizontalOptions="Start" Padding="30">
	<autocomplete:SfAutoComplete HeightRequest="40" x:Name="autoComplete" TextHighlightMode="FirstOccurrence" SuggestionMode="StartsWith"/>                    
</StackLayout> 

{% endhighlight %}

{% highlight c# %}

List<String> countryNames = new List<String>();
countryNames.Add("Uganda");
countryNames.Add("Ukraine");
countryNames.Add("United Arab Emirates");
countryNames.Add("United Kingdom");
countryNames.Add("United States");
autoComplete.SuggestionMode= SuggestionMode.StartsWith;
autoComplete.TextHighlightMode=OccurrenceMode.FirstOccurrence;
autoComplete.DataSource = countryNames;

{% endhighlight %}

{% endtabs %}

![](images/Highlighting-matched-text/FirstOccurrance.png)

## MultipleOccurrence

{% tabs %}

{% highlight xaml %}

<StackLayout VerticalOptions="Start" HorizontalOptions="Start" Padding="30">
	<autocomplete:SfAutoComplete HeightRequest="40" x:Name="autoComplete" TextHighlightMode="MultipleOccurrence" SuggestionMode="Contains"/>                    
</StackLayout> 

{% endhighlight %}

{% highlight c# %}

List<String> countryNames = new List<String>();
countryNames.Add("Uganda");
countryNames.Add("Ukraine");
countryNames.Add("United Arab Emirates");
countryNames.Add("United Kingdom");
countryNames.Add("United States");
autoComplete.SuggestionMode= SuggestionMode.Contains;
autoComplete.TextHighlightMode=OccurrenceMode.MultipleOccurrence;
autoComplete.DataSource = countryNames;

{% endhighlight %}

{% endtabs %}
![](images/Highlighting-matched-text/MultipleOccurrance.png)