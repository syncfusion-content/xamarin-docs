---
layout: post
title: Reveal and conceal event of Syncfusion Backdrop Page
description: How to hook the event when backdrop page is revealed and concealed.
platform: xamarin
control: SfBackdropPage
documentation: ug
---

# Events

## BackLayerStateChanged event

`BackLayerStateChanged` event is triggered when the backdrop front layer page is revealed and concealed. The event gets triggered when [IsBackLayerRevealed](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfBackdrop.XForms~Syncfusion.XForms.Backdrop.SfBackdropPage~IsBackLayerRevealed.html)  gets changed dynamically, when revealing and concealing the front layer page on swiping and by touch interaction when clicking the tool bar icon.

{% tabs %} 

{% highlight xaml %} 

<?xml version="1.0" encoding="UTF-8"?>
<backdrop:SfBackdropPage
    xmlns="http://xamarin.com/schemas/2014/forms"
    xmlns:x="http://schemas.microsoft.com/winfx/2009/xaml"
    xmlns:backdrop="clr-namespace:Syncfusion.XForms.Backdrop;assembly=Syncfusion.SfBackdrop.XForms"
    x:Class="BackDropSample.MainPage"
    Title="Menu" x:Name="backdrop" BackLayerStateChanged="BackLayerStateChanged" >
  
{% endhighlight %}

{% highlight C# %} 

public MainPage()
    {
        InitializeComponent();
        backdrop.BackLayerStateChanged += BackLayerStateChanged;
    }
void BackLayerStateChanged(object sender, System.EventArgs e)
    {
           
    }
{% endhighlight %}

{% endtabs %}
