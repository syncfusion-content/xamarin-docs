---
layout: post
title: Text Highlighting in Xamarin AutoComplete | Syncfusion
description: This section describes how to highlight the matched characters in the Syncfusion Xamarin.Forms SfAutoComplete control.
platform: xamarin
control: SfAutoComplete
documentation: ug
---
# Highlighting Matched Text in Xamarin AutoComplete

## Overview

The SfAutoComplete control allows you to highlight matching characters in the suggestion list, making it easier for users to identify and select the desired item. This feature enhances the user experience by visually emphasizing the text that matches the user's input.

There are two highlighting modes available:
* [`FirstOccurrence`](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfAutoComplete.XForms.OccurrenceMode.html#Syncfusion_SfAutoComplete_XForms_OccurrenceMode_FirstOccurrence) - Highlights only the first instance of the matching text
* [`MultipleOccurrence`](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfAutoComplete.XForms.OccurrenceMode.html#Syncfusion_SfAutoComplete_XForms_OccurrenceMode_MultipleOccurrence) - Highlights all instances of the matching text

## Customizing the Highlighted Text

You can customize the appearance of the highlighted text using the following properties:
* [`HighlightedTextColor`](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfAutoComplete.XForms.SfAutoComplete.html#Syncfusion_SfAutoComplete_XForms_SfAutoComplete_HighlightedTextColor) - Sets the color of the highlighted text to differentiate it from the rest of the text.
* [`HighlightedTextFontAttributes`](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfAutoComplete.XForms.SfAutoComplete.html#Syncfusion_SfAutoComplete_XForms_SfAutoComplete_HighlightedTextFontAttributes) - Sets the font attributes (such as Bold, Italic) of the highlighted text.

## Highlighting the First Occurrence

When you set the [`TextHighlightMode`](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfAutoComplete.XForms.SfAutoComplete.html#Syncfusion_SfAutoComplete_XForms_SfAutoComplete_TextHighlightMode) property to [`FirstOccurrence`](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfAutoComplete.XForms.OccurrenceMode.html#Syncfusion_SfAutoComplete_XForms_OccurrenceMode_FirstOccurrence), only the first instance of the matching text in each suggestion item will be highlighted.

This is particularly useful with the [`StartsWith`](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfAutoComplete.XForms.SuggestionMode.html#Syncfusion_SfAutoComplete_XForms_SuggestionMode_StartsWith) suggestion mode, as shown in the following example:
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
                                     TextHighlightMode="FirstOccurrence"
                                     HighlightedTextColor="Red"
                                     HighlightedTextFontAttributes="Bold"
                                     SuggestionMode="StartsWith">
            <autocomplete:SfAutoComplete.AutoCompleteSource>
                <ListCollection:List x:TypeArguments="x:String">
                    <x:String>Albania</x:String>
                    <x:String>Algeria</x:String>
                    <x:String>American Samoa</x:String>
                    <x:String>Andorra</x:String>
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
                SuggestionMode = SuggestionMode.StartsWith,
                TextHighlightMode = OccurrenceMode.FirstOccurrence,
                HighlightedTextColor = Color.Red,
                HighlightedTextFontAttributes = FontAttributes.Bold,
                AutoCompleteSource = new List<string>()
                {
                    "Albania",
                    "Algeria",
                    "American Samoa",
                    "Andorra"
                }
            };

            stackLayout.Children.Add(autoComplete);
            this.Content = stackLayout;
        }
    }
}

{% endhighlight %}

{% endtabs %}

![First occurrence text highlighting](images/Highlighting-matched-text/FirstOccurrance.png)

## Highlighting Multiple Occurrences

It highlights the matching character that are present everywhere in the suggestion list for [`Contains`](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfAutoComplete.XForms.SuggestionMode.html#Syncfusion_SfAutoComplete_XForms_SuggestionMode_Contains) case in [`SuggestionMode`](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfAutoComplete.XForms.SfAutoComplete.html#Syncfusion_SfAutoComplete_XForms_SfAutoComplete_SuggestionMode).

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
                                     HighlightedTextColor="Red"
                                     HighlightedTextFontAttributes="Bold"
                                     SuggestionMode="Contains">
            <autocomplete:SfAutoComplete.AutoCompleteSource>
                <ListCollection:List x:TypeArguments="x:String">
                    <x:String>Albania</x:String>
                    <x:String>Algeria</x:String>
                    <x:String>American Samoa</x:String>
                    <x:String>Andorra</x:String>
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
                SuggestionMode = SuggestionMode.Contains,
                TextHighlightMode = OccurrenceMode.MultipleOccurrence,
                HighlightedTextColor = Color.Red,
                HighlightedTextFontAttributes = FontAttributes.Bold,
                AutoCompleteSource = new List<string>()
                {
                    "Albania",
                    "Algeria",
                    "American Samoa",
                    "Andorra"
                }
            };

            stackLayout.Children.Add(autoComplete);
            this.Content = stackLayout;
        }
    }
}

{% endhighlight %}

{% endtabs %}
![Multiple occurrence text highlighting](images/Highlighting-matched-text/MultipleOccurrance.png)

N> You can refer to our [Xamarin AutoComplete](https://www.syncfusion.com/xamarin-ui-controls/xamarin-autocomplete) feature tour page for its groundbreaking feature representations. You can also explore our [Xamarin.Forms AutoComplete example](https://github.com/syncfusion/xamarin-demos/tree/master/Forms/AutoComplete) to knows the functionalities of each feature.