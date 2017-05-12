---
layout: post
title: Colors in Syncfusion SfAutoComplete control for Xamarin.Forms
description: Learn how to set minimum Prefix Characters in SfAutoComplete
platform: xamarin
control: SfAutoComplete
documentation: ug
---
# Prefix Characters Constraint

Instead of displaying suggestion list on every character entry, matches can be filtered and displayed after a few character entries. This can be done by [`MinimumPrefixCharacters`] property and its default value is 1.

{% tabs %}

{% highlight xaml %}

<StackLayout VerticalOptions="Start" HorizontalOptions="Start" Padding="30">
	<autocomplete:SfAutoComplete HeightRequest="40" x:Name="autoComplete" MinimumPrefixCharacters="3" />                    
</StackLayout> 

{% endhighlight %}

{% highlight c# %}

List<String> countryNames = new List<String>();
countryNames.Add("Uganda");
countryNames.Add("Ukraine");
countryNames.Add("United Arab Emirates");
countryNames.Add("United Kingdom");
countryNames.Add("United States");
autoComplete.DataSource = countryNames;
autoComplete.MinimumPrefixCharacters = 3;

{% endhighlight %}

{% endtabs %}