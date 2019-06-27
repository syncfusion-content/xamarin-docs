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

`BackLayerStateChanged` event is triggered when the backdrop page back layer is revealed and concealed. The event gets triggered in the following cases mentioned in this [link](https://help.syncfusion.com/xamarin/sfbackdroppage/getting-started#reveal-and-conceal-the-back-layer).

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
        // TODO: handle event action.
    }
{% endhighlight %}

{% endtabs %}
