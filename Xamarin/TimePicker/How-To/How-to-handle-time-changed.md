---
layout: post
title: Events using Syncfusion TimePicker for Xamarin.Forms
description: Learn how to perform an operation while changing its time in yncfusion TimePicker for Xamarin.Forms.
platform: Xamarin
control: TimePicker
documentation: ug
---

# How to handle time changed using the TimeSelected event
You can perform an operation when selecting time using the `TimeSelected` event. The TimeSelected event returns the following arguments:

<table>
<tr>
<th>Members</th>
<th>Description</th>
</tr>
<tr>
<td>NewValue</td>
<td>Shows recently selected time in TimePicker.</td>
</tr>
<tr>
<td>OldValue</td>
<td>Shows previously selected time in TimePicker.</td>
</tr>
</table>

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
                                 TimeSelected="TimePicker_TimeSelected"/>
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
        SfTimePicker TimePicker;
        public MainPage()
        {
            InitializeComponent();
            TimePicker = new SfTimePicker();
            TimePicker.TimeSelected += TimePicker_TimeSelected;
            this.Content = TimePicker;
        }

        private void TimePicker_TimeSelected(object sender, TimeChangedEventArgs e)
        {
           DisplayAlert("TimeSelected", "NewValue: " + e.NewValue + "\n" + "OldValue: " + e.OldValue, "Ok");
        }
    }
}

{% endhighlight %}
{% endtabs %}

![Event](images/Event.png)

