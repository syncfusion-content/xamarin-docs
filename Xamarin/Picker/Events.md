---
layout: post
title: Events of Syncfusion Picker control for Xamarin.Forms
description: How to hook the events when picker is open and closed in the Dialog mode in Picker conrol for Xamarin.Forms.
platform: xamarin
control: SfPicker
documentation: ug
---

# Events in Syncfusion Picker

Three events have been used for a picker when it is in the `Dialog` mode. They are,

* Opened
* Closing
* Closed

## Opened event

The `Opened` event occurs when the picker is opened. 

## Closing event 

The `Closing` event raises when the picker gets closing. You can stop the picker close action by setting the `e.cancel` to true.

## Closed event

The `Closed` event was raised after the picker is closed.

{% tabs %} 

{% highlight xaml %} 

<?xml version="1.0" encoding="UTF-8"?>
<ContentPage xmlns="http://xamarin.com/schemas/2014/forms"
             xmlns:x="http://schemas.microsoft.com/winfx/2009/xaml"
             xmlns:d="http://xamarin.com/schemas/2014/forms/design"
             xmlns:syncfusion="clr-namespace:Syncfusion.SfPicker.XForms;assembly=Syncfusion.SfPicker.XForms"
             xmlns:mc="http://schemas.openxmlformats.org/markup-compatibility/2006"
             mc:Ignorable="d"
             x:Class="PickerClosingEventSample.MainPage">
             
              <ContentPage.Content>
                         <syncfusion:SfPicker Opened="picker_Opened" Closed="picker_Closed" Closing="picker_Closing">
                         ...
                        </syncfusion:SfPicker>
              </ContentPage.Content>

</ContentPage>

  
{% endhighlight %}

{% highlight C# %} 

using System;
using System.Collections.Generic;
using System.Collections.ObjectModel;
using System.ComponentModel;
using System.Linq;
using System.Text;
using System.Threading.Tasks;
using Xamarin.Forms;
namespace PickerClosingEventSample
  {   
   public partial class MainPage : ContentPage    
    {
        SfPicker picker = new SfPicker();

        public MainPage()
        {
         InitializeComponent();
         picker.Opened += picker_Opened;
         picker.Closing += picker_Closing;
         picker.Closed += picker_Closed;

        }

        private void picker_Opened(object sender, EventArgs e)
        {
          // handle the open action
        }

        private void Picker_Closing(object sender, Syncfusion.XForms.Core.CancelEventArgs e)
        {
           // stop the close action by setting the `e.cancel` to true.
        }

        private void picker_Closed(object sender, EventArgs e)
        {
           // hit after the picker is closed.
        }
    }
}
{% endhighlight %}

{% endtabs %}

N> View [sample](https://github.com/SyncfusionExamples/xamarin-sfpicker-examples)  in GitHub
