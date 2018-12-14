---
layout: post
title: Reveal height customization of Syncfusion Backdrop Page
description: How to customize a reveal height
platform: xamarin
control: SfBackdropPage
documentation: ug
---

# Reveal Height Customization

Essential Backdrop Page supports reveal height customization which is used, when you need to reveal the back layer and to limit the translate animation height of the front layer.It is illustrated as follows,

## Set reveal height of front layer

The revealing of back layer can be enabled by setting the [`IsBackLayerRevealed`](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfBackdrop.XForms~Syncfusion.XForms.Backdrop.SfBackdropPage~IsBackLayerRevealed.html) property to true.To know more about this,refer the [link](https://help.syncfusion.com/xamarin/sfbackdroppage/getting-started?cs-save-lang=1&cs-lang=csharp#reveal-and-conceal-the-back-layer).

{% tabs %} 

{% highlight xaml %} 

<backdrop:SfBackdropPage.FrontLayer>
        <backdrop:BackdropFrontLayer RevealedHeight="30">
            <Grid />
        </backdrop:BackdropFrontLayer>
</backdrop:SfBackdropPage.FrontLayer> 


{% endhighlight %}

{% highlight C# %} 

this.FrontLayer = new BackdropFrontLayer()
{
	Content = new Grid(),
	RevealedHeight = 30
};

{% endhighlight %}

{% endtabs %}

## Backdrop Page revealing option

The backdrop page allows the user to indicate how the back layer gets revealed using the [`BackLayerRevealOption`](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfBackdrop.XForms~Syncfusion.XForms.Backdrop.SfBackdropPage~BackLayerRevealOption.html) property.

### Reveal based on back layer content

Revealing height depends on the content of back layer when setting the [`BackLayerRevealOption`](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfBackdrop.XForms~Syncfusion.XForms.Backdrop.SfBackdropPage~BackLayerRevealOption.html) property as `Auto`.

If the content of back layer exceeds the height of the screen,It reveals the back layer based on value of [`RevealedHeight`](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfBackdrop.XForms~Syncfusion.XForms.Backdrop.SfBackdropPage~BackLayerRevealOption.html) property.

{% tabs %} 

{% highlight xaml %} 

<backdrop:SfBackdropPage
    xmlns="http://xamarin.com/schemas/2014/forms"
    xmlns:x="http://schemas.microsoft.com/winfx/2009/xaml"
    xmlns:backdrop="clr-namespace:Syncfusion.XForms.Backdrop;assembly=Syncfusion.SfBackdrop.XForms"
    x:Class="BackdropGettingStarted.BackdropSamplePage"
    BackLayerRevealOption="Auto">
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
        }
    }
}

{% endhighlight %}

{% endtabs %}

### Reveal based on inbuilt property

Revealing is done based on [`RevealedHeight`](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfBackdrop.XForms~Syncfusion.XForms.Backdrop.SfBackdropPage~BackLayerRevealOption.html) property when setting the [`BackLayerRevealOption`](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfBackdrop.XForms~Syncfusion.XForms.Backdrop.SfBackdropPage~BackLayerRevealOption.html) property as `Fill`.

{% tabs %} 

{% highlight xaml %} 

<backdrop:SfBackdropPage
    xmlns="http://xamarin.com/schemas/2014/forms"
    xmlns:x="http://schemas.microsoft.com/winfx/2009/xaml"
    xmlns:backdrop="clr-namespace:Syncfusion.XForms.Backdrop;assembly=Syncfusion.SfBackdrop.XForms"
    x:Class="BackdropGettingStarted.BackdropSamplePage"
    BackLayerRevealOption="Fill">
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
            this.BackLayerRevealOption = RevealOption.Fill;
        }
    }
}

{% endhighlight %}

{% endtabs %}
