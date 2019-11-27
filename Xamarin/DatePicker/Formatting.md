---
layout: post
title: Format using Syncfusion DatePicker for Xamarin.Forms
description: This section explains the way to give the different date formats to the Syncfusion DatePicker control for Xamarin.Forms  
platform: Xamarin
control: Picker
documentation: ug
---


# Format

Format is a way to represent the value of the date in a different string format.

By default, the DatePicker’s format is "DateFormat.M_d_yyyy".

The following example demonstrates the DatePicker with the custom format DateFormat.yyyy-MM-dd.

{% tabs %}
{% highlight xaml %}

<?xml version="1.0" encoding="utf-8" ?>
<ContentPage xmlns="http://xamarin.com/schemas/2014/forms"
             xmlns:x="http://schemas.microsoft.com/winfx/2009/xaml"
             xmlns:local="clr-namespace:DatePickerSample"
             xmlns:syncfusion="clr-namespace:Syncfusion.XForms.Pickers;assembly=Syncfusion.SfPicker.XForms"
             x:Class="DatePickerSample.MainPage">
    <ContentPage.Content>
        <syncfusion:SfDatePicker x:Name="datepicker"
                                 Format="yyyy_MM_dd"/>
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
                Format = DateFormat.yyyy_MM_dd
            };

            this.Content = datePicker;
        }
    }
}

{% endhighlight %}
{% endtabs %}

![Format of SfDatePicker](images/Format_DatePicker.png)