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

SfRating control provides Tooltip support to the SfRating control using `TooltipPlacement` property. 

N> By default, this property value is set to None.

### TopLeft 

The Tooltip will display on top of the SfRating control. 

{% tabs %}

{% highlight C# %}

	rating.TooltipPlacement=TooltipPlacement.LeftTop;

{% endhighlight %} 

{% highlight xaml %}

	<rating:SfRating x:Name="rating" TooltipPlacement="LeftTop" />
	
{% endhighlight %}

{% endtabs %}

![](images/topLeft.jpg) 

### BottomRight

The Tooltip will display on bottom of the SfRating control.

{% tabs %}

{% highlight C# %}

	rating.TooltipPlacement=TooltipPlacement.RightBottom;

{% endhighlight %}

{% highlight xaml %}

	<rating:SfRating x:Name="rating" TooltipPlacement="RightBottom" />
	
{% endhighlight %}

{% endtabs %}

![](images/rightBottom.jpg)

### None

It is used to invisible the Tooltip in the SfRating control.

{% tabs %}

{% highlight C# %}

	rating.TooltipPlacement=TooltipPlacement.None;

{% endhighlight %}

{% highlight xaml %}

	<rating:SfRating x:Name="rating" TooltipPlacement="None" />
	
{% endhighlight %}

{% endtabs %}

![](images/null.jpg)

## ToolTipPrecision

The `ToolTipPrecision` property sets the number precisions to be displayed after decimal point in Tooltip. 

N> The default value of ToolTip precision is 1.

{% tabs %}

{% highlight C# %}

      rating.ToolTipPrecision=6;

{% endhighlight %}

{% highlight xaml %}

	<rating:SfRating x:Name="rating" ToolTipPrecision="6" />
	
{% endhighlight %}

{% endtabs %}

![](images/toolTipPrecision.jpg)