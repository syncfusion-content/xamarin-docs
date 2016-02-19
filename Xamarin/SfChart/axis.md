---
layout: post
title: Chart Axis
description: How to customize the grid lines, tick lines, labels and title of chart axis
platform: xamarin
control: Chart
documentation: ug
---

# Axis

Charts typically have two axes that are used to measure and categorize data: a vertical (Y) axis, and a horizontal (X) axis.

Vertical(Y) axis always uses numerical scale. Horizontal(X) axis supports the following types of scale:

* Category
* Numeric
* Date time
* Logarithmic Axis

## Category Axis

Category axis displays text labels instead of numbers. 

{% tabs %} 

{% highlight xaml %}

<chart:SfChart.PrimaryAxis >

	<chart:CategoryAxis />

</chart:SfChart.PrimaryAxis>

{% endhighlight %}

{% highlight c# %}

chart.PrimaryAxis = new CategoryAxis();

{% endhighlight %}

{% endtabs %}

![](axis_images/axis_img1.png)

### Placing labels between ticks

Labels in category axis can be placed between the ticks by setting `LabelPlacement` to `BetweenTicks`. Default value of `LabelPlacement` property is `OnTicks` i.e. labels will be placed on the ticks by default.

{% tabs %} 

{% highlight xaml %}

<chart:SfChart.PrimaryAxis >

	<chart:CategoryAxis LabelPlacement="BetweenTicks"/>

</chart:SfChart.PrimaryAxis>

{% endhighlight %}

{% highlight c# %}

chart.PrimaryAxis = new CategoryAxis() { LabelPlacement = LabelPlacement.BetweenTicks };

{% endhighlight %}

{% endtabs %}

![](axis_images/axis_img2.png)

### Displaying labels after a fixed interval

To display labels after a fixed interval n, you can set `Interval` property of ChartAxis as n. Default value of interval is 1 i.e. all the labels will be displayed by default.

{% tabs %} 

{% highlight xaml %}

<chart:SfChart.PrimaryAxis >

	<chart:CategoryAxis Interval="2" LabelPlacement="BetweenTicks"/>

</chart:SfChart.PrimaryAxis>

{% endhighlight %}

{% highlight c# %}

chart.PrimaryAxis = new CategoryAxis() { Interval = 2, LabelPlacement = LabelPlacement.BetweenTicks };

{% endhighlight %}

{% endtabs %}

![](axis_images/axis_img3.png)

## Numeric Axis

Numeric axis uses numerical scale and displays numbers as labels. 

{% tabs %} 

{% highlight xaml %}

<chart:SfChart.PrimaryAxis >

	<chart:NumericalAxis/>

</chart:SfChart.PrimaryAxis>

{% endhighlight %}

{% highlight c# %}

chart.PrimaryAxis = new NumericalAxis();

{% endhighlight %}

{% endtabs %}

![](axis_images/axis_img4.png)

### Customizing numeric range

To customize the range of an axis, you can use the `Minimum` and `Maximum` properties of `NumericalAxis`. By default, nice range will be calculated automatically based on the provided data.

{% tabs %} 

{% highlight xaml %}

<chart:SfChart.SecondaryAxis >

	<chart:NumericalAxis Minimum="10" Maximum="50"/>

</chart:SfChart.SecondaryAxis >

{% endhighlight %}

{% highlight c# %}

chart.SecondaryAxis = new NumericalAxis() { Minimum = 10, Maximum = 50 };

{% endhighlight %}

{% endtabs %}

![](axis_images/axis_img5.png)

### Customizing numeric interval

Axis interval can be customized using the `Interval` property of ChartAxis. By default, nice interval will be calculated based on the minimum and maximum value of the provided data.

{% tabs %} 

{% highlight xaml %}

<chart:SfChart.SecondaryAxis >

	<chart:NumericalAxis Interval="10"/>

</chart:SfChart.SecondaryAxis >

{% endhighlight %}

{% highlight c# %}

chart.SecondaryAxis = new NumericalAxis() { Interval = 10 };

{% endhighlight %}

{% endtabs %}

![](axis_images/axis_img6.png)

### Apply padding to the range

Padding can be applied to the minimum and maximum extremes of the axis range by using `RangePadding` property. Numeric axis supports the following types of padding.

* None
* Round
* Additional
* Normal

**None**

When the value of `RangePadding` property is `None`, padding will not be applied to the axis. This is also the default value of `RangePadding` for horizontal axis.

{% tabs %} 

{% highlight xaml %}

<chart:SfChart.SecondaryAxis>

	<chart:NumericalAxis RangePadding="None"/>

</chart:SfChart.SecondaryAxis>

{% endhighlight %}

{% highlight c# %}

chart.SecondaryAxis = new NumericalAxis() { RangePadding = NumericalPadding.None };

{% endhighlight %}

{% endtabs %}

![](axis_images/axis_img7.png)

**Round**

When the value of `RangePadding` property is `Round`, axis range will be rounded to the nearest possible value divided by the interval.

{% tabs %} 

{% highlight xaml %}

<chart:SfChart.SecondaryAxis>

	<chart:NumericalAxis RangePadding="Round"/>

</chart:SfChart.SecondaryAxis>

{% endhighlight %}

{% highlight c# %}

chart.SecondaryAxis = new NumericalAxis() { RangePadding = NumericalPadding.Round };

{% endhighlight %}

{% endtabs %}

![](axis_images/axis_img8.png)

**Additional**

When the value of `RangePadding` property is `Additional`, axis range will be rounded and an interval of the axis will be added as padding to the minimum and maximum values of the range.

{% tabs %} 

{% highlight xaml %}

<chart:SfChart.SecondaryAxis>

	<chart:NumericalAxis RangePadding="Additional"/>

</chart:SfChart.SecondaryAxis>

{% endhighlight %}

{% highlight c# %}

chart.SecondaryAxis = new NumericalAxis() { RangePadding = NumericalPadding.Additional };

{% endhighlight %}

{% endtabs %}

![](axis_images/axis_img9.png)

**Normal**

When the value of `RangePadding` property is `Normal`, nice range will be calculated for the axis based on the best readability of the data. This is also the default for vertical axis.

{% tabs %} 

{% highlight xaml %}

<chart:SfChart.SecondaryAxis>

	<chart:NumericalAxis RangePadding="Normal"/>

</chart:SfChart.SecondaryAxis>

{% endhighlight %}

{% highlight c# %}

chart.SecondaryAxis = new NumericalAxis() { RangePadding = NumericalPadding.Normal };

{% endhighlight %}

{% endtabs %}

![](axis_images/axis_img10.png)

## Date Time Axis

Date time axis uses date time scale and displays date time values as axis labels in specified format. 

{% tabs %} 

{% highlight xaml %}

<chart:SfChart.PrimaryAxis >

	<chart:DateTimeAxis/>

</chart:SfChart.PrimaryAxis>

{% endhighlight %}

{% highlight c# %}

chart.PrimaryAxis = new DateTimeAxis();

{% endhighlight %}

{% endtabs %}

![](axis_images/axis_img11.png)

### Customizing date time range

To customize the range of an axis, you can use the `Minimum` and `Maximum` properties of `DateTimeAxis`. By default, nice range will be calculated automatically based on the provided data.

{% tabs %} 

{% highlight xaml %}

Namespace:

xmlns:sys="clr-namespace:System;assembly=mscorlib"
...
<chart:SfChart.PrimaryAxis  >

	<chart:DateTimeAxis>

		<chart:DateTimeAxis.Minimum>

			<sys:DateTime x:FactoryMethod="Parse">

				<x:Arguments>

					<x:String>Jan 1 2010</x:String>

				</x:Arguments>

			</sys:DateTime>

		</chart:DateTimeAxis.Minimum>

		<chart:DateTimeAxis.Maximum>

			<sys:DateTime x:FactoryMethod="Parse">

				<x:Arguments>

					<x:String>Dec 30 2015</x:String>

				</x:Arguments>

			</sys:DateTime>

		</chart:DateTimeAxis.Maximum>

	</chart:DateTimeAxis>

</chart:SfChart.PrimaryAxis>

{% endhighlight %}

{% highlight c# %}

chart.PrimaryAxis = new DateTimeAxis() { 

	Minimum = new DateTime(2010, 1, 1), 
	Maximum = new DateTime(2015, 12, 30) 
	
};

{% endhighlight %}

{% endtabs %}

![](axis_images/axis_img12.png)

### Date time intervals

Date time intervals can be customized using `Interval` and `IntervalType` properties of the `DateTimeAxis`. For example, setting `Interval` as 2 and `IntervalType` as `Years` will consider 2 years as interval.

Essential Chart supports the following types of interval for date time axis

* Years
* Months
* Days
* Hours
* Minutes
* Seconds
* Milliseconds

{% tabs %} 

{% highlight xaml %}

<chart:SfChart.PrimaryAxis>

	<chart:DateTimeAxis IntervalType="Months">

		<chart:DateTimeAxis.Interval>

			<Double>6</Double>

		</chart:DateTimeAxis.Interval>

	</chart:DateTimeAxis>

</chart:SfChart.PrimaryAxis>

{% endhighlight %}

{% highlight c# %}

chart.PrimaryAxis = new DateTimeAxis() { 

	IntervalType = DateTimeIntervalType.Months, 
	Interval = 6 
	
};

{% endhighlight %}

{% endtabs %}

![](axis_images/axis_img13.png)

### Apply padding to the range

Padding can be applied to the minimum and maximum extremes of the range by using `RangePadding` property. Date time axis supports the following types of padding:

* None
* Round
* Additional

**None**

When the value of `RangePadding` property is `None`, padding will not be applied to the axis. This is also the default value of `RangePadding`.

{% tabs %} 

{% highlight xaml %}

<chart:SfChart.PrimaryAxis>

	<chart:DateTimeAxis RangePadding="None"/>

</chart:SfChart.PrimaryAxis >

{% endhighlight %}

{% highlight c# %}

chart.PrimaryAxis = new DateTimeAxis() { RangePadding = DateTimeRangePadding.None };

{% endhighlight %}

{% endtabs %}

![](axis_images/axis_img14.png)

**Round**

When the value of `RangePadding` property is `round`, axis range will be rounded to the nearest possible date time value.

{% tabs %} 

{% highlight xaml %}

<chart:SfChart.PrimaryAxis >

	<chart:DateTimeAxis RangePadding="Round"/>

</chart:SfChart.PrimaryAxis >

{% endhighlight %}

{% highlight c# %}

chart.PrimaryAxis = new DateTimeAxis() { RangePadding = DateTimeRangePadding.Round };

{% endhighlight %}

{% endtabs %}

![](axis_images/axis_img15.png)

**Additional**

When the value of `RangePadding` property is `Additional`, range will be rounded and date time interval of the axis will be added as padding to the minimum and maximum extremes of the range.

{% tabs %} 

{% highlight xaml %}

<chart:SfChart.PrimaryAxis >

	<chart:DateTimeAxis RangePadding="Additional"/>

</chart:SfChart.PrimaryAxis >

{% endhighlight %}

{% highlight c# %}

chart.PrimaryAxis = new DateTimeAxis() { RangePadding = DateTimeRangePadding.Additional };

{% endhighlight %}

{% endtabs %}

![](axis_images/axis_img16.png)

## Logarithmic Axis

Logarithmic axis uses logarithmic scale and displays numbers as axis labels.

{% tabs %} 

{% highlight xaml %}

<chart:SfChart.SecondaryAxis>

	<chart:LogarithmicAxis />

</chart:SfChart.SecondaryAxis>

{% endhighlight %}

{% highlight c# %}

chart.SecondaryAxis = new LogarithmicAxis (); 

{% endhighlight %}

{% endtabs %}

![](axis_images/logaxis_img1.png)

## Customizing the logarithmic range

To customize the range of log axis, you can use the minimum and maximum properties of LogarithmicAxis. By default,nice range will be calculated automatically based on the provided data.

{% tabs %} 

{% highlight xaml %}

<chart:SfChart.SecondaryAxis>

	<chart:LogarithmicAxis >
	
		<chart:LogarithmicAxis.Minimum>
			<x:Double>100</x:Double>
		</chart:LogarithmicAxis.Minimum>
		
		<chart:LogarithmicAxis.Maximum>
			<x:Double>10000</x:Double>
		</chart:LogarithmicAxis.Maximum>
		
	</chart:LogarithmicAxis>
	
</chart:SfChart.SecondaryAxis>

{% endhighlight %}

{% highlight c# %}

chart.SecondaryAxis = new LogarithmicAxis() { 

	Minimum = 100, 
	Maximum = 10000 

};

{% endhighlight %}

{% endtabs %}

![](axis_images/logaxis_img2.png)

## Customizing the logarithmic base

To customize the log base value, you can use LogarithmicBase property.

{% tabs %} 

{% highlight xaml %}

<chart:SfChart.SecondaryAxis>

	<chart:LogarithmicAxis LogarithmicBase="2" />

</chart:SfChart.SecondaryAxis>	

{% endhighlight %}

{% highlight c# %}

chart.SecondaryAxis = new LogarithmicAxis() { LogarithmicBase = 2 };

{% endhighlight %}

{% endtabs %}

![](axis_images/logaxis_img3.png)

## Common axis features

Customization of features such as axis title, labels, grid lines and tick lines are common to all the axes. Each of these features are explained in this section.

### Axis Visibility

Axis visibility can be controlled using the `IsVisible` property of axis. Default value of `IsVisible` property is `True`.

{% tabs %} 

{% highlight xaml %}

<chart:SfChart.SecondaryAxis>

	<chart:NumericalAxis IsVisible="False"/>

</chart:SfChart.SecondaryAxis >

{% endhighlight %}

{% highlight c# %}

chart.SecondaryAxis.IsVisible = false;

{% endhighlight %}

{% endtabs %}

![](axis_images/axis_img17.png)

### Axis title

The `Title` property in axis provides options to customize the text and font of axis title. Axis does not display title by default. The title can be customized using following properties,

* `Text` – used to set the title for axis.
* `TextColor` – used to change the color of the label.
* `BackgroundColor` – used to change the label background color.
* `BorderColor` – used to change the border color.
* `BorderWidth` – used to change the width of the border.
* `Font` – used to change the text size, font family and font weight.
* `Margin` - used to change the margin size for labels.

Following code snippet illustrates how to enable and customize the axis title.

{% tabs %} 

{% highlight xaml %}

<chart:SfChart.PrimaryAxis>

	<chart:CategoryAxis  >

		<chart:CategoryAxis.Title>

			<chart:ChartAxisTitle Text="Month" TextColor="Blue">

				<chart:ChartAxisTitle.Font>

					<Font FontSize="20" FontAttributes ="Bold"/>

				</chart:ChartAxisTitle.Font>

			</chart:ChartAxisTitle>

		</chart:CategoryAxis.Title>

	</chart:CategoryAxis  >

</chart:SfChart.PrimaryAxis >

{% endhighlight %}

{% highlight c# %}

chart.PrimaryAxis.Title.Text = "Month";

chart.PrimaryAxis.Title.TextColor = Color.Blue;

chart.PrimaryAxis.Title.Font = Font.SystemFontOfSize(20, FontAttributes.Bold);

{% endhighlight %}

{% endtabs %}

![](axis_images/axis_img18.png)

### Label customization

The `LabelStyle` property of axis provides options to customize the font-family, color, size and font-weight of axis labels. The axis labels can be customized using following properties:

* `TextColor` – used to change the color of the labels.
* `BackgroundColor` – used to change the label background color.
* `BorderColor` – used to change the border color.
* `BorderThickness` – used to change the thickness of the border.
* `Font` – used to change the text size, font family and font weight.
* `Margin` - used to change the margin size for labels.

{% tabs %} 

{% highlight xaml %}

<chart:SfChart.PrimaryAxis>

	<chart:CategoryAxis >

		<chart:CategoryAxis.LabelStyle>

			<chart:ChartAxisLabelStyle TextColor="Red">

				<chart:ChartAxisLabelStyle.Font>

					<Font FontSize="20" FontAttributes ="Bold"/>

				</chart:ChartAxisLabelStyle.Font>

			</chart:ChartAxisLabelStyle>

		</chart:CategoryAxis.LabelStyle>

	</chart:CategoryAxis>

</chart:SfChart.PrimaryAxis>

{% endhighlight %}

{% highlight c# %}

chart.PrimaryAxis.LabelStyle.Font = Font.SystemFontOfSize(20, FontAttributes.Bold);

chart.PrimaryAxis.LabelStyle.TextColor = Color.Red;

{% endhighlight %}

{% endtabs %}

![](axis_images/axis_img19.png)

### Label and tick positioning

Axis labels and ticks can be positioned inside or outside the chart area by using `LabelStyle`.`LabelsPosition` and `TickPosition` properties of ChartAxis. By default labels and ticks will be positioned outside the chart area.

{% tabs %} 

{% highlight xaml %}

<chart:SfChart.PrimaryAxis >

	<chart:DateTimeAxis TickPosition="Inside">

		<chart:DateTimeAxis.LabelStyle>

			<chart:ChartAxisLabelStyle LabelsPosition="Inside"/>
		
		</chart:DateTimeAxis.LabelStyle>

	</chart:DateTimeAxis>

</chart:SfChart.PrimaryAxis >

{% endhighlight %}

{% highlight c# %}

chart.PrimaryAxis.LabelStyle.LabelsPosition = AxisElementPosition.Inside;

chart.PrimaryAxis.TickPosition = AxisElementPosition.Inside;

{% endhighlight %}

{% endtabs %}

![](axis_images/axis_img20.png)

### Edge labels placement

Labels with long text at the edges of an axis may appear partially outside the chart. The `EdgeLabelsDrawingMode` property can be used to avoid the partial appearance of labels at the corners.

{% tabs %} 

{% highlight xaml %}

<chart:CategoryAxis EdgeLabelsDrawingMode="Shift"/>

{% endhighlight %}

{% highlight c# %}

chart.PrimaryAxis.EdgeLabelsDrawingMode = EdgeLabelsDrawingMode.Shift;

{% endhighlight %}

{% endtabs %}

![](axis_images/axis_img21.png)

### Grid lines customization

The `ShowMajorGridLines` and `ShowMinorGridLines` properties are used to control the visibility of grid lines. `MajorGridLineStyle` and `MinorGridLineStyle` properties in axis are used to customize the major grid lines and minor grid lines of an axis respectively. They provide options to change the width, dashes, color of grid lines. By default minor grid lines will not be visible. 

{% tabs %} 

{% highlight xaml %}

<chart:SfChart.SecondaryAxis >

	<chart:NumericalAxis ShowMajorGridLines="True" ShowMinorGridLines="True" 
	MinorTicksPerInterval="1"/>

</chart:SfChart.SecondaryAxis >

{% endhighlight %}

{% highlight c# %}

chart. SecondaryAxis = new NumericalAxis ()

{

	ShowMajorGridLines = true,

	ShowMinorGridLines = true,

	MinorTicksPerInterval = 1

};

{% endhighlight %}

{% endtabs %}

![](axis_images/axis_img22.png)

### Tick lines customization

The `MajorTickStyle` and `MinorTickStyle` properties in axis are used to customize the major tick lines of an axis and minor tick lines of an axis respectively. They provide options to change the width, size, color and visibility of tick lines. By default minor tick lines will not be visible.

{% tabs %} 

{% highlight xaml %}

<chart:SfChart.SecondaryAxis >

	<chart:NumericalAxis ShowMinorGridLines="True" MinorTicksPerInterval="1">

		<chart:NumericalAxis.MajorTickStyle >

			<chart:ChartAxisTickStyle TickSize="7" StrokeColor="Blue" StrokeWidth="3"/>

		</chart:NumericalAxis.MajorTickStyle>

		<chart:NumericalAxis.MinorTickStyle>

			<chart:ChartAxisTickStyle TickSize="5" StrokeColor="Green" StrokeWidth="2"/>

		</chart:NumericalAxis.MinorTickStyle>

	<chart:NumericalAxis/>

</chart:SfChart.SecondaryAxis >

{% endhighlight %}

{% highlight c# %}

NumericalAxis numerical = new NumericalAxis();

numerical.MajorTickStyle.TickSize = 7;

numerical.MajorTickStyle.StrokeWidth = 3;

numerical.MajorTickStyle.StrokeColor = Color.Red;

numerical.ShowMinorGridLines = true;

numerical.MinorTicksPerInterval = 1;

numerical.MinorTickStyle.TickSize = 5;

numerical.MinorTickStyle.StrokeWidth = 2;

numerical.MinorTickStyle.StrokeColor = Color.Green;

chart.SecondaryAxis = numerical;

{% endhighlight %}

{% endtabs %}

![](axis_images/axis_img23.png)

### Inversing axis

Axis can be inversed using the `IsInversed` property of axis. Default value of `IsInversed` property is `False`.

{% tabs %} 

{% highlight c# %}

<chart:SfChart.SecondaryAxis >

	<chart:NumericalAxis IsInversed="True">

</chart:SfChart.SecondaryAxis >

{% endhighlight %}

{% highlight c# %}

chart.SecondaryAxis.IsInversed = true;

{% endhighlight %}

{% endtabs %}

![](axis_images/axis_img24.png)

### Placing axes at the opposite side

The `OpposedPosition` property of axis can be used to place the axis at the opposite side of its default position. Default value of `OpposedPosition` property is `False`. 

{% tabs %} 

{% highlight xaml %}

<chart:SfChart.SecondaryAxis >

	<chart:NumericalAxis OpposedPosition="True">

</chart:SfChart.SecondaryAxis >

{% endhighlight %}

{% highlight c# %}

chart.SecondaryAxis.OpposedPosition = true;

{% endhighlight %}

{% endtabs %}

![](axis_images/axis_img25.png)

### Maximum number of labels per 100 pixels

By default, a maximum of 3 labels are displayed for each 100 pixels in axis. The maximum number of labels that should be present within 100 pixels length can be customized using the `MaximumLabels` property of an axis. This property is applicable only for automatic range calculation and will not work if you set value for `Interval` property of an axis.

{% tabs %} 

{% highlight xaml %}

<chart:SfChart.SecondaryAxis >

	<chart:NumericalAxis MaximumLabels="5"/>

</chart:SfChart.SecondaryAxis >

{% endhighlight %}

{% highlight c# %}

Chart.SecondaryAxis.MaximumLabels = 5;

{% endhighlight %}

{% endtabs %}

![](axis_images/axis_img26.png)

## Smart Axis Labels

Axis labels may overlap with each other based on chart dimensions and label size. The `LabelsIntersectAction` property of axis is useful in avoiding the overlapping of axis labels with each other. Default value of `LabelsIntersectAction` is `None`. Other available values of `LabelsIntersectAction` are `MultipleRows` and `Hide`.

{% tabs %} 

{% highlight xaml %}

<chart:SfChart.PrimaryAxis >

	<chart:CategoryAxis LabelsIntersectAction="MultipleRows"/>

</chart:SfChart.PrimaryAxis >

{% endhighlight %}

{% highlight c# %}

chart.PrimaryAxis.LabelsIntersectAction = AxisLabelsIntersectAction.MultipleRows;

{% endhighlight %}

{% endtabs %}

![](axis_images/axis_img27.png)

## Event

**ActualRangeChanged**

This event is triggered when the actual range of the axis is changed. The argument contains the following information.

* `ActualMinimum` - used to get or set the actual minimum value of the axis.
* `ActualMaximum` - used to get or set the actual maximum value of the axis.
* `VisibleMinimum` - used to get or set the visible minimum value of the axis.
* `VisibleMaximum` - used to get or set the visible maximum value of the axis.

N> Actual range and visible range are similar unless the range is changed by specifying the `ZoomPosition` and `ZoomFactor` properties or zoom the chart interactively. Visible range is always the range which you see visually in the screen.

**LabelCreated**

This event is triggered when the axis label is created. The argument contains the following information.

* `LabelContent` - used to get or set the axis label content.
* `Position` - used to get the position of label.