---
layout: post
title: LoadMore in Syncfusion SfAutoComplete control for Xamarin.Forms
description: Learn how to restrict maximum suggestion to be displayed in SfAutoComplete
platform: xamarin
control: SfAutoComplete
documentation: ug
---
# Maximum Display Item with Expander

Restrict the number of suggestions displayed and have the remaining items loaded by selecting LoadMore. We can also set the maximum suggestion to be displayed using LoadMore method.

{% tabs %}

{% highlight xaml %}

<StackLayout VerticalOptions="Start" HorizontalOptions="Start" Padding="30">
	<autocomplete:SfAutoComplete HeightRequest="40" x:Name="autoComplete" MaximumSuggestion="3"  />                    
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
autoComplete.DataSource = countryNames;

{% endhighlight %}

{% endtabs %}

![](images/Maximum-display-item-with-Expander/LoadMore.png)