---
layout: post
title: Interval of Syncfusion.Xamarin.Forms TimePicker
description: How to set interval between hours, minutes and seconds of the Syncfusion.Xamarin.Forms TimePicker control.
platform: Xamarin
control: TimePicker
documentation: ug
---

# How to set an interval

## How to set an interval between hours

TimePicker provides an option to give an interval between hours using the `SfTimePicker.HourInterval` property.

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
                                 HourInterval="2"/>
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
                HourInterval = 2
            };

            this.Content = timePicker;
        }
    }
}

{% endhighlight %}

{% endtabs %}

## How to set an interval between minutes

TimePicker provides an option to give an interval between minutes using the `SfTimePicker.MinuteInterval` property.

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
                                 MinuteInterval="2"/>
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
                MinuteInterval = 2
            };

            this.Content = timePicker;
        }
    }
}

{% endhighlight %}

{% endtabs %}

## How to set an interval between seconds

TimePicker provides an option to give an interval between seconds using the `SfTimePicker.SecondInterval` property.

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
                                 SecondInterval="2"/>
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
                SecondInterval = 2
            };

            this.Content = timePicker;
        }
    }
}

{% endhighlight %}
{% endtabs %}

![TimeInterval](images/TimeInterval.png)