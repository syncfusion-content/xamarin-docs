---
layout: post
title: LoadMore in Syncfusion SfAutoComplete control for Xamarin.Forms
description: This section will deswcribe about how to restrict maximum suggestion to be displayed in Xamarin.Forms SfAutoComplete.
platform: xamarin
control: SfAutoComplete
documentation: ug
---
# Maximum Display Item with Expander

## Maximum display item with expander in Xamarin SfAutoComplete

Restrict the number of suggestions displayed and have the remaining items loaded by selecting LoadMore.We can restrict maximum suggestion to be displayed with the `MaximumSuggestion` property. We can set the desire text for the displaying the Load more text with the property `LoadMoreText`.

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

![Maximum display item with Expander](images/Maximum-display-item-with-Expander/LoadMore.png)

## Restricting the maximum display of item dynamically

We can restrict the maximum display of items dynamically by calling `LoadMore` method. The user can dynamically change the maximum suggestion count by calling LoadMore method by giving the maximum suggestion as the argument inside.

N> LoadMore method has enhanced only on iOS and Android platform.

{% tabs %}
{% highlight c# %}

// without passing argument
autoComplete.LoadMore();

// with passing argument
autoComplete.LoadMore(5);

{% endhighlight %}
{% endtabs %}

## Load more view customization

`SfAutoComplete` allows customizing User Interface(UI) of Load More view.
To customize the load more text, add the custom UI in the `LoadMoreTemplate` API in SfAutoComplete, as shown in the following code snippet.

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

The `LoadMoreButtonTapped` can be triggered only when you tap on the load more button.

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

N> The `LoadMoreButtonTapped` event is supported only on the Android and iOS platforms.

N> You can refer to our [Xamarin AutoComplete](https://www.syncfusion.com/xamarin-ui-controls/xamarin-autocomplete) feature tour page for its groundbreaking feature representations. You can also explore our [Xamarin.Forms AutoComplete example](https://github.com/syncfusion/xamarin-demos/tree/master/Forms/AutoComplete) to knows the functionalities of each feature.