---
layout: post
title: LoadMore in Syncfusion SfAutoComplete control for Xamarin.Forms
description: Learn how to restrict maximum suggestion to be displayed in SfAutoComplete
platform: xamarin
control: SfAutoComplete
documentation: ug
---
# Maximum Display Item with Expander

Restrict the number of suggestions displayed and have the remaining items loaded by selecting LoadMore.We can restrict maximum suggestion to be displayed with the `MaximumSuggestion` property. We can set the desire text for the displaying the Load more text with the property `LoadMoreText`.

{% tabs %}

{% highlight xaml %}

<StackLayout VerticalOptions="Start" HorizontalOptions="Start" Padding="30">
	<autocomplete:SfAutoComplete HeightRequest="40" MultiSelectMode="Delimiter" Delimiter="," LoadMoreText= "LOAD MORE" x:Name="autoComplete" MaximumSuggestion="8"  />                    
</StackLayout> 

{% endhighlight %}

{% highlight c# %}

autoComplete.MaximumSuggestion = 8;
autoComplete.LoadMoreText =  "LOAD MORE";

{% endhighlight %}

{% endtabs %}

![](images/Maximum-display-item-with-Expander/LoadMore.png)

### Restricting the maximum display of item dynamically

We can restrict the maximum display of items dynamically by calling `LoadMore` method. The user can dynamically change the maximum suggestion count by calling LoadMore method by giving the maximum suggestion as the argument inside.

{% tabs %}
{% highlight c# %}

// without passing argument
autoComplete.LoadMore();

// with passing argument
autoComplete.LoadMore(5);

{% endhighlight %}
{% endtabs %}

## No Results Found

When the entered item is not in the suggestion list, SfAutoComplete displays a text indicating there is no search results found. We can set the desire text to be displayed for indicating no results found with the `NoResultsFoundText` property.

{% tabs %}

{% highlight xaml %}

<StackLayout VerticalOptions="Start" HorizontalOptions="Start" Padding="30">
	<autocomplete:SfAutoComplete HeightRequest="40" x:Name="autoComplete" NoResultsFoundText="No Results Found" />                    
</StackLayout> 

{% endhighlight %}

{% highlight c# %}

autoComplete.NoResultsFoundText="No Results Found";
autoComplete.DataSource = countryNames;

{% endhighlight %}

{% endtabs %}

![](images/Maximum-display-item-with-Expander/NoResultsFound.png)