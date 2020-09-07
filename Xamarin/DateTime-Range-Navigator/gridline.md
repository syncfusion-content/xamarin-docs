---
layout: post
title: Grid lines customization for SfDateTimeRangeNavigator
description: Grid Lines
platform: xamarin
control: SfDateTimeRangeNavigator
documentation: ug
---

# Grid Lines

The [`MinorScaleStyle`](https://help.syncfusion.com/cr/xamarin/Syncfusion.RangeNavigator.XForms.SfDateTimeRangeNavigator.html#Syncfusion_RangeNavigator_XForms_SfDateTimeRangeNavigator_MinorScaleStyle) and [`MajorScaleStyle`](https://help.syncfusion.com/cr/xamarin/Syncfusion.RangeNavigator.XForms.SfDateTimeRangeNavigator.html#Syncfusion_RangeNavigator_XForms_SfDateTimeRangeNavigator_MajorScaleStyle) properties of [`SfDateTimeRangeNavigator`](https://help.syncfusion.com/cr/xamarin/Syncfusion.RangeNavigator.XForms.SfDateTimeRangeNavigator.html) used to customize the minor and major grid lines. Following properties are available in each scale style to configure the grid lines.

* [`ShowGridLines`](https://help.syncfusion.com/cr/xamarin/Syncfusion.RangeNavigator.XForms.ScaleStyle.html#Syncfusion_RangeNavigator_XForms_ScaleStyle_ShowGridLines) – used to set the visibility of grid lines.
* [`GridLineWidth`](https://help.syncfusion.com/cr/xamarin/Syncfusion.RangeNavigator.XForms.ScaleStyle.html#Syncfusion_RangeNavigator_XForms_ScaleStyle_GridLineWidth) – used to set the width for grid lines.
* [`GridLineColor`](https://help.syncfusion.com/cr/xamarin/Syncfusion.RangeNavigator.XForms.ScaleStyle.html#Syncfusion_RangeNavigator_XForms_ScaleStyle_GridLineColor) – used to set the color for grid lines.
* [`GridLineDashes`](https://help.syncfusion.com/cr/xamarin/Syncfusion.RangeNavigator.XForms.ScaleStyle.html#Syncfusion_RangeNavigator_XForms_ScaleStyle_GridLineDashArray) – used to set dashes for grid lines.


{% tabs %}
{% highlight xaml %}
<rangenavigator:SfDateTimeRangeNavigator HorizontalOptions="FillAndExpand" VerticalOptions="FillAndExpand" Minimum="1/5/2015" 
	Maximum="11/7/2015">

<rangenavigator:SfDateTimeRangeNavigator.MajorScaleStyle>

<rangenavigator:ScaleStyle GridLineColor="#F109D7" GridLineWidth="10" ShowGridLines="True"/>

</rangenavigator:SfDateTimeRangeNavigator.MajorScaleStyle >

<rangenavigator:SfDateTimeRangeNavigator.MinorScaleStyle>

<rangenavigator:ScaleStyle GridLineColor="Red" GridLineWidth="3" ShowGridLines="True"/>

</rangenavigator:SfDateTimeRangeNavigator.MinorScaleStyle >

</rangenavigator:SfDateTimeRangeNavigator>
{% endhighlight %}

{% highlight c# %}
SfDateTimeRangeNavigator rangeNavigator = new SfDateTimeRangeNavigator();

...

rangeNavigator.MajorScaleStyle.ShowGridLines = true;

rangeNavigator.MajorScaleStyle.GridLineColor = Color.FromHex("#F109D7");

rangeNavigator.MajorScaleStyle.GridLineWidth = 10;

rangeNavigator.MinorScaleStyle.ShowGridLines = true;

rangeNavigator.MinorScaleStyle.GridLineColor = Color.Red;

rangeNavigator.MinorScaleStyle.GridLineWidth = 3;

rangeNavigator.MinorScaleStyle.GridLineDashArray = new double[2] { 4, 4 };
{% endhighlight %}
{% endtabs %}

![](gridLine_images/gridline_img1.png)
