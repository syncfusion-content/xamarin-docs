---
layout: post
title: Show a dialog using Syncfusion DatePicker for Xamarin.Forms
description: Learn how to show the DatePicker as dialog mode using button click in syncfusion DatePicker for Xamarin.Forms (SfDatePicker)
platform: Xamarin
control: DatePicker
documentation: ug
---

# How to show as a Dialog in Xamarin.Forms DatePicker(SfPicker)

DatePicker can be rendered as a dialog by setting the [`SfDatePicker.PickerMode`](https://help.syncfusion.com/cr/xamarin/Syncfusion.XForms.Pickers.PickerHelper.PickerBase.html#Syncfusion_XForms_Pickers_PickerHelper_PickerBase_PickerMode) property to [`Dialog`](https://help.syncfusion.com/cr/xamarin/Syncfusion.XForms.Pickers.PickerMode.html#Syncfusion_XForms_Pickers_PickerMode_Dialog). The default value of [`SfDatePicker.PickerMode`](https://help.syncfusion.com/cr/xamarin/Syncfusion.XForms.Pickers.PickerHelper.PickerBase.html#Syncfusion_XForms_Pickers_PickerHelper_PickerBase_PickerMode) property is [`"Default"`](https://help.syncfusion.com/cr/xamarin/Syncfusion.XForms.Pickers.PickerMode.html#Syncfusion_XForms_Pickers_PickerMode_Default). 

{% tabs %}

{% highlight xaml %}

<?xml version="1.0" encoding="utf-8" ?>
<ContentPage xmlns="http://xamarin.com/schemas/2014/forms"
             xmlns:x="http://schemas.microsoft.com/winfx/2009/xaml"
             xmlns:local="clr-namespace:DatePickerSample"
             xmlns:syncfusion="clr-namespace:Syncfusion.XForms.Pickers;assembly=Syncfusion.SfPicker.XForms"
             x:Class="DatePickerSample.MainPage">
    <ContentPage.Content>
        <syncfusion:SfDatePicker x:Name="DatePicker"
                                 PickerMode="Dialog"/>
    </ContentPage.Content>
</ContentPage>

{% endhighlight %}

{% highlight c# %}

using Syncfusion.XForms.Pickers;
using Xamarin.Forms;

namespace DatePickerSample
{
    public partial class MainPage : ContentPage
    {
        public MainPage()
        {
            InitializeComponent();
            SfDatePicker datePicker = new SfDatePicker()
            {
                PickerMode = DatePickerMode.Dialog
            };

            this.Content = datePicker;
        }
    }
}

{% endhighlight %}

{% endtabs %}

The DatePicker can be opened programmatically by setting the [`SfDatePicker.IsOpen`](https://help.syncfusion.com/cr/xamarin/Syncfusion.XForms.Pickers.PickerHelper.PickerBase.html#Syncfusion_XForms_Pickers_PickerHelper_PickerBase_IsOpen) property to true. Default value of [`SfDatePicker.IsOpen`](https://help.syncfusion.com/cr/xamarin/Syncfusion.XForms.Pickers.PickerHelper.PickerBase.html#Syncfusion_XForms_Pickers_PickerHelper_PickerBase_IsOpen) is "false".

Note: This property is automatically changed to false when you close the dialog by clicking outside of the dialog.

{% tabs %}

{% highlight xaml %}

<?xml version="1.0" encoding="utf-8" ?>
<ContentPage xmlns="http://xamarin.com/schemas/2014/forms"
             xmlns:x="http://schemas.microsoft.com/winfx/2009/xaml"
             xmlns:local="clr-namespace:DatePickerSample"
             xmlns:syncfusion="clr-namespace:Syncfusion.XForms.Pickers;assembly=Syncfusion.SfPicker.XForms"
             x:Class="DatePickerSample.MainPage">
    <ContentPage.Content>
        <Grid>
        <syncfusion:SfDatePicker x:Name="datepicker"
                                 PickerMode="Dialog"/>
        <Button Text="Open Picker" 
                x:Name="pickerButton"
                Clicked="Button_Clicked"
                HorizontalOptions="Center"
                VerticalOptions="Center"
                HeightRequest="50" 
                WidthRequest="100"/>
        </Grid>
    </ContentPage.Content>
</ContentPage>

{% endhighlight %}

{% highlight c# %}

using Xamarin.Forms;

namespace DatePickerSample
{
    public partial class MainPage : ContentPage
    {
        public MainPage()
        {
            InitializeComponent();
        }

        private void Button_Clicked(object sender, System.EventArgs e)
        {
            datepicker.IsOpen = true;
        }
    }
}

{% endhighlight %}

{% endtabs %}

