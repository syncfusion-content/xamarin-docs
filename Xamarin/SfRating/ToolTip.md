---

layout: post
title: Tooltip in Syncfusion Rating control for Xamarin.Forms
description: Learn how to change the Tooltip of rating control
platform: Xamarin
control: Rating
documentation: ug

---


# Tooltip

## TooltipPlacement

Rating control provides tooltip support with rating value using `TooltipPlacement` property. 

N> By default, this property value is set to None.

### TopLeft 

The Tooltip will display on top of the SfRating control. 

{% highlight C# %}

	sfRating.TooltipPlacement=TooltipPlacement.LeftTop;

{% endhighlight %} 

![](images/topLeft.jpg) 

### BottomRight

The Tooltip will display on bottom of the SfRating control.

{% highlight C# %}

	sfRating.TooltipPlacement=TooltipPlacement.RightBottom;

{% endhighlight %}

![](images/rightBottom.jpg)

### None

It is used to invisible the tool tip in the SfRating control.

{% highlight C# %}

	sfRating.TooltipPlacement=TooltipPlacement.None;

{% endhighlight %}

![](images/null.jpg)

## Tooltip Precision

The `ToolTipPrecision` property sets the number precisions to be displayed after decimal point in tool tip. 

N> The default value of ToolTip precision is 1.

{% highlight C# %}

      sfRating.TooltipPlacement=6;

{% endhighlight %}

![](images/toolTipPrecision.jpg)