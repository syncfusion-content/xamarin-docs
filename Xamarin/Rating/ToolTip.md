---

layout: post
title: ToolTip in Xamarin Rating Control | Syncfusion
description: Explore ToolTip functionality in the Syncfusion Xamarin Rating (SfRating) control, including placement options and precision settings.
platform: Xamarin
control: Rating
documentation: ug

---

# ToolTip in Xamarin Rating (SfRating)

ToolTips offer additional context about UI elements that may not be immediately clear to users. In the Xamarin.Forms [`SfRating`](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfRating.XForms.SfRating.html) control, ToolTips display the [`Value`](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfRating.XForms.SfRating.html#Syncfusion_SfRating_XForms_SfRating_Value). They appear when hovering over rating items and disappear once a rating item is selected.

## Configure Tooltip Placement

The [`ToolTipPlacement`](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfRating.XForms.SfRating.html#Syncfusion_SfRating_XForms_SfRating_TooltipPlacement) property specifies where the ToolTip is displayed in relation to the control. Options include:

- [`BottomRight`](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfRating.XForms.TooltipPlacement.html#Syncfusion_SfRating_XForms_TooltipPlacement_BottomRight)
- [`None`](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfRating.XForms.TooltipPlacement.html#Syncfusion_SfRating_XForms_TooltipPlacement_None)
- [`TopLeft`](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfRating.XForms.TooltipPlacement.html#Syncfusion_SfRating_XForms_TooltipPlacement_TopLeft)

> Note: The default placement is set to [`None`](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfRating.XForms.TooltipPlacement.html#Syncfusion_SfRating_XForms_TooltipPlacement_None).

### BottomRight Placement

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

![SfRating BottomRight ToolTip](images/rightBottom.jpg)

### TopLeft Placement

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

![SfRating TopLeft ToolTip](images/topLeft.jpg)

### None

Setting [`ToolTipPlacement`](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfRating.XForms.SfRating.html#Syncfusion_SfRating_XForms_SfRating_TooltipPlacement) to [`None`](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfRating.XForms.TooltipPlacement.html#Syncfusion_SfRating_XForms_TooltipPlacement_None) will disable the ToolTip.

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

![No ToolTip](images/null.jpg)

## ToolTip Precision Configuration
The [`ToolTipPrecision`](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfRating.XForms.SfRating.html#Syncfusion_SfRating_XForms_SfRating_TooltipPrecision) property defines the number of decimal places shown in the ToolTip. Default precision is set to 1.

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

![SfRating ToolTip Precision](images/toolTipPrecision.jpg)
