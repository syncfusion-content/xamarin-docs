---
layout: post
title: Events in Xamarin Backdrop Page control | Syncfusion
description: Learn here all about Events support in Syncfusion Xamarin Backdrop Page (SfBackdropPage) control and more.
platform: xamarin
control: SfBackdropPage
documentation: ug
---

# Events in Xamarin Backdrop Page (SfBackdropPage)

## BackLayerStateChanged event

The `BackLayerStateChanged` event occurs when the backdrop page back layer is revealed and concealed. The event occurs in the cases mentioned in this [documentation](https://help.syncfusion.com/xamarin/sfbackdroppage/getting-started#reveal-and-conceal-the-back-layer).

{% tabs %} 

{% highlight xaml %} 

<?xml version="1.0" encoding="UTF-8"?>
<backdrop:SfBackdropPage
    xmlns="http://xamarin.com/schemas/2014/forms"
    xmlns:x="http://schemas.microsoft.com/winfx/2009/xaml"
    xmlns:backdrop="clr-namespace:Syncfusion.XForms.Backdrop;assembly=Syncfusion.SfBackdrop.XForms"
    x:Class="BackdropGettingStarted.MainPage"
    Title="Menu"
    BackLayerStateChanged="BackLayerStateChanged" >
  
{% endhighlight %}

{% highlight C# %} 

public MainPage()
    {
        InitializeComponent();
        this.BackLayerStateChanged += BackLayerStateChanged;
    }

private void BackLayerStateChanged(object sender, System.EventArgs e)
    {
        // handle event action.
    }
{% endhighlight %}

{% endtabs %}
