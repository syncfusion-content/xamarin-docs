---
layout: post
title: Watermark in Xamarin.Forms AutoComplete | Syncfusion
description: Learn about Watermark support in Syncfusion Xamarin.Forms AutoComplete (SfAutoComplete) control and how to customize it.
platform: xamarin
control: SfAutoComplete
documentation: ug
---

# Watermark in Xamarin.Forms AutoComplete (SfAutoComplete)

## Overview
The [`Watermark`](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfAutoComplete.XForms.SfAutoComplete.html#Syncfusion_SfAutoComplete_XForms_SfAutoComplete_Watermark) property provides a short hint that describes the expected input in the SfAutoComplete control. Watermarks are visible only when the text field is empty and will reappear if the text is cleared.
The following example demonstrates how to use the watermark to hint users to start with the character "U":

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
        <autocomplete:SfAutoComplete
	           x:Name="autoComplete"
	           HeightRequest="40"
               Watermark="Enter 'U' to filter suggestions">
            <autocomplete:SfAutoComplete.AutoCompleteSource>
                <ListCollection:List x:TypeArguments="x:String">
                    <x:String>Antigua and Barbuda</x:String>
                    <x:String>American Samoa</x:String>
                    <x:String>Afghanistan</x:String>
                    <x:String>Antarctica</x:String>
                    <x:String>Argentina</x:String>
                    <x:String>Anguilla</x:String>
                    <x:String>Albania</x:String>
                    <x:String>Algeria</x:String>
                    <x:String>Andorra</x:String>
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
                Padding = 30
            };

            SfAutoComplete autoComplete = new SfAutoComplete()
            {
                HeightRequest = 40,
                Watermark = "Enter 'A' to filter suggestions",
                AutoCompleteSource = new List<string>()
                {
                    "Antigua and Barbuda",
                    "American Samoa",
                    "Afghanistan",
                    "Antarctica",
                    "Argentina",
                    "Anguilla",
                    "Albania",
                    "Algeria",
                    "Andorra",
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

![Watermark](images/Watermark/watermark.png)

> **Note:** There's an inconsistency in the example above. The XAML code shows "Enter 'U' to filter suggestions" while the C# code shows "Enter 'A' to filter suggestions". Make sure to use consistent watermark text in your implementation.
## Customizing Watermark Text Color

You can customize the text color of the watermark using the [`WatermarkColor`](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfAutoComplete.XForms.SfAutoComplete.html#Syncfusion_SfAutoComplete_XForms_SfAutoComplete_WatermarkColor) property:

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
        <autocomplete:SfAutoComplete
	           x:Name="autoComplete"
	           HeightRequest="40"
               Watermark="Enter some text"
               WatermarkColor="#1976d2">
            <autocomplete:SfAutoComplete.AutoCompleteSource>
                <ListCollection:List x:TypeArguments="x:String">
                    <x:String>Antigua and Barbuda</x:String>
                    <x:String>American Samoa</x:String>
                    <x:String>Afghanistan</x:String>
                    <x:String>Antarctica</x:String>
                    <x:String>Argentina</x:String>
                    <x:String>Anguilla</x:String>
                    <x:String>Albania</x:String>
                    <x:String>Algeria</x:String>
                    <x:String>Andorra</x:String>
                    <x:String>Angola</x:String>
                </ListCollection:List>
            </autocomplete:SfAutoComplete.AutoCompleteSource>
        </autocomplete:SfAutoComplete>
    </StackLayout>
</ContentPage>>

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
                Padding = 30
            };

            SfAutoComplete autoComplete = new SfAutoComplete()
            {
                HeightRequest = 40,
                Watermark = "Enter some text",
                WatermarkColor = Color.FromHex("1976d2"),
                AutoCompleteSource = new List<string>()
                {
                    "Antigua and Barbuda",
                    "American Samoa",
                    "Afghanistan",
                    "Antarctica",
                    "Argentina",
                    "Anguilla",
                    "Albania",
                    "Algeria",
                    "Andorra",
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

![Watermark color](images/Watermark/watermark-color.png)

## Setting Initial Focus on the Control

You can set the initial focus on the AutoComplete control when the page loads by using the [`IsFocused`](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfAutoComplete.XForms.SfAutoComplete.html#Syncfusion_SfAutoComplete_XForms_SfAutoComplete_IsFocused) property. This automatically displays the keyboard for user input as soon as the control is rendered.
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
        <autocomplete:SfAutoComplete
	           x:Name="autoComplete"
	           HeightRequest="40"
               Watermark="Enter 'A' to filter suggestions"
               WatermarkColor="#1976d2"
            IsFocused="True">
            <autocomplete:SfAutoComplete.AutoCompleteSource>
                <ListCollection:List x:TypeArguments="x:String">
                    <x:String>Antigua and Barbuda</x:String>
                    <x:String>American Samoa</x:String>
                    <x:String>Afghanistan</x:String>
                    <x:String>Antarctica</x:String>
                    <x:String>Argentina</x:String>
                    <x:String>Anguilla</x:String>
                    <x:String>Albania</x:String>
                    <x:String>Algeria</x:String>
                    <x:String>Andorra</x:String>
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
                Padding = 30
            };

            SfAutoComplete autoComplete = new SfAutoComplete()
            {
                HeightRequest = 40,
                Watermark = "Enter 'A' to filter suggestions",
                WatermarkColor = Color.FromHex("#1976d2"),
                IsFocused = true,
                AutoCompleteSource = new List<string>()
                {
                    "Antigua and Barbuda",
                    "American Samoa",
                    "Afghanistan",
                    "Antarctica",
                    "Argentina",
                    "Anguilla",
                    "Albania",
                    "Algeria",
                    "Andorra",
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

> **Note**
> You can refer to our [Xamarin AutoComplete](https://www.syncfusion.com/xamarin-ui-controls/xamarin-autocomplete) feature tour page for its groundbreaking feature representations. You can also explore our [Xamarin.Forms AutoComplete example](https://github.com/syncfusion/xamarin-demos/tree/master/Forms/AutoComplete) to learn about the functionalities of each feature.
