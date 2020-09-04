---
layout: post
title: Reveal height customization of Syncfusion Backdrop Page
description: How to customize a reveal height
platform: xamarin
control: SfBackdropPage
documentation: ug
---

# Reveal Height Customization

When revealing the [`back layer`](https://help.syncfusion.com/xamarin/sfbackdroppage/getting-started#reveal-and-conceal-the-back-layer), the front layer will be moved downwards. By setting the [`BackLayerRevealOption`](https://help.syncfusion.com/cr/xamarin/Syncfusion.XForms.Backdrop.SfBackdropPage.html#Syncfusion_XForms_Backdrop_SfBackdropPage_BackLayerRevealOption) property of backdrop, you can customize how far the front layer can be moved from the header when revealing the back layer.

The following options are provided to move the front layer:

[`Fill`](https://help.syncfusion.com/cr/xamarin/Syncfusion.XForms.Backdrop.RevealOption.html) – Moves the front layer downwards to the entire height of the page excluding the [`RevealedHeight`](https://help.syncfusion.com/cr/xamarin/Syncfusion.XForms.Backdrop.BackdropFrontLayer.html#Syncfusion_XForms_Backdrop_BackdropFrontLayer_RevealedHeight).

[`Auto`](https://help.syncfusion.com/cr/xamarin/Syncfusion.XForms.Backdrop.RevealOption.html) – Moves the front layer downwards to the height of the back layer content.

{% tabs %} 

{% highlight xaml %} 

<?xml version="1.0" encoding="UTF-8"?>
<backdrop:SfBackdropPage
    xmlns="http://xamarin.com/schemas/2014/forms"
    xmlns:x="http://schemas.microsoft.com/winfx/2009/xaml"
    xmlns:backdrop="clr-namespace:Syncfusion.XForms.Backdrop;assembly=Syncfusion.SfBackdrop.XForms"
    x:Class="BackdropGettingStarted.BackdropSamplePage"
	BackLayerRevealOption="Auto">
	<backdrop:SfBackdropPage.FrontLayer>
        <backdrop:BackdropFrontLayer>
            <Grid />
        </backdrop:BackdropFrontLayer>
    </backdrop:SfBackdropPage.FrontLayer>
</backdrop:SfBackdropPage>


{% endhighlight %}

{% highlight C# %} 

using Syncfusion.XForms.Backdrop;
namespace BackdropGettingStarted
{
    public class BackdropSamplePage : SfBackdropPage
    {
        public BackdropSamplePage()
        {
            this.BackLayerRevealOption = RevealOption.Auto;
            this.FrontLayer = new BackdropFrontLayer()
            {
                Content = new Grid()
            };
        }
    }
}

{% endhighlight %}

{% endtabs %}

![Revealing height customization](RevealingHeight_images/Revealing_height.jpg)