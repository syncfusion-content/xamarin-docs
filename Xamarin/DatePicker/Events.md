---
layout: post
title: DatePicker Events in Xamarin DatePicker control | Syncfusion
description: Learn here all about DatePicker Events support in Syncfusion Xamarin Date Picker (SfDatePicker) control and more.
platform: Xamarin
control: SfDatePicker
documentation: ug
---

# Events in Xamarin DatePicker (SfDatePicker)

Three events are used when the [`SfDatePicker`](https://help.syncfusion.com/cr/xamarin/Syncfusion.XForms.Pickers.SfDatePicker.html) is in [`Dialog`](https://help.syncfusion.com/cr/xamarin/Syncfusion.XForms.Pickers.PickerMode.html#Syncfusion_XForms_Pickers_PickerMode_Dialog) mode.

 * [`Opened`](https://help.syncfusion.com/cr/xamarin/Syncfusion.XForms.Pickers.SfDatePicker.html#Syncfusion_XForms_Pickers_SfDatePicker_Opened)
 * [`Closing`](https://help.syncfusion.com/cr/xamarin/Syncfusion.XForms.Pickers.SfDatePicker.html#Syncfusion_XForms_Pickers_SfDatePicker_Closing)
 * [`Closed`](https://help.syncfusion.com/cr/xamarin/Syncfusion.XForms.Pickers.SfDatePicker.html#Syncfusion_XForms_Pickers_SfDatePicker_Closed)

## Opened event

The [`Opened`](https://help.syncfusion.com/cr/xamarin/Syncfusion.XForms.Pickers.SfDatePicker.html#Syncfusion_XForms_Pickers_SfDatePicker_Opened) event occurs when the DatePicker is opened. 

## Closing event 

The [`Closing`](https://help.syncfusion.com/cr/xamarin/Syncfusion.XForms.Pickers.SfDatePicker.html#Syncfusion_XForms_Pickers_SfDatePicker_Closing) event occurs when the DatePicker closes.

Drop-down close can be restricted by setting `e.cancel` to true.

## Closed event

The [`Closed`](https://help.syncfusion.com/cr/xamarin/Syncfusion.XForms.Pickers.SfDatePicker.html#Syncfusion_XForms_Pickers_SfDatePicker_Closed) event was triggered, after the DatePicker was closed.

{% tabs %}

{% highlight xaml %}

    <?xml version="1.0" encoding="utf-8" ?>
    <ContentPage xmlns="http://xamarin.com/schemas/2014/forms"
                 xmlns:x="http://schemas.microsoft.com/winfx/2009/xaml"
                 xmlns:datePicker="clr-namespace:Syncfusion.XForms.Pickers;assembly=Syncfusion.SfPicker.XForms"
                 x:Class="DatePickerSample.MainPage">
    
     ...
    <datePicker:SfDatePicker x:Name="datePicker" PickerMode="Dialog"
                                 Opened="SfDatePicker_Opened"
                                 Closing="SfDatePicker_Closing"
                                 Closed="SfDatePicker_Closed">
            
    </datePicker:SfDatePicker>
    </ContentPage>


{% endhighlight %}

{% highlight C# %}
      
    public partial class MainPage : ContentPage
    {
        public MainPage()
        {
            InitializeComponent();
            datePicker.Opened += SfDatePicker_Opened;
            datePicker.Closing += SfDatePicker_Closing;
            datePicker.Closed += SfDatePicker_Closed;
        }
          private void SfDatePicker_Opened(object sender, EventArgs e)
        {

        }

        private void SfDatePicker_Closing(object sender, Syncfusion.XForms.Core.CancelEventArgs e)
        {
            //To restrict the datepicker get close, set e.Cancel to true.
            e.Cancel = true;
        }

        private void SfDatePicker_Closed(object sender, EventArgs e)
        {

        }
    }
    

{% endhighlight %}

{% endtabs %}


