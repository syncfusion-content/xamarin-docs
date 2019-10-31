---

layout: post
title: Tooltip in Syncfusion SfRating control for Xamarin.Forms
description: Learn how to change the Tooltip of rating control
platform: Xamarin
control: Rating
documentation: ug

---

# Tooltip

Tooltip provides additional information about objects that are unfamiliar to users and are not directly displayed in UI. In the Xamarin.Forms SfRating control, tooltip shows the data of `Value`. It will be displayed when the mouse is hovered over the rating items and will be disappeared when a rating item is selected.

## Set Tooltip Placement

Using `ToolTipPlacement` property, We can define where the ToolTip need to be displayed. TooTipPlacement having the following three types of placement.

*BottomRight,
*None,
*TopLeft.

N> By default, this property value is set to None.

### BottomRight

The Tooltip will display on bottom of the SfRating control.

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

The Tooltip will be displayed on top of the SfRating control. 

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

When we set `ToolTipPlacement` as None, The ToolTip will be disappear.

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

The `ToolTipPrecision` property sets the number precisions to be displayed after decimal point in ToolTip. 

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