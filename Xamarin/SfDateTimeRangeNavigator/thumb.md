---
layout: post
title: Thumb customization for SfDateTimeRangeNavigator
description: Thumb
platform: xamarin
control: SfDateTimeRangeNavigator
documentation: ug
---

# Thumb

The [`LeftThumbStyle`](https://help.syncfusion.com/cr/cref_files/xamarin/sfchart/Syncfusion.SfChart.XForms~Syncfusion.RangeNavigator.XForms.SfDateTimeRangeNavigator~LeftThumbStyle.html) and [`RightThumbStyle`](https://help.syncfusion.com/cr/cref_files/xamarin/sfchart/Syncfusion.SfChart.XForms~Syncfusion.RangeNavigator.XForms.SfDateTimeRangeNavigator~RightThumbStyle.html) properties are used to configure the left and right thumb of the [`SfDateTimeRangeNavigator`](https://help.syncfusion.com/cr/cref_files/xamarin/sfchart/Syncfusion.SfChart.XForms~Syncfusion.RangeNavigator.XForms.SfDateTimeRangeNavigator.html). Following properties are available in thumb style to configure left and right thumb individually. 

* [`BorderColor`](https://help.syncfusion.com/cr/cref_files/xamarin/sfchart/Syncfusion.SfChart.XForms~Syncfusion.RangeNavigator.XForms.ThumbStyle~BorderColor.html) – used to change the stroke color of the thumb.
* [`BackgroundColor`](https://help.syncfusion.com/cr/cref_files/xamarin/sfchart/Syncfusion.SfChart.XForms~Syncfusion.RangeNavigator.XForms.ThumbStyle~BackgroundColor.html) – used to change the background color of the thumb.
* [`BorderWidth`](https://help.syncfusion.com/cr/cref_files/xamarin/sfchart/Syncfusion.SfChart.XForms~Syncfusion.RangeNavigator.XForms.ThumbStyle~BorderWidth.html) – used to change the stroke width of the thumb.
* [`Width`](https://help.syncfusion.com/cr/cref_files/xamarin/sfchart/Syncfusion.SfChart.XForms~Syncfusion.RangeNavigator.XForms.ThumbStyle~Width.html) – used to change the width of the thumb.
* [`Height`](https://help.syncfusion.com/cr/cref_files/xamarin/sfchart/Syncfusion.SfChart.XForms~Syncfusion.RangeNavigator.XForms.ThumbStyle~Height.html) – used to change the height of the thumb.
* [`LineColor`](https://help.syncfusion.com/cr/cref_files/xamarin/sfchart/Syncfusion.SfChart.XForms~Syncfusion.RangeNavigator.XForms.ThumbStyle~LineColor.html) – used to change the line color of the thumb.
* [`LineWidth`](https://help.syncfusion.com/cr/cref_files/xamarin/sfchart/Syncfusion.SfChart.XForms~Syncfusion.RangeNavigator.XForms.ThumbStyle~LineWidth.html) – used to change the line width of the thumb.
* [`LineDashArray`](https://help.syncfusion.com/cr/cref_files/xamarin/sfchart/Syncfusion.SfChart.XForms~Syncfusion.RangeNavigator.XForms.ThumbStyle~LineDashArray.html) – used to change the dash array of the thumb line.


{% tabs %}
{% highlight xaml %}
<rangenavigator:SfDateTimeRangeNavigator HorizontalOptions="FillAndExpand" VerticalOptions="FillAndExpand" Minimum="1/1/2015" 
	Maximum="12/31/2015">

	<rangenavigator:SfDateTimeRangeNavigator.LeftThumbStyle>

		<rangenavigator:ThumbStyle BorderColor="#083928" BackgroundColor="Aqua" BorderWidth="3" LineColor="#E70E49" 
			LineWidth="5"/>

	</rangenavigator:SfDateTimeRangeNavigator.LeftThumbStyle>

	<rangenavigator:SfDateTimeRangeNavigator.RightThumbStyle>

		<rangenavigator:ThumbStyle BorderColor="#083928" BackgroundColor="Aqua" BorderWidth="3" LineColor="#E70E49" 
			LineWidth="5"/>

	</rangenavigator:SfDateTimeRangeNavigator.RightThumbStyle>

</rangenavigator:SfDateTimeRangeNavigator>
{% endhighlight %}

{% highlight c# %}
SfDateTimeRangeNavigator rangeNavigator = new SfDateTimeRangeNavigator();

...

rangeNavigator.LeftThumbStyle.BackgroundColor = Color.Aqua;

rangeNavigator.LeftThumbStyle.BorderColor = Color.FromHex("#083928");

rangeNavigator.LeftThumbStyle.BorderWidth = 3;

rangeNavigator.LeftThumbStyle.LineColor = Color.FromHex("#E70E49");

rangeNavigator.LeftThumbStyle.LineWidth = 5;

rangeNavigator.RightThumbStyle.BackgroundColor = Color.Aqua;

rangeNavigator.RightThumbStyle.BorderColor = Color.FromHex("#083928");

rangeNavigator.RightThumbStyle.BorderWidth = 3;

rangeNavigator.RightThumbStyle.LineColor = Color.FromHex("#E70E49");

rangeNavigator.RightThumbStyle.LineWidth = 5;
{% endhighlight %}
{% endtabs %}

![](thumb_images/thumb_img1.png)