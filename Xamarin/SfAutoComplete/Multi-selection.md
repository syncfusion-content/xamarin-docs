---
layout: post
title: Multi Selection in Syncfusion SfAutoComplete control for Xamarin.Forms
description: Learn how to restrict maximum suggestion to be displayed in SfAutoComplete
platform: xamarin
control: SfAutoComplete
documentation: ug
---
# Multi Selection

Select multiple items from a suggestion list. There are two ways to perform multiselection in autocomplete.

* Token Representation

*  Delimiter

## Token Representation

Selected items will be displayed with a customizable token representation and the users can remove each tokenized item with the close button.

{% tabs %}

{% highlight xaml %}

<StackLayout VerticalOptions="Start" HorizontalOptions="Start" Padding="30">
	<autocomplete:SfAutoComplete HeightRequest="40" x:Name="autoComplete" MultiSelectMode="Token" TokensWrapMode="Wrap" IsSelectedItemsVisibleInDropDown="false" />                    
</StackLayout> 

{% endhighlight %}

{% highlight c# %}

List<String> countryNames = new List<String>();
countryNames.Add("Uganda");
countryNames.Add("Ukraine");
countryNames.Add("United Arab Emirates");
countryNames.Add("United Kingdom");
countryNames.Add("United States");
autoComplete.MaximumSuggestion=3;
autoComplete.MultiSelectMode=MultiSelectMode.Token;
autoComplete.TokensWrapMode=TokensWrapMode.Wrap;
autoComplete.IsSelectedItemsVisibleInDropDown=false;
autoComplete.DataSource = countryNames;

{% endhighlight %}

{% endtabs %}

![](images/MultiSelect/TokenRepresentation.png)

## Delimiter

Selected items can be divided with a desired character given for a delimiter.

{% tabs %}

{% highlight xaml %}

<StackLayout VerticalOptions="Start" HorizontalOptions="Start" Padding="30">
	<autocomplete:SfAutoComplete HeightRequest="40" x:Name="autoComplete" MultiSelectMode="Delimiter"  Delimiter="*" />                    
</StackLayout> 

{% endhighlight %}

{% highlight c# %}

List<String> countryNames = new List<String>();
countryNames.Add("Uganda");
countryNames.Add("Ukraine");
countryNames.Add("United Arab Emirates");
countryNames.Add("United Kingdom");
countryNames.Add("United States");
autoComplete.MaximumSuggestion=3;
autoComplete.MultiSelectMode=MultiSelectMode.Delimiter;
autoComplete.Delimiter="*";
autoComplete.DataSource = countryNames;

{% endhighlight %}

{% endtabs %}

![](images/MultiSelect/Delimiter.png)

