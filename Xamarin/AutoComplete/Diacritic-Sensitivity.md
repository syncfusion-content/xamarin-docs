---
layout: post
title: Diacritic sensitivity in Syncfusion SfAutoComplete control 
description: This section will describes about how to enable and disable Diacritic sensitivity in Xamarin.Forms SfAutoComplete
platform: xamarin
control: SfAutoComplete
documentation: ug
---
# Diacritic Sensitivity

## Diacritic Sensitivity  in Xamarin SfAutoComplete

The control does not stick with one type of keyboard, so you can populate items from a language with letters containing diacritics, and search for them with English characters from an en-US keyboard. Users can enable or disable the diacritic sensitivity with the `IgnoreDiacritic` property. In the below code example we have illustrate how to enables the diacritic sensitivity so that items in the suggestion list get populated by entering any diacritic character of that alphabet.

{% tabs %}

{% highlight xaml %}

<?xml version="1.0" encoding="utf-8" ?>
<ContentPage xmlns="http://xamarin.com/schemas/2014/forms"
             xmlns:x="http://schemas.microsoft.com/winfx/2009/xaml"
             xmlns:autocomplete="clr-namespace:Syncfusion.SfAutoComplete.XForms;assembly=Syncfusion.SfAutoComplete.XForms"
             xmlns:ListCollection="clr-namespace:System.Collections.Generic;assembly=netstandard"
             xmlns:local="clr-namespace:AutocompleteSample"
             x:Class="AutocompleteSample.MainPage">
    <StackLayout VerticalOptions="Start" 
                 HorizontalOptions="Start" 
                 Padding="30">
        <autocomplete:SfAutoComplete HeightRequest="40" 
                                     TextHighlightMode="MultipleOccurrence" 
                                     SuggestionMode="Contains"
                                     HighlightedTextColor="Red" 
                                     IgnoreDiacritic="false">
            <autocomplete:SfAutoComplete.AutoCompleteSource>
                <ListCollection:List x:TypeArguments="x:String">
                    <x:String>Hów tó gâin wéight?</x:String>
                    <x:String>Hów tó drâw ân éléphânt?</x:String>
                    <x:String>Whéré cân I buy â câmérâ?</x:String>
                    <x:String>Guidé mé âll thé wây</x:String>
                    <x:String>Hów tó mâké â câké?</x:String>
                    <x:String>Sây, Hélló Wórld!</x:String>
                    <x:String>Hów tó mâké â róbót?</x:String>
                    <x:String>Whât timé nów in Indiâ?</x:String>
                </ListCollection:List>
            </autocomplete:SfAutoComplete.AutoCompleteSource>
        </autocomplete:SfAutoComplete>
    </StackLayout>
</ContentPage>    

{% endhighlight %}

{% highlight c# %}

using Syncfusion.SfAutoComplete.XForms;
using System.Collections.Generic;
using Xamarin.Forms;

namespace AutocompleteSample
{
    public partial class MainPage : ContentPage
    {
        public MainPage()
        {
            InitializeComponent();
            StackLayout stackLayout = new StackLayout()
            {
                VerticalOptions = LayoutOptions.Start,
                HorizontalOptions = LayoutOptions.Start,
                Padding = new Thickness(30)
            };

            SfAutoComplete autoComplete = new SfAutoComplete()
            {
                HeightRequest = 40,
                TextHighlightMode = OccurrenceMode.MultipleOccurrence,
                SuggestionMode = SuggestionMode.Contains,
                HighlightedTextColor = Color.Red,
                IgnoreDiacritic = false,
                AutoCompleteSource = new List<string>()
                {
                   "Hów tó gâin wéight?",
                   "Hów tó drâw ân éléphânt?",
                   "Whéré cân I buy â câmérâ?",
                   "Guidé mé âll thé wây",
                   "Hów tó mâké â câké?",
                   "Sây, Hélló Wórld!",
                   "Hów tó mâké â róbót?",
                   "Whât timé nów in Indiâ?"
                }
            };

            stackLayout.Children.Add(autoComplete);
            this.Content = stackLayout;
        }
    }
}

{% endhighlight %}

{% endtabs %}

![Diacritic-Sensitivity](images/Diacritic-Sensitivity/Diacritic.png)

