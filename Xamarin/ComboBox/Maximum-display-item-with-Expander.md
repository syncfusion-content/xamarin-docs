---
layout: post
title: Maximum display item with Expander in Xamarin ComboBox | Syncfusion
description: Learn here all about Maximum display item with Expander support in Syncfusion Xamarin ComboBox (SfComboBox) control and more.
platform: xamarin
control: SfComboBox
documentation: ug
---
# Maximum display item with Expander in Xamarin ComboBox (SfComboBox)

## Maximum display item with expander in Xamarin SfComboBox

Restrict the number of suggestions displayed and have the remaining items loaded by selecting the LoadMore. you can restrict the maximum suggestion to be displayed with the `MaximumSuggestion` property and also you can set the desire text for displaying the LoadMore text with the LoadMoreText` property.

{% tabs %}

{% highlight xaml %}

<?xml version="1.0" encoding="utf-8" ?>
<ContentPage xmlns="http://xamarin.com/schemas/2014/forms"
             xmlns:x="http://schemas.microsoft.com/winfx/2009/xaml"
             xmlns:comboBox="clr-namespace:Syncfusion.SfComboBox.XForms;assembly=Syncfusion.SfComboBox.XForms"
             xmlns:ListCollection="clr-namespace:System.Collections.Generic;assembly=netstandard"
             xmlns:local="clr-namespace:ComboBoxSample"
             x:Class="ComboBoxSample.MainPage">
    <StackLayout VerticalOptions="Start" 
                 HorizontalOptions="Start" 
                 Padding="30">
        <comboBox:SfComboBox HeightRequest="40"
                             MultiSelectMode="Delimiter"
                             Delimiter=","
                             LoadMoreText="LOAD MORE"
                             MaximumSuggestion="2">
            <comboBox:SfComboBox.ComboBoxSource>
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
            </comboBox:SfComboBox.ComboBoxSource>
        </comboBox:SfComboBox>
    </StackLayout>
</ContentPage>

{% endhighlight %}

{% highlight c# %}

using Syncfusion.SfComboBox.XForms;
using System.Collections.Generic;
using Xamarin.Forms;

namespace ComboBoxSample
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

            SfComboBox comboBox = new SfComboBox()
            {
                HeightRequest = 40,
                MultiSelectMode = MultiSelectMode.Delimiter,
                Delimiter = ",",
                LoadMoreText = "LOAD MORE",
                MaximumSuggestion = 2,
                ComboBoxSource = new List<string>()
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

            stackLayout.Children.Add(comboBox);
            this.Content = stackLayout;
        }
    }
}

{% endhighlight %}

{% endtabs %}


![Maximum display item with Expander](images/Maximum-display-item-with-Expander/LoadMore.png)

## Restricting the maximum display of items dynamically

You can restrict the maximum display of items dynamically by calling the `LoadMore` method. The user can dynamically change the maximum suggestion count by calling the LoadMore method by giving the maximum suggestion as the argument inside.

N> LoadMore method has enhanced only on iOS and Android platform.

{% tabs %}
{% highlight c# %}

// without passing argument
comboBox.LoadMore();

// with passing argument
comboBox.LoadMore(5);

{% endhighlight %}
{% endtabs %}

## Load More Button Tapped Event

The `LoadMoreButtonTapped` can be triggered only when you tap on the load more button.

{% tabs %}

{% highlight xaml %}

 <comboBox:SfComboBox HeightRequest="40"
                      LoadMoreButtonTapped="ComboBox_LoadMoreButtonTapped"
                      LoadMoreText="LOAD MORE"
                      MaximumSuggestion="3">

{% endhighlight %}

{% highlight c# %}
namespace ComboBoxSample
{
    public partial class MainPage : ContentPage
    {
        SfComboBox comboBox;
        public MainPage()
        {
          comboBox = new SfComboBox();
          comboBox.LoadMoreButtonTapped += ComboBox_LoadMoreButtonTapped;
          comboBox.HeightRequest = 40;
          comboBox.LoadMoreText = "Load More";
        }

        private void ComboBox_LoadMoreButtonTapped(object sender, EventArgs e)
        {
            // Trigger when tap the load more button
        }
    }
}


{% endhighlight %}

{% endtabs %}
