---

layout: post
title: ToolTip in Xamarin Rating control | Syncfusion
description: Learn here all about ToolTip support in Syncfusion Xamarin Rating (SfRating) control, its elements and more.
platform: Xamarin
control: Rating
documentation: ug

---

# ToolTip in Xamarin Rating (SfRating)

Tooltip provides additional information about objects that are unfamiliar to users and are not directly displayed in UI. In the Xamarin.Forms SfRating control, tooltip shows the data of [`Value`](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfRating.XForms.SfRating.html#Syncfusion_SfRating_XForms_SfRating_Value). It will be displayed when the mouse is hovered over the rating items and will be disappeared when a rating item is selected.

## Set Tooltip Placement

Using [`ToolTipPlacement`](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfRating.XForms.SfRating.html#Syncfusion_SfRating_XForms_SfRating_TooltipPlacement) property, We can define where the ToolTip need to be displayed. [`ToolTipPlacement`](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfRating.XForms.SfRating.html#Syncfusion_SfRating_XForms_SfRating_TooltipPlacement) having the following three types of placement.

*[`BottomRight`](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfRating.XForms.TooltipPlacement.html#Syncfusion_SfRating_XForms_TooltipPlacement_BottomRight),
*[`None`](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfRating.XForms.TooltipPlacement.html#Syncfusion_SfRating_XForms_TooltipPlacement_None),
*[`TopLeft`](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfRating.XForms.TooltipPlacement.html#Syncfusion_SfRating_XForms_TooltipPlacement_TopLeft).

N> By default, this property value is set to [`None`](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfRating.XForms.TooltipPlacement.html#Syncfusion_SfRating_XForms_TooltipPlacement_None).

### BottomRight

The Tooltip will display on bottom of the [`SfRating`](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfRating.XForms.SfRating.html) control.

{% tabs %}

{% highlight xaml %}

	<rating:SfRating TooltipPlacement="BottomRight" />
	
{% endhighlight %}

{% highlight C# %}

SfRating rating;
public MainPage()
{
    InitializeComponent();
    rating = new SfRating();
    rating.TooltipPlacement = TooltipPlacement.BottomRight;
}

{% endhighlight %}

{% endtabs %}

![SfRating right bottom ToolTip](images/rightBottom.jpg)

### TopLeft 

The Tooltip will be displayed on top of the [`SfRating`](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfRating.XForms.SfRating.html) control. 

{% tabs %}

{% highlight xaml %}

	<rating:SfRating TooltipPlacement="TopLeft" />
	
{% endhighlight %}

{% highlight C# %}

SfRating rating;
public MainPage()
{
    InitializeComponent();
    rating = new SfRating();
    rating.TooltipPlacement = TooltipPlacement.TopLeft;
}

{% endhighlight %} 

{% endtabs %}

![SfRating top left ToolTip](images/topLeft.jpg) 

### None

When we set [`ToolTipPlacement`](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfRating.XForms.SfRating.html#Syncfusion_SfRating_XForms_SfRating_TooltipPlacement) as None, The ToolTip will be disappear.

{% tabs %}

{% highlight xaml %}

	<rating:SfRating TooltipPlacement="None" />
	
{% endhighlight %}

{% highlight C# %}

SfRating rating;
public MainPage()
{
    InitializeComponent();
    rating = new SfRating();
    rating.TooltipPlacement = TooltipPlacement.None;
}

{% endhighlight %}

{% endtabs %}

![No tooltip](images/null.jpg)

## Set ToolTip Precision

The [`ToolTipPrecision`](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfRating.XForms.SfRating.html#Syncfusion_SfRating_XForms_SfRating_TooltipPrecision) property sets the number precisions to be displayed after decimal point in ToolTip. 

N> The default value of ToolTip precision is 1.

{% tabs %}

{% highlight xaml %}

	<rating:SfRating TooltipPrecision="6" />
	
{% endhighlight %}

{% highlight C# %}

SfRating rating;
public MainPage()
{
    InitializeComponent();
    rating = new SfRating();
    rating.TooltipPrecision = 6;
}

{% endhighlight %}

{% endtabs %}

![SfRating ToolTip precision](images/toolTipPrecision.jpg)
