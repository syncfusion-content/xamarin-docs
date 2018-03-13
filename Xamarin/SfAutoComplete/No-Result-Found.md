---
layout: post
title: No Result Found Text in Syncfusion SfAutoComplete control for Xamarin.Forms
description: Learn how to display the no result found text in SfAutoComplete
platform: xamarin
control: SfAutoComplete
documentation: ug
---
# No Results Found

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