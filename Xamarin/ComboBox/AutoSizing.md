---
layout: post
title: AutoSizing in Xamarin ComboBox control | Syncfusion
description: Learn here all about AutoSizing support in Syncfusion Xamarin ComboBox (SfComboBox) control and more.
platform: Xamarin
control: SfComboBox
documentation: ug
---

# AutoSizing in Xamarin ComboBox (SfComboBox)

AutoSizing can be enabled in [`SfComboBox`](https://help.syncfusion.com/cr/xamarin/Syncfusion.XForms.ComboBox.SfComboBox.html) control so that the control will extend its layout based on the text input.

[`EnableAutoSize`](https://help.syncfusion.com/cr/xamarin/Syncfusion.XForms.ComboBox.SfComboBox.html#Syncfusion_XForms_ComboBox_SfComboBox_EnableAutoSize) property is used to enable the autoSizing in [`SfComboBox`](https://help.syncfusion.com/cr/xamarin/Syncfusion.XForms.ComboBox.SfComboBox.html) control. To enable the API, you need to set the [`MultiSelectMode`](https://help.syncfusion.com/cr/xamarin/Syncfusion.XForms.ComboBox.SfComboBox.html#Syncfusion_XForms_ComboBox_SfComboBox_MultiSelectMode) as [`Token`](https://help.syncfusion.com/cr/xamarin/Syncfusion.XForms.ComboBox.MultiSelectMode.html#Syncfusion_XForms_ComboBox_MultiSelectMode_Token) and [`TokensWrapMode`](https://help.syncfusion.com/cr/xamarin/Syncfusion.XForms.ComboBox.SfComboBox.html#Syncfusion_XForms_ComboBox_SfComboBox_TokensWrapMode) as [`Wrap`](https://help.syncfusion.com/cr/xamarin/Syncfusion.XForms.ComboBox.TokensWrapMode.html#Syncfusion_XForms_ComboBox_TokensWrapMode_Wrap). The default value of [`EnableAutoSize`](https://help.syncfusion.com/cr/xamarin/Syncfusion.XForms.ComboBox.SfComboBox.html#Syncfusion_XForms_ComboBox_SfComboBox_EnableAutoSize) is false.

{% tabs %}
{% highlight xaml %}

<?xml version="1.0" encoding="utf-8"?>
<ContentPage xmlns="http://xamarin.com/schemas/2014/forms"
             xmlns:x="http://schemas.microsoft.com/winfx/2009/xaml"
             xmlns:d="http://xamarin.com/schemas/2014/forms/design"
              xmlns:ListCollection="clr-namespace:System.Collections.Generic;assembly=netstandard"
             xmlns:combobox="clr-namespace:Syncfusion.XForms.ComboBox;assembly=Syncfusion.SfComboBox.XForms"
             xmlns:mc="http://schemas.openxmlformats.org/markup-compatibility/2006"
             mc:Ignorable="d" x:Class="LayoutsExample.MainPage">
    <StackLayout VerticalOptions="Start" HorizontalOptions="Start" Padding="30">
        <combobox:SfComboBox x:Name="comboBox" EnableAutoSize="True" MultiSelectMode="Token" TokensWrapMode="Wrap">
            <combobox:SfComboBox.ComboBoxSource>
                <ListCollection:List x:TypeArguments="x:String">
                    <x:String>Uganda</x:String>
                    <x:String>Ukraine</x:String>
                    <x:String>United Arab Emirates</x:String>
                    <x:String>United Kingdom</x:String>
                    <x:String>United States</x:String>
                </ListCollection:List>
            </combobox:SfComboBox.ComboBoxSource>
        </combobox:SfComboBox>
    </StackLayout>
</ContentPage>
		  
{% endhighlight %}
{% highlight c# %}
	
using System;
using System.Collections.Generic;
using System.ComponentModel;
using System.Linq;
using System.Text;
using System.Threading.Tasks;
using Syncfusion.XForms.ComboBox;
using Xamarin.Forms;

namespace LayoutsExample
{
    // Learn more about making custom code visible in the Xamarin.Forms previewer
    // by visiting https://aka.ms/xamarinforms-previewer
    [DesignTimeVisible(false)]
    public partial class MainPage : ContentPage
    {
        public MainPage()
        {
            InitializeComponent();

            StackLayout layout = new StackLayout()
            {
                VerticalOptions = LayoutOptions.Start,
                HorizontalOptions = LayoutOptions.Start,
                Padding = new Thickness(30)
            };
            List<String> countryNames = new List<String>();
            countryNames.Add("Uganda");
            countryNames.Add("Ukraine");
            countryNames.Add("United Arab Emirates");
            countryNames.Add("United Kingdom");
            countryNames.Add("United States");

            SfComboBox comboBox = new SfComboBox();
            comboBox.HeightRequest = 40;
            comboBox.ComboBoxSource = countryNames;
            comboBox.EnableAutoSize = true;
            comboBox.MultiSelectMode = MultiSelectMode.Token;
            comboBox.TokensWrapMode = TokensWrapMode.Wrap;
            layout.Children.Add(comboBox);
            Content = layout;
        }
    }
}
	 
{% endhighlight %}
{% endtabs %}

![EnableAutoSize image](images/AutoSizing/AutoSizing.png)
