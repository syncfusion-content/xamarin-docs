---
layout: post
title: Grid lines customization for SfDateTimeRangeNavigator
description: Grid Lines
platform: xamarin
control: SfDateTimeRangeNavigator
documentation: ug
---

# Grid Lines

The `MinorScaleStyle` and `MajorScaleStyle` properties of `SfDateTimeRangeNavigator` used to customize the minor and major grid lines. Following properties are available in each scale style to configure the grid lines.

* `ShowGridLines` – used to set the visibility of grid lines.
* `GridLineWidth` – used to set the width for grid lines.
* `GridLineColor` – used to set the color for grid lines.
* `GridLineDashes` – used to set dashes for grid lines.


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
SfDateTimeRangeNavigator rangenavigator = new SfDateTimeRangeNavigator();

...

rangenavigator.MajorScaleStyle.ShowGridLines = true;

rangenavigator.MajorScaleStyle.GridLineColor = Color.FromHex("#F109D7");

rangenavigator.MajorScaleStyle.GridLineWidth = 10;

rangenavigator.MinorScaleStyle.ShowGridLines = true;

rangenavigator.MinorScaleStyle.GridLineColor = Color.Red;

rangenavigator.MinorScaleStyle.GridLineWidth = 3;

rangenavigator.MinorScaleStyle.GridLineDashArray = new double[2] { 4, 4 };
{% endhighlight %}
{% endtabs %}

![](gridLine_images/gridline_img1.png)
