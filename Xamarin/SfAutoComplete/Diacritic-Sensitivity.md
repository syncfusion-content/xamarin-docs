---
layout: post
title: Diacritic sensitivity in Syncfusion SfAutoComplete control for Xamarin.Forms
description: Learn how to enable and disable Diacritic sensitivity in SfAutoComplete
platform: xamarin
control: SfAutoComplete
documentation: ug
---
# Diacritic Sensitivity

The control does not stick with one type of keyboard, so you can populate items from a language with letters containing diacritics, and search for them with English characters from an en-US keyboard. Users can enable or disable the diacritic sensitivity with the `IgnoreDiacritic` porperty. In the below code example we have illustrate how to disable the diacritic sensitivity so that items in the suggestion list get populated by entering any diacritic character of that alphabet.

{% tabs %}

{% highlight xaml %}

<StackLayout VerticalOptions="Start" HorizontalOptions="Start" Padding="30">
    <auto:SfAutoComplete HeightRequest="40" x:Name="autoComplete" TextHighlightMode="MultipleOccurrence" SuggestionMode="Contains" HighlightedTextColor="Red" IgnoreDiacritic="false"  /> 
</StackLayout>                   


{% endhighlight %}

{% highlight c# %}

        List<String> diacritic = new List<String>();
		diacritic.Add("Diréct mé tó hómé");
		diacritic.Add("Hów tó gâin wéight?");
		diacritic.Add("Hów tó drâw ân éléphânt?");
		diacritic.Add("Whéré cân I buy â câmérâ?");
		diacritic.Add("Guidé mé âll thé wây");
		diacritic.Add("Hów tó mâké â câké?");
		diacritic.Add("Sây, Hélló Wórld!");
		diacritic.Add("Hów tó mâké â róbót?");
		diacritic.Add("Whât timé nów in Indiâ?");
		diacritic.Add("Whó is whó in thé wórld?");
		autoComplete.DataSource = diacritic;

{% endhighlight %}

{% endtabs %}

![](images/Maximum-display-item-with-Expander/LoadMore.png)

