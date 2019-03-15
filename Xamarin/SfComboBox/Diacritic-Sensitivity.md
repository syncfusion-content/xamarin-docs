---
layout: post
title: Diacritic sensitivity in Syncfusion SfComboBox control for Xamarin.Forms
description: Learn how to enable and disable Diacritic sensitivity in SfComboBox
platform: xamarin
control: SfComboBox
documentation: ug
---
# Diacritic Sensitivity

The control does not stick with one type of keyboard, so you can populate items from a language with letters containing diacritics, and search for them with English characters from an en-US keyboard. Users can enable or disable the diacritic sensitivity with the `IgnoreDiacritic` property. In the below code example we have illustrate how to enables the diacritic sensitivity so that items in the suggestion list get populated by entering any diacritic character of that alphabet.

{% tabs %}

{% highlight xaml %}

<StackLayout VerticalOptions="Start" HorizontalOptions="Start" Padding="30">
   <combobox:SfComboBox HeightRequest="40" x:Name="comboBox" IsEditableMode="True" AllowFiltering="True" TextHighlightMode="MultipleOccurrence" SuggestionMode="Contains" HighlightedTextColor="Red" IgnoreDiacritic="false"/>
</StackLayout>                   


{% endhighlight %}

{% highlight c# %}

List<String> diacritic = new List<String>();
diacritic.Add("Hów tó gâin wéight?");
diacritic.Add("Hów tó drâw ân éléphânt?");
diacritic.Add("Whéré cân I buy â câmérâ?");
diacritic.Add("Guidé mé âll thé wây");
diacritic.Add("Hów tó mâké â câké?");
diacritic.Add("Sây, Hélló Wórld!");
diacritic.Add("Hów tó mâké â róbót?");
diacritic.Add("Whât timé nów in Indiâ?");
comboBox.DataSource = diacritic;

{% endhighlight %}

{% endtabs %}

![](images/Diacritic-Sensitivity/Diacritic.png)

