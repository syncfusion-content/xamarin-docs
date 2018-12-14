---
layout: post
title: Corner shape customization of Syncfusion Backdrop Page
description: How to customize a corner shape
platform: xamarin
control: SfBackdropPage
documentation: ug
---

# Corner Shape Customization

Essential Backdrop Page supports corner shape customization that are illustrated as follows.

## Adjust the shape of front layer

The SfBackdropPage allows to adjust the edge shape of the front layer which can be adjusted using the [`EdgeShape`](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfBackdrop.XForms~Syncfusion.XForms.Backdrop.BackdropFrontLayer~EdgeShape.html) property.

### Customize the corner shape of front layer

The [`EdgeShape`](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfBackdrop.XForms~Syncfusion.XForms.Backdrop.BackdropFrontLayer~EdgeShape.html) property of the SfBackdropPage allows the user to set the curve or flat shape to the edge of the front layer.

The SfBackdropPage allows to adjust the corner radius of the front layer. The right and left corner radius of the front layer in the SfBackdropPage can be set by using the [RightCornerRadius](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfBackdrop.XForms~Syncfusion.XForms.Backdrop.BackdropFrontLayer~RightCornerRadius.html) and [LeftCornerRadius](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfBackdrop.XForms~Syncfusion.XForms.Backdrop.BackdropFrontLayer~LeftCornerRadius.html) property.

And also, corner radius property is applicable even when the [`EdgeShape`](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfBackdrop.XForms~Syncfusion.XForms.Backdrop.BackdropFrontLayer~EdgeShape.html) property set to curve or flat.

{% tabs %} 

{% highlight xaml %} 

<backdrop:SfBackdropPage.FrontLayer>
        <backdrop:BackdropFrontLayer LeftCornerRadius="0" RightCornerRadius="30" EdgeShape="Curve">
            <Grid />
        </backdrop:BackdropFrontLayer>
</backdrop:SfBackdropPage.FrontLayer> 


{% endhighlight %}

{% highlight C# %} 

this.FrontLayer = new BackdropFrontLayer()
{
	Content = new Grid(),
	LeftCornerRadius = 0,
	RightCornerRadius = 30,
	EdgeShape = EdgeShape.Curve
};

{% endhighlight %}

{% endtabs %}

>**NOTE**
Flat type of [`EdgeShape`](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfBackdrop.XForms~Syncfusion.XForms.Backdrop.BackdropFrontLayer~EdgeShape.html) property is available, but feature is not available in UWP platform.



