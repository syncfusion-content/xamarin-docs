---
layout: post
title: Load More in Xamarin AutoComplete | Syncfusion
description: This section describes how to restrict the maximum number of suggestions displayed in the Syncfusion Xamarin.Forms SfAutoComplete control.
platform: xamarin
control: SfAutoComplete
documentation: ug
---
# Maximum Display Item with Load More Option

## Maximum display item with expander in Xamarin SfAutoComplete

Restrict the number of suggestions displayed and have the remaining items loaded by selecting [`LoadMore`](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfAutoComplete.XForms.SfAutoComplete.html#Syncfusion_SfAutoComplete_XForms_SfAutoComplete_LoadMore).We can restrict maximum suggestion to be displayed with the [`MaximumSuggestion`](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfAutoComplete.XForms.SfAutoComplete.html#Syncfusion_SfAutoComplete_XForms_SfAutoComplete_MaximumSuggestion) property. We can set the desire text for the displaying the Load more text with the property [`LoadMoreText`](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfAutoComplete.XForms.SfAutoComplete.html#Syncfusion_SfAutoComplete_XForms_SfAutoComplete_LoadMoreText).

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
                                     MultiSelectMode="Delimiter"
                                     Delimiter=","
                                     LoadMoreText="LOAD MORE"
                                     MaximumSuggestion="2">
            <autocomplete:SfAutoComplete.AutoCompleteSource>
               <ListCollection:List x:TypeArguments="x:String">
                    <x:String>Albania</x:String>
                    <x:String>Algeria</x:String>
                    <x:String>American Samoa</x:String>
                    <x:String>Andorra</x:String>
                    <x:String>Aruba</x:String>
                    <x:String>Angola</x:String>
                    <x:String>Argentina</x:String>
                    <x:String>Armenia</x:String>
                    <x:String>America</x:String>
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
                MultiSelectMode = MultiSelectMode.Delimiter,
                Delimiter = ",",
                LoadMoreText = "LOAD MORE",
                MaximumSuggestion = 2,
                AutoCompleteSource = new List<string>()
                {
                   "Albania",
                   "Algeria",
                   "American Samoa",
                   "Andorra",
                   "Aruba",
                   "Angola",
                   "Argentina",
                   "Armenia",
                   "America"
                }
            };

            stackLayout.Children.Add(autoComplete);
            this.Content = stackLayout;
        }
    }
}

{% endhighlight %}

{% endtabs %}

![Maximum display item with Load More option](images/Maximum-display-item-with-Expander/LoadMore.png)

## Dynamically Changing the Maximum Suggestion Count

You can dynamically change the maximum number of suggestions displayed by calling the [`LoadMore`](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfAutoComplete.XForms.SfAutoComplete.html#Syncfusion_SfAutoComplete_XForms_SfAutoComplete_LoadMore) method. This method can be called with or without an argument:

* Without an argument: Loads all remaining items
* With an argument: Loads the specified number of additional items
> **Note:** The [`LoadMore`](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfAutoComplete.XForms.SfAutoComplete.html#Syncfusion_SfAutoComplete_XForms_SfAutoComplete_LoadMore) method is supported only on iOS and Android platforms.

{% tabs %}
{% highlight c# %}

// without passing argument
autoComplete.LoadMore();

// with passing argument
autoComplete.LoadMore(5);

{% endhighlight %}
{% endtabs %}

## Customizing the Load More View

The [`SfAutoComplete`](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfAutoComplete.XForms.SfAutoComplete.html) control allows you to customize the appearance of the Load More option using the [`LoadMoreTemplate`](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfAutoComplete.XForms.SfAutoComplete.html#Syncfusion_SfAutoComplete_XForms_SfAutoComplete_LoadMoreTemplate) property.

The following example demonstrates how to create a custom Load More template:
{% tabs %}

{% highlight xaml %}

<ContentPage xmlns="http://xamarin.com/schemas/2014/forms"
             xmlns:x="http://schemas.microsoft.com/winfx/2009/xaml"
             xmlns:border="clr-namespace:Syncfusion.XForms.Border;assembly=Syncfusion.Core.XForms"
			 xmlns:ListCollection="clr-namespace:System.Collections.Generic;assembly=netstandard"
             xmlns:autocomplete="clr-namespace:Syncfusion.SfAutoComplete.XForms;assembly=Syncfusion.SfAutoComplete.XForms"
             x:Class="AutoComplete.MainPage">
  <StackLayout VerticalOptions="Start" HorizontalOptions="Start" Padding="30">
        <autocomplete:SfAutoComplete MaximumSuggestion="3"  HeightRequest="40" x:Name="autoComplete" Watermark="Enter Text">
            <autocomplete:SfAutoComplete.LoadMoreTemplate>
              <border:SfBorder BackgroundColor="#6200EE" BorderWidth="1" BorderColor="Lavender" CornerRadius="20,20,20,20">
                    <Label  TextColor="White"  HorizontalTextAlignment="Center" FontSize="15" FontAttributes="Bold" Text="Load More Template"></Label>
              </border:SfBorder>
             
            </autocomplete:SfAutoComplete.LoadMoreTemplate>
            <autocomplete:SfAutoComplete.AutoCompleteSource>
                <ListCollection:List x:TypeArguments="x:String">
                    <x:String>Albania</x:String>
                    <x:String>Algeria</x:String>
                    <x:String>American Samoa</x:String>
                    <x:String>Andorra</x:String>
                    <x:String>Aruba</x:String>
                    <x:String>Angola</x:String>
                    <x:String>Argentina</x:String>
                    <x:String>Armenia</x:String>
                    <x:String>America</x:String>
                </ListCollection:List>
        </autocomplete:SfAutoComplete.AutoCompleteSource>
       </autocomplete:SfAutoComplete>
    </StackLayout>
 </ContentPage>

{% endhighlight %}

{% highlight C# %}

 StackLayout stackLayout = new StackLayout()
            {
                VerticalOptions = LayoutOptions.Start,
                HorizontalOptions = LayoutOptions.Start,
                Padding = new Thickness(30)
            };
            Syncfusion.XForms.Border.SfBorder border = new Syncfusion.XForms.Border.SfBorder();
            border.BorderWidth = 1;
            border.BackgroundColor = Color.FromHex("#6200EE");
            border.BorderColor = Color.Lavender;
            border.CornerRadius = new Thickness(20, 20, 20, 20);
            var nameLabel = new Label { FontAttributes = FontAttributes.Bold, TextColor = Color.White, HorizontalTextAlignment = TextAlignment.Center, FontSize = 15, Text = "Load More Template" };
            border.Content = nameLabel;

            SfAutoComplete autoComplete = new SfAutoComplete()
            {
                HeightRequest = 40,
                MaximumSuggestion = 3,
                Watermark = "Enter Text",
                AutoCompleteSource = new List<string>()
                {
                   "Albania",
                   "Algeria",
                   "American Samoa",
                   "Andorra",
                   "Aruba",
                   "Angola",
                   "Argentina",
                   "Armenia",
                   "America"
                },

                LoadMoreTemplate = border

            };

            stackLayout.Children.Add(autoComplete);
            this.Content = stackLayout;

{% endhighlight %}

{% endtabs %}

![LoadMoreTemplate](images/Maximum-display-item-with-Expander/LoadMoreTemplate.png)

## Load More Button Tapped Event

The [`LoadMoreButtonTapped`](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfAutoComplete.XForms.SfAutoComplete.html#Syncfusion_SfAutoComplete_XForms_SfAutoComplete_LoadMoreButtonTapped) can be triggered only when you tap on the load more button.

{% tabs %}

{% highlight xaml %}

 <autocomplete:SfAutoComplete HeightRequest="40"
                              LoadMoreButtonTapped="AutoComplete_LoadMoreButtonTapped"
                              LoadMoreText="LOAD MORE"
                              MaximumSuggestion="3"/>

{% endhighlight %}

{% highlight c# %}
namespace AutocompleteSample
{
    public partial class MainPage : ContentPage
    {
        SfAutoComplete autoComplete;
        public MainPage()
        {
          autoComplete = new SfAutoComplete();
          autoComplete.LoadMoreButtonTapped += AutoComplete_LoadMoreButtonTapped;
          autoComplete.HeightRequest = 40;
          autoComplete.LoadMoreText = "Load More";
        }

        private void AutoComplete_LoadMoreButtonTapped(object sender, EventArgs e)
        {
            // Trigger when tap the load more button
        }
    }
}


{% endhighlight %}

{% endtabs %}

N> The [`LoadMoreButtonTapped`](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfAutoComplete.XForms.SfAutoComplete.html#Syncfusion_SfAutoComplete_XForms_SfAutoComplete_LoadMoreButtonTapped) event is supported only on the Android and iOS platforms.

N> You can refer to our [Xamarin AutoComplete](https://www.syncfusion.com/xamarin-ui-controls/xamarin-autocomplete) feature tour page for its groundbreaking feature representations. You can also explore our [Xamarin.Forms AutoComplete example](https://github.com/syncfusion/xamarin-demos/tree/master/Forms/AutoComplete) to knows the functionalities of each feature.