---
layout: post
title: AutoComplete Modes in Xamarin AutoComplete control | Syncfusion
description: Learn about AutoComplete Modes support in Syncfusion Xamarin AutoComplete (SfAutoComplete) control and more details.
platform: xamarin
control: AutoComplete
documentation: ug
---

# AutoComplete Modes in Xamarin AutoComplete (SfAutoComplete)

## Overview

The [`SfAutoComplete`](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfAutoComplete.XForms.SfAutoComplete.html) control provides three different ways to display filtered suggestions through the [`AutoCompleteMode`](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfAutoComplete.XForms.SfAutoComplete.html#Syncfusion_SfAutoComplete_XForms_SfAutoComplete_AutoCompleteMode) property:
* [`Suggest`](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfAutoComplete.XForms.AutoCompleteMode.html#Syncfusion_SfAutoComplete_XForms_AutoCompleteMode_Suggest) - Displays suggestions in a dropdown list
* [`Append`](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfAutoComplete.XForms.AutoCompleteMode.html#Syncfusion_SfAutoComplete_XForms_AutoCompleteMode_Append) - Appends the first suggestion to the text
* [`SuggestAppend`](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfAutoComplete.XForms.AutoCompleteMode.html#Syncfusion_SfAutoComplete_XForms_AutoCompleteMode_SuggestAppend) - Combines both Suggest and Append modes

The default value is [`Suggest`](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfAutoComplete.XForms.AutoCompleteMode.html#Syncfusion_SfAutoComplete_XForms_AutoCompleteMode_Suggest).

## Suggest Mode

In Suggest mode, filtered suggestions are displayed in a dropdown list, allowing users to select an item from the list.
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
        <autocomplete:SfAutoComplete x:Name="autoComplete" 
                                     HeightRequest="40"
                                     AutoCompleteMode="Suggest">
            <autocomplete:SfAutoComplete.AutoCompleteSource>
                <ListCollection:List x:TypeArguments="x:String">
                    <x:String>India</x:String>
                    <x:String>Uganda</x:String>
                    <x:String>Ukraine</x:String>
                    <x:String>Canada</x:String>
                    <x:String>United Arab Emirates</x:String>
                    <x:String>France</x:String>
                    <x:String>United Kingdom</x:String>
                    <x:String>China</x:String>
                    <x:String>United States</x:String>
                    <x:String>Japan</x:String>
                    <x:String>Angola</x:String>
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
                AutoCompleteMode = AutoCompleteMode.Suggest,
                AutoCompleteSource = new List<string>()
                {
                    "India",
                    "Uganda",
                    "Ukraine",
                    "Canada",
                    "United Arab Emirates",
                    "France",
                    "United Kingdom",
                    "China",
                    "United States",
                    "Japan",
                    "Angola"
                }
            };

            stackLayout.Children.Add(autoComplete);
            this.Content = stackLayout;
        }
    }
}

	 
{% endhighlight %}

{% endtabs %}

![suggest](images/AutoComplete-Suggesting-Modes/suggest.png)

## Append Mode
In Append mode, the first item from the filtered suggestions is automatically appended to the text in the [`SfAutoComplete`](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfAutoComplete.XForms.SfAutoComplete.html) control. The dropdown list remains closed in this mode.

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
        <autocomplete:SfAutoComplete x:Name="autoComplete" 
                                     HeightRequest="40"
                                     AutoCompleteMode="Append">
            <autocomplete:SfAutoComplete.AutoCompleteSource>
                <ListCollection:List x:TypeArguments="x:String">
                    <x:String>India</x:String>
                    <x:String>Uganda</x:String>
                    <x:String>Ukraine</x:String>
                    <x:String>Canada</x:String>
                    <x:String>United Arab Emirates</x:String>
                    <x:String>France</x:String>
                    <x:String>United Kingdom</x:String>
                    <x:String>China</x:String>
                    <x:String>United States</x:String>
                    <x:String>Japan</x:String>
                    <x:String>Angola</x:String>
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
                AutoCompleteMode = AutoCompleteMode.Append,
                AutoCompleteSource = new List<string>()
                {
                    "India",
                    "Uganda",
                    "Ukraine",
                    "Canada",
                    "United Arab Emirates",
                    "France",
                    "United Kingdom",
                    "China",
                    "United States",
                    "Japan",
                    "Angola"
                }
            };

            stackLayout.Children.Add(autoComplete);
            this.Content = stackLayout;
        }
    }
}
	 
{% endhighlight %}

{% endtabs %}

![Append](images/AutoComplete-Suggesting-Modes/append.png)

## SuggestAppend Mode

In SuggestAppend mode, the control combines both Suggest and Append behaviors:
- The first matched item is appended to the text
- Filtered suggestions are displayed in a dropdown list

Users can either select an item directly from the list or use the up and down arrow keys to navigate through the suggestions.
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
        <autocomplete:SfAutoComplete x:Name="autoComplete" 
                                     HeightRequest="40"
                                     AutoCompleteMode="SuggestAppend">
            <autocomplete:SfAutoComplete.AutoCompleteSource>
                <ListCollection:List x:TypeArguments="x:String">
                    <x:String>India</x:String>
                    <x:String>Uganda</x:String>
                    <x:String>Ukraine</x:String>
                    <x:String>Canada</x:String>
                    <x:String>United Arab Emirates</x:String>
                    <x:String>France</x:String>
                    <x:String>United Kingdom</x:String>
                    <x:String>China</x:String>
                    <x:String>United States</x:String>
                    <x:String>Japan</x:String>
                    <x:String>Angola</x:String>
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
                AutoCompleteMode = AutoCompleteMode.SuggestAppend,
                AutoCompleteSource = new List<string>()
                {
                    "India",
                    "Uganda",
                    "Ukraine",
                    "Canada",
                    "United Arab Emirates",
                    "France",
                    "United Kingdom",
                    "China",
                    "United States",
                    "Japan",
                    "Angola"
                }
            };

            stackLayout.Children.Add(autoComplete);
            this.Content = stackLayout;
        }
    }
}

{% endhighlight %}

{% endtabs %}

![suggest append](images/AutoComplete-Suggesting-Modes/suggest-append.png)

## See Also

* [Xamarin AutoComplete Features Overview](https://www.syncfusion.com/xamarin-ui-controls/xamarin-autocomplete)
* [Xamarin.Forms AutoComplete Examples](https://github.com/syncfusion/xamarin-demos/tree/master/Forms/AutoComplete)
