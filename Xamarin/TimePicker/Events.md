---
layout: post
title: TimePicker Events in Xamarin TimePicker control | Syncfusion
description: Learn here all about TimePicker Events support in Syncfusion Xamarin Time Picker (SfTimePicker) control and more.
platform: Xamarin
control: SfTimePicker
documentation: ug
---

# Events in Xamarin TimePicker (SfTimePicker)

Three events have been used for the SfTimePicker when it is in the Dialog mode. 

 * Opened
 * Closing
 * Closed

## Opened event

The `Opened` event occurs when the SfTimePicker is opened. 

## Closing event 

The `Closing` event occurs when the SfTimePicker gets closing. 
Dropdown close can be restricted by setting `e.cancel` to true.

## Closed event

The `Closed` event was raised after the SfTimePicker is closed.

{% tabs %}

{% highlight xaml %}

    <?xml version="1.0" encoding="utf-8" ?>
    <ContentPage xmlns="http://xamarin.com/schemas/2014/forms"
                 xmlns:x="http://schemas.microsoft.com/winfx/2009/xaml"
                 xmlns:timePicker="clr-namespace:Syncfusion.XForms.Pickers;assembly=Syncfusion.SfPicker.XForms"
                 x:Class="TimePickerSample.MainPage">
    
     ...
     <timePicker:SfTimePicker x:Name="timePicker"                                          PickerMode="Dialog"
                                 Opened="TimePicker_Opened" 
                                 Closing="TimePicker_Closing"
                                 Closed="TimePicker_Closed"
                                 >
        </timePicker:SfTimePicker>
    </ContentPage>


{% endhighlight %}

{% highlight C# %}
      
      public partial class MainPage : ContentPage
    {
        public MainPage()
        {
            InitializeComponent();
            timePicker.Opened += TimePicker_Opened;
            timePicker.Closing += TimePicker_Closing;
            timePicker.Closed += TimePicker_Closed;
        }

       
        private void TimePicker_Opened(object sender, EventArgs e)
        {
        }

        private void TimePicker_Closing(object sender, Syncfusion.XForms.Core.CancelEventArgs e)
        {
            //To restrict the timepicker get close, set e.Cancel to true.
            e.Cancel = true;
        }

        private void TimePicker_Closed(object sender, EventArgs e)
        {
        }


{% endhighlight %}

{% endtabs %}


