---
layout: post
title: TimePicker as dialog using Syncfusion TimePicker for Xamarin.Forms
description:  Learn how to show TimePicker as dialog using button in Syncfusion TimePicker control for Xamarin.Forms
platform: Xamarin
control: TimePicker
documentation: ug
---

# How to show as a Dialog

TimePicker can be rendered as a dialog by setting the`SfTimePicker.PickerMode` property to Dialog. Default value of the `SfTimePicker.PickerMode` property is "Default". 

{% tabs %}
{% highlight xaml %}

<?xml version="1.0" encoding="utf-8" ?>
<ContentPage xmlns="http://xamarin.com/schemas/2014/forms"
             xmlns:x="http://schemas.microsoft.com/winfx/2009/xaml"
             xmlns:local="clr-namespace:TimePickerSample"
             xmlns:syncfusion="clr-namespace:Syncfusion.XForms.Pickers;assembly=Syncfusion.SfPicker.XForms"
             x:Class="TimePickerSample.MainPage">
    <ContentPage.Content>
        <syncfusion:SfTimePicker x:Name="timePicker"
                                 PickerMode="Dialog"/>
    </ContentPage.Content>
</ContentPage>

{% endhighlight %}

{% highlight c# %}

using Syncfusion.XForms.Pickers;
using Xamarin.Forms;

namespace TimePickerSample
{
    public partial class MainPage : ContentPage
    {
        public MainPage()
        {
            InitializeComponent();
            SfTimePicker timePicker = new SfTimePicker()
            {
                PickerMode = timePickerMode.Dialog
            };

            this.Content = timePicker;
        }
    }
}

{% endhighlight %}
{% endtabs %}

The TimePicker can be opened programmatically by setting the `SfTimePicker.IsOpen` property to true. Default value of `SfTimePicker.IsOpen` is "false".

Note: This property is automatically changed to false when you close the dialog by clicking outside of the dialog.

{% tabs %}
{% highlight xaml %}

<?xml version="1.0" encoding="utf-8" ?>
<ContentPage xmlns="http://xamarin.com/schemas/2014/forms"
             xmlns:x="http://schemas.microsoft.com/winfx/2009/xaml"
             xmlns:local="clr-namespace:TimePickerSample"
             xmlns:syncfusion="clr-namespace:Syncfusion.XForms.Pickers;assembly=Syncfusion.SfPicker.XForms"
             x:Class="TimePickerSample.MainPage">
    <ContentPage.Content>
        <Grid>
        <syncfusion:SfTimePicker x:Name="timePicker"
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

namespace TimePickerSample
{
    public partial class MainPage : ContentPage
    {
        public MainPage()
        {
            InitializeComponent();
        }

        private void Button_Clicked(object sender, System.EventArgs e)
        {
            timePicker.IsOpen = true;
        }
    }
}

{% endhighlight %}
{% endtabs %}