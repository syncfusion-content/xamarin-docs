---
layout: post
title: Minor and Major scale customization for SfDateTimeRangeNavigator
description: Minor and Major scales
platform: xamarin
control: SfDateTimeRangeNavigator
documentation: ug
---

# Major and Minor Scales

SfDateTimeRangeNavigator displays major and minor scales at the top and bottom position of the control. You can also control its visibility using [`MajorScaleStyle.IsVisible`](https://help.syncfusion.com/cr/cref_files/xamarin/sfchart/Syncfusion.SfChart.XForms~Syncfusion.RangeNavigator.XForms.ScaleStyle~IsVisible.html) and [`MinorScaleStyle.IsVisible`](https://help.syncfusion.com/cr/cref_files/xamarin/sfchart/Syncfusion.SfChart.XForms~Syncfusion.RangeNavigator.XForms.ScaleStyle~IsVisible.html) properties.

## Intervals

By default, best possible interval component will be chosen for both major and minor scales based on the available size of the view. For example, if the available space is sufficient to show only year labels without overlapping, interval will be displayed in years. However, you can also set specific `DateTimeIntervalType` components using [`Intervals`](https://help.syncfusion.com/cr/cref_files/xamarin/sfchart/Syncfusion.SfChart.XForms~Syncfusion.RangeNavigator.XForms.SfDateTimeRangeNavigator~Intervals.html) property as demonstrated in the below code snippet.

{% tabs %}
{% highlight xaml %}
<rangenavigator:SfDateTimeRangeNavigator Minimum="1/1/2015" Maximum="1/1/2016" ViewRangeStart="5/1/2015" 
	ViewRangeEnd="9/1/2016" Intervals="Year,Month" />
{% endhighlight %}

{% highlight c# %}
SfDateTimeRangeNavigator dateTime = new SfDateTimeRangeNavigator();
dateTime.Intervals = DateTimeIntervalType.Year | DateTimeIntervalType. Month;
{% endhighlight %}
{% endtabs %}

![](minorandmajorscale_images/minorandmajorscale_img1.png)

## Appearance Customization

The [`MajorScaleStyle`](https://help.syncfusion.com/cr/cref_files/xamarin/sfchart/Syncfusion.SfChart.XForms~Syncfusion.RangeNavigator.XForms.SfDateTimeRangeNavigator~MajorScaleStyle.html) and [`MinorScaleStyle`](https://help.syncfusion.com/cr/cref_files/xamarin/sfchart/Syncfusion.SfChart.XForms~Syncfusion.RangeNavigator.XForms.SfDateTimeRangeNavigator~MinorScaleStyle.html) properties of `SfDateTimeRangeNavigator` are used to customize the appearance of ticks and labels.

* [`Position`](https://help.syncfusion.com/cr/cref_files/xamarin/sfchart/Syncfusion.SfChart.XForms~Syncfusion.RangeNavigator.XForms.ScaleStyle~Position.html) – used to position the labels and ticks inside or outside of the range navigator.
* [`LabelAlignment`](https://help.syncfusion.com/cr/cref_files/xamarin/sfchart/Syncfusion.SfChart.XForms~Syncfusion.RangeNavigator.XForms.ScaleStyle~LabelAlignment.html) – used to set the alignment of the labels. 
* [`LabelTextColor`](https://help.syncfusion.com/cr/cref_files/xamarin/sfchart/Syncfusion.SfChart.XForms~Syncfusion.RangeNavigator.XForms.ScaleStyle~LabelTextColor.html) – used to change the text color of the labels.
* [`LabelFontSize`](https://help.syncfusion.com/cr/cref_files/xamarin/sfchart/Syncfusion.SfChart.XForms~Syncfusion.RangeNavigator.XForms.ScaleStyle~LabelFontSize.html) – used to change the font size of the labels.
* [`LabelFontAttributes`](https://help.syncfusion.com/cr/cref_files/xamarin/sfchart/Syncfusion.SfChart.XForms~Syncfusion.RangeNavigator.XForms.ScaleStyle~LabelFontAttributes.html) – used to change the font attribute of the labels.
* [`LabelFontFamily`](https://help.syncfusion.com/cr/cref_files/xamarin/sfchart/Syncfusion.SfChart.XForms~Syncfusion.RangeNavigator.XForms.ScaleStyle~LabelFontFamily.html) – used to change the font family of the labels.
* [`SelectedLabelFontSize`](https://help.syncfusion.com/cr/cref_files/xamarin/sfchart/Syncfusion.SfChart.XForms~Syncfusion.RangeNavigator.XForms.ScaleStyle~SelectedLabelFontSize.html) – used to change the font size of the selected labels.
* [`SelectedLabelFontAttributes`](https://help.syncfusion.com/cr/cref_files/xamarin/sfchart/Syncfusion.SfChart.XForms~Syncfusion.RangeNavigator.XForms.ScaleStyle~SelectedLabelFontAttributes.html) – used to change the font attribute of the selected labels.
* [`SelectedLabelFontFamily`](https://help.syncfusion.com/cr/cref_files/xamarin/sfchart/Syncfusion.SfChart.XForms~Syncfusion.RangeNavigator.XForms.ScaleStyle~SelectedLabelFontFamily.html) – used to change the font family of the selected labels.
* [`LabelMargin`](https://help.syncfusion.com/cr/cref_files/xamarin/sfchart/Syncfusion.SfChart.XForms~Syncfusion.RangeNavigator.XForms.ScaleStyle~LabelMargin.html) – used to change the margin size of the labels.
* [`SelectedLabelTextColor`](https://help.syncfusion.com/cr/cref_files/xamarin/sfchart/Syncfusion.SfChart.XForms~Syncfusion.RangeNavigator.XForms.ScaleStyle~SelectedLabelTextColor.html) – used to change the text color of the selected labels.
* [`SelectedLabelMargin`](https://help.syncfusion.com/cr/cref_files/xamarin/sfchart/Syncfusion.SfChart.XForms~Syncfusion.RangeNavigator.XForms.ScaleStyle~SelectedLabelMargin.html) – used to change the margin of the selected labels.
* [`TickLineWidth`](https://help.syncfusion.com/cr/cref_files/xamarin/sfchart/Syncfusion.SfChart.XForms~Syncfusion.RangeNavigator.XForms.ScaleStyle~TickLineWidth.html) - used to change the thickness of the tick line.
* [`TickLineColor`](https://help.syncfusion.com/cr/cref_files/xamarin/sfchart/Syncfusion.SfChart.XForms~Syncfusion.RangeNavigator.XForms.ScaleStyle~TickLineColor.html) - used to change the color of the tick line.

{% tabs %}
{% highlight xaml %}
<rangenavigator:SfDateTimeRangeNavigator Minimum="1/1/2015" Maximum="1/1/2016" ViewRangeStart="5/1/2015" 
	ViewRangeEnd="9/1/2016">
	
	<rangenavigator:SfDateTimeRangeNavigator.MajorScaleStyle>
	
		<rangenavigator:ScaleStyle Position="Inside" LabelAlignment="Right" SelectedLabelTextColor="Blue" 
			SelectedLabelFontSize="20" SelectedLabelMargin="15" LabelTextColor="Black" LabelFontSize="20" LabelMargin="15"/>
			
	</rangenavigator:SfDateTimeRangeNavigator.MajorScaleStyle>
	
	<rangenavigator:SfDateTimeRangeNavigator.MinorScaleStyle>
	
		<rangenavigator:ScaleStyle Position="Inside" LabelAlignment="Left" SelectedLabelTextColor="Black" 
			SelectedLabelFontSize="20" SelectedLabelMargin="15" LabelTextColor="Red" LabelFontSize="20" LabelMargin="15" />
			
	</rangenavigator:SfDateTimeRangeNavigator.MinorScaleStyle>
	
</rangenavigator:SfDateTimeRangeNavigator>
{% endhighlight %}

{% highlight c# %}
SfDateTimeRangeNavigator dateTime = new SfDateTimeRangeNavigator();

dateTime.MajorScaleStyle.Position = ScalePosition.Inside;
dateTime.MajorScaleStyle.LabelTextColor = Color.Black;
dateTime.MajorScaleStyle.LabelMargin = 15;
dateTime.MajorScaleStyle.LabelFontSize = 20;
dateTime.MajorScaleStyle.LabelAlignment = LabelAlignment.Right;
dateTime.MajorScaleStyle.SelectedLabelTextColor = Color.Red;
dateTime.MajorScaleStyle.SelectedLabelMargin = 15;
dateTime.MajorScaleStyle.SelectedLabelFontSize = 20;

dateTime.MinorScaleStyle.Position = ScalePosition.Inside;
dateTime.MinorScaleStyle.LabelTextColor = Color.Red;
dateTime.MinorScaleStyle.LabelMargin = 15;
dateTime.MinorScaleStyle.LabelFontSize = 20;
dateTime.MinorScaleStyle.LabelAlignment = LabelAlignment.Left;
dateTime.MinorScaleStyle.SelectedLabelTextColor = Color.Black;
dateTime.MinorScaleStyle.SelectedLabelMargin = 15;
dateTime.MinorScaleStyle.SelectedLabelFontSize = 20;
{% endhighlight %}
{% endtabs %}

![](minorandmajorscale_images/minorandmajorscale_img2.png)


