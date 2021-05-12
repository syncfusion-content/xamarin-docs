---
layout: post
title: Corner Shape Customization in Xamarin Backdrop Page | Syncfusion
description: Learn here all about Corner Shape Customization support in Syncfusion Xamarin Backdrop Page (SfBackdropPage) control and more.
platform: xamarin
control: SfBackdropPage
documentation: ug
---

# Corner Shape Customization in Xamarin Backdrop Page (SfBackdropPage)

Backdrop allows to customize the shapes on the top corners of the front layer. Curved and cut (flat) shape options are available , it can be switched by setting [`EdgeShape`](https://help.syncfusion.com/cr/xamarin/Syncfusion.XForms.Backdrop.BackdropFrontLayer.html#Syncfusion_XForms_Backdrop_BackdropFrontLayer_EdgeShape) property of the front layer.

![CornerType image](CornerShape_images/CornerType.png)

>**NOTE**
The backdrop can only be shaped on the top left and top right corners.

>**NOTE**
If you need to set background color for the back layer, set the `BackgroundColor` property to the content of the BackdropBackLayer instead of BackdropBackLayer itself.

Both the side of the corner radius can be customized separately by setting [LeftCornerRadius](https://help.syncfusion.com/cr/xamarin/Syncfusion.XForms.Backdrop.BackdropFrontLayer.html#Syncfusion_XForms_Backdrop_BackdropFrontLayer_LeftCornerRadius) and [RightCornerRadius](https://help.syncfusion.com/cr/xamarin/Syncfusion.XForms.Backdrop.BackdropFrontLayer.html#Syncfusion_XForms_Backdrop_BackdropFrontLayer_RightCornerRadius) properties of [BackdropFrontLayer](https://help.syncfusion.com/cr/xamarin/Syncfusion.XForms.Backdrop.BackdropFrontLayer.html).

{% tabs %} 

{% highlight xaml %} 

<backdrop:SfBackdropPage.FrontLayer>
        <backdrop:BackdropFrontLayer LeftCornerRadius="30" RightCornerRadius="0" EdgeShape="Flat">
            <Grid />
        </backdrop:BackdropFrontLayer>
</backdrop:SfBackdropPage.FrontLayer> 


{% endhighlight %}

{% highlight C# %} 

this.FrontLayer = new BackdropFrontLayer()
{
	Content = new Grid(),
	LeftCornerRadius = 30,
	RightCornerRadius = 0,
	EdgeShape = EdgeShape.Flat
};

{% endhighlight %}

{% endtabs %}




