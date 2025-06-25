---
layout: post
title: Diacritic Sensitivity in Xamarin SfAutoComplete | Syncfusion
description: This section describes how to enable and disable diacritic sensitivity in the Xamarin.Forms SfAutoComplete control
platform: xamarin
control: SfAutoComplete
documentation: ug
---
# Diacritic Sensitivity in Xamarin SfAutoComplete

The SfAutoComplete control supports working with different languages and keyboard types. This allows you to populate items from languages with letters containing diacritics (accent marks) and search for them using English characters from an en-US keyboard.

## Configuring Diacritic Sensitivity

Users can enable or disable the diacritic sensitivity using the [`IgnoreDiacritic`](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfAutoComplete.XForms.SfAutoComplete.html#Syncfusion_SfAutoComplete_XForms_SfAutoComplete_IgnoreDiacritic) property. When set to `false`, the control becomes diacritic-sensitive, meaning it distinguishes between characters with and without diacritics. When set to `true` (default), the control ignores diacritics during search operations.

The following example demonstrates how to enable diacritic sensitivity so that items in the suggestion list are populated only when entering the exact diacritic characters:
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

N> You can refer to our [Xamarin AutoComplete](https://www.syncfusion.com/xamarin-ui-controls/xamarin-autocomplete) feature tour page for its groundbreaking feature representations. You can also explore our [Xamarin.Forms AutoComplete example](https://github.com/syncfusion/xamarin-demos/tree/master/Forms/AutoComplete) to knows the functionalities of each feature.