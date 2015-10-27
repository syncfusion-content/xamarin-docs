---
layout: post
title: Chart Axis
description: How to customize the grid lines, tick lines, labels and title of chart axis
platform: xamarin
control: Chart
documentation: ug
---

# Axis

**Charts** typically have two axes that are used to measure and categorize data: a vertical (Y) axis, and a horizontal (X) axis.

Vertical(Y) axis always uses numerical scale. Horizontal(X) axis supports the following types of scale:

* Category
* Numeric
* Date time

## Category Axis


Category axis displays text labels instead of numbers. 

{% highlight xml %}
[XAML]

<chart:SfChart.PrimaryAxis >

	<chart:CategoryAxis />

</chart:SfChart.PrimaryAxis>


{% endhighlight %}

{% highlight c# %}
[C#]

chart.PrimaryAxis = new CategoryAxis();


{% endhighlight %}

![D:/Chart UG/Xamarin/UG images/Xamarin UG Images/Merged UG Images/Axis- clubbed/CategoryAxis.png](axis_images/axis_img1.png)

### Placing labels between ticks

Labels in category axis can be placed between the ticks by setting **LabelPlacement** to **BetweenTicks**. Default value of **LabelPlacement** property is **OnTicks** i.e. labels will be placed on the ticks by default.

{% highlight xml %}
[XAML]

<chart:SfChart.PrimaryAxis >

	<chart:CategoryAxis LabelPlacement="BetweenTicks"/>

</chart:SfChart.PrimaryAxis>


{% endhighlight %}

{% highlight c# %}
[C#]

chart.PrimaryAxis = new CategoryAxis() { LabelPlacement = LabelPlacement.BetweenTicks };

{% endhighlight %}

![D:/Chart UG/Xamarin/UG images/Xamarin UG Images/Merged UG Images/Axis- clubbed/CategoryTicks.png](axis_images/axis_img2.png)

### Displaying labels after a fixed interval

To display labels after a fixed interval n, you can set **Interval** property of ChartAxis as **n**. Default value of interval is 1 i.e. all the labels will be displayed by default.

{% highlight xml %}
[XAML]

<chart:SfChart.PrimaryAxis >

	<chart:CategoryAxis Interval="2"/>

</chart:SfChart.PrimaryAxis>


{% endhighlight %}

{% highlight c# %}
[C#]

chart.PrimaryAxis = new CategoryAxis() { Interval = 2 };


{% endhighlight %}

![D:/Chart UG/Xamarin/UG images/Xamarin UG Images/Merged UG Images/Axis- clubbed/CategoryInterval.png](axis_images/axis_img3.png)


## Numeric Axis

Numeric axis uses numerical scale and displays numbers as labels. 

{% highlight xml %}
[XAML]

<chart:SfChart.PrimaryAxis >

	<chart:NumericalAxis/>

</chart:SfChart.PrimaryAxis>


{% endhighlight %}

{% highlight c# %}
[C#]

chart.PrimaryAxis = new NumericalAxis();

{% endhighlight %}

![D:/Chart UG/Xamarin/UG images/Xamarin UG Images/Merged UG Images/Axis- clubbed/numerical-1.png](axis_images/axis_img4.png)

### Customizing numeric range

To customize the range of an axis, you can use the **Minimum** and **Maximum** properties of **NumericalAxis**. By default, nice range will be calculated automatically based on the provided data.

{% highlight xml %}
[XAML]

<chart:SfChart.SecondaryAxis >

	<chart:NumericalAxis Minimum="10" Maximum="50"/>

</chart:SfChart. SecondaryAxis >

{% endhighlight %}

{% highlight c# %}
[C#]

chart.SecondaryAxis = new NumericalAxis() { Minimum = 10, Maximum = 50 };

{% endhighlight %}

![D:/Chart UG/Xamarin/UG images/Xamarin UG Images/Merged UG Images/Axis- clubbed/NumericRange.png](axis_images/axis_img5.png)

### Customizing numeric interval

Axis interval can be customized using the **Interval** property of ChartAxis. By default, nice interval will be calculated based on the minimum and maximum value of the provided data.

{% highlight xml %}
[XAML]

<chart:SfChart.SecondaryAxis >

	<chart:NumericalAxis Interval="10"/>

</chart:SfChart.SecondaryAxis >

{% endhighlight %}

{% highlight c# %}
[C#]

chart.SecondaryAxis = new NumericalAxis() { Interval = 10 };

{% endhighlight %}

![D:/Chart UG/Xamarin/UG images/Xamarin UG Images/Merged UG Images/Axis- clubbed/Numeric-Interval.png](axis_images/axis_img6.png)

### Apply padding to the range

Padding can be applied to the minimum and maximum extremes of the axis range by using **RangePadding** property. Numeric axis supports the following types of padding.

* None
* Round
* Additional
* Normal

**None**

When the value of **RangePadding** property is **none**, padding will not be applied to the axis. This is also the default value of **RangePadding** for horizontal axis.

{% highlight xml %}
[XAML]

<chart:SfChart.SecondaryAxis>

	<chart:NumericalAxis RangePadding="None"/>

</chart:SfChart.SecondaryAxis>


{% endhighlight %}

{% highlight c# %}
[C#]

chart.SecondaryAxis = new NumericalAxis() { RangePadding = NumericalPadding.None };

{% endhighlight %}

![D:/Chart UG/Xamarin/UG images/Xamarin UG Images/Merged UG Images/Axis- clubbed/NumericRangeNone.png](axis_images/axis_img7.png)

**Round**

When the value of **RangePadding** property is **Round**, axis range will be rounded to the nearest possible value divided by the interval.

{% highlight xml %}
[XAML]

<chart:SfChart.SecondaryAxis>

	<chart:NumericalAxis RangePadding="Round"/>

</chart:SfChart.SecondaryAxis>

{% endhighlight %}

{% highlight c# %}
[C#]

chart.SecondaryAxis = new NumericalAxis() { RangePadding = NumericalPadding.Round };

{% endhighlight %}

![D:/Chart UG/Xamarin/UG images/Xamarin UG Images/Merged UG Images/Axis- clubbed/NumericRangeRound.png](axis_images/axis_img8.png)

**Additional**

When the value of **RangePadding** property is **Additional**, axis range will be rounded and an interval of the axis will be added as padding to the minimum and maximum values of the range.

{% highlight xml %}
[XAML]

<chart:SfChart.SecondaryAxis>

	<chart:NumericalAxis RangePadding="Additional"/>

</chart:SfChart.SecondaryAxis>

{% endhighlight %}

{% highlight c# %}
[C#]

chart.SecondaryAxis = new NumericalAxis() { RangePadding = NumericalPadding.Additional };

{% endhighlight %}

![D:/Chart UG/Xamarin/UG images/Xamarin UG Images/Merged UG Images/Axis- clubbed/NuericRangeAdditional.png](axis_images/axis_img9.png)

**Normal**

When the value of **RangePadding** property is **Normal**, nice range will be calculated for the axis based on the best readability of the data. This is also the default for vertical axis.

{% highlight xml %}
[XAML]

<chart:SfChart.SecondaryAxis>

	<chart:NumericalAxis RangePadding="Normal"/>

</chart:SfChart.SecondaryAxis>

{% endhighlight %}

{% highlight c# %}
[C#]

chart.SecondaryAxis = new NumericalAxis() { RangePadding = NumericalPadding.Normal };

{% endhighlight %}

![D:/Chart UG/Xamarin/UG images/Xamarin UG Images/Merged UG Images/Axis- clubbed/NumericRangNormal.png](axis_images/axis_img10.png)

## Date Time Axis

Date time axis uses date time scale and displays date time values as axis labels in specified format. 

{% highlight xml %}
[XAML]

<chart:SfChart.PrimaryAxis >

	<chart:DateTimeAxis/>

</chart:SfChart.PrimaryAxis>

{% endhighlight %}

{% highlight c# %}
[C#]

chart.PrimaryAxis = new DateTimeAxis();

{% endhighlight %}

![D:/Chart UG/Xamarin/UG images/Xamarin UG Images/Merged UG Images/Axis1-clubbed/DateTime.png](axis_images/axis_img11.png)

### Customizing date time range

To customize the range of an axis, you can use the **Minimum** and **Maximum** properties of **DateTimeAxis**. By default, nice range will be calculated automatically based on the provided data.

{% highlight xml %}
[XAML]

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
[C#]

chart.PrimaryAxis = new DateTimeAxis() { Minimum = new DateTime(2010, 1, 1), Maximum = new DateTime(2015, 12, 30) };

{% endhighlight %}

![D:/Chart UG/Xamarin/UG images/Xamarin UG Images/Merged UG Images/Axis1-clubbed/DateTimeRange.png](axis_images/axis_img12.png)

### Date time intervals

Date time intervals can be customized using **Interval** and **IntervalType** properties of the date time axis. For example, setting **Interval** as **2** and **IntervalType** as **Years** will consider 2 years as interval.

Essential Chart supports the following types of interval for date time axis

* Years
* Months
* Days
* Hours
* Minutes
* Seconds
* Milliseconds

{% highlight xml %}

[XAML]

<chart:SfChart.PrimaryAxis>

	<chart:DateTimeAxis IntervalType="Months">

		<chart:DateTimeAxis.Interval>

			<Double>6</Double>

		</chart:DateTimeAxis.Interval>

	</chart:DateTimeAxis>

</chart:SfChart.PrimaryAxis>

{% endhighlight %}

{% highlight c# %}
[C#]

chart.PrimaryAxis = new DateTimeAxis() { IntervalType = DateTimeIntervalType.Months, Interval = 6 };

{% endhighlight %}

![D:/Chart UG/Xamarin/UG images/Xamarin UG Images/Merged UG Images/Axis1-clubbed/DateTimeInterval.png](axis_images/axis_img13.png)

### Apply padding to the range

Padding can be applied to the minimum and maximum extremes of the range by using **RangePadding** property. Date time axis supports the following types of padding:

* None
* Round
* Additional

**None**

When the value of **RangePadding** property is **None**, padding will not be applied to the axis. This is also the default value of **RangePadding**.

{% highlight xml %}
[XAML]

<chart:SfChart.PrimaryAxis>

	<chart:DateTimeAxis RangePadding="None"/>

</chart:SfChart.PrimaryAxis >

{% endhighlight %}

{% highlight c# %}
[C#]

chart.PrimaryAxis = new DateTimeAxis() { RangePadding = DateTimeRangePadding.None };

{% endhighlight %}

![D:/Chart UG/Xamarin/UG images/Xamarin UG Images/Merged UG Images/Axis1-clubbed/DateTimeNone.png](axis_images/axis_img14.png)

**Round**

When the value of **RangePadding** property is **round**, axis range will be rounded to the nearest possible date time value.

{% highlight xml %}
[XAML]

<chart:SfChart.PrimaryAxis >

	<chart:DateTimeAxis RangePadding="Round"/>

</chart:SfChart.PrimaryAxis >

{% endhighlight %}

{% highlight c# %}
[C#]

chart.PrimaryAxis = new DateTimeAxis() { RangePadding = DateTimeRangePadding.Round };

{% endhighlight %}

![D:/Chart UG/Xamarin/UG images/Xamarin UG Images/Merged UG Images/Axis1-clubbed/DateTimeRound.png](axis_images/axis_img15.png)

**Additional**

When the value of **RangePadding** property is **Additional**, range will be rounded and date time interval of the axis will be added as padding to the minimum and maximum extremes of the range.

{% highlight xml %}
[XAML]

<chart:SfChart.PrimaryAxis >

	<chart:DateTimeAxis RangePadding="Additional"/>

</chart:SfChart.PrimaryAxis >

{% endhighlight %}

{% highlight c# %}
[C#]

chart.PrimaryAxis = new DateTimeAxis() { RangePadding = DateTimeRangePadding.Additional };

{% endhighlight %}

![D:/Chart UG/Xamarin/UG images/Xamarin UG Images/Merged UG Images/Axis1-clubbed/DateTimeAdditional.png](axis_images/axis_img16.png)

## Common axis features

Customization of features such as axis title, labels, grid lines and tick lines are common to all the axes. Each of these features are explained in this section.

### Axis Visibility

Axis visibility can be controlled using the **IsVisible** property of axis. Default value of **IsVisible** property is **true**.

{% highlight xml %}
[XAML]

<chart:SfChart.SecondaryAxis>

	<chart:NumericalAxis IsVisible="False"/>

</chart:SfChart. SecondaryAxis >

{% endhighlight %}

{% highlight c# %}
[C#]

chart.SecondaryAxis.IsVisible = false;

{% endhighlight %}

![D:/Chart UG/Xamarin/UG images/Xamarin UG Images/Merged UG Images/Axis1-clubbed/AxisVisible.png](axis_images/axis_img17.png)

### Axis title

The **Title** property in axis provides options to customize the text and font of axis title. Axis does not display title by default. The title can be customized using following properties,

* **Text** – used to set the title for axis.
* **TextColor** – used to change the color of the label.
* **BackgroundColor** – used to change the label background color.
* **BorderColor** – used to change the border color.
* **BorderWidth** – used to change the width of the border.
* **Font** – used to change the text size, font family and font weight.
* **Margin** - used to change the margin size for labels.

Following code snippet illustrates how to enable and customize the axis title.

{% highlight xml %}
[XAML]

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
[C#]

chart.PrimaryAxis.Title.Text = "Month";

chart.PrimaryAxis.Title.TextColor = Color.Blue;

chart.PrimaryAxis.Title.Font = Font.SystemFontOfSize(20, FontAttributes.Bold);


{% endhighlight %}

![D:/Chart UG/Xamarin/UG images/Xamarin UG Images/Merged UG Images/Axis1-clubbed/Axis-title.png](axis_images/axis_img18.png)

### Label customization

The **LabelStyle** property of axis provides options to customize the font-family, color, size and font-weight of axis labels. The axis labels can be customized using following properties:

* **TextColor** – used to change the color of the labels.
* **BackgroundColor** – used to change the label background color.
* **BorderColor** – used to change the border color.
* **BorderThickness** – used to change the thickness of the border.
* **Font** – used to change the text size, font family and font weight.
* **Margin** - used to change the margin size for labels.

{% highlight xml %}
[XAML]

<chart:SfChart.PrimaryAxis>

	<chart: CategoryAxis >

		<chart: CategoryAxis.LabelStyle>

			<chart:ChartAxisLabelStyle TextColor="Red">

				<chart:ChartAxisLabelStyle.Font>

					<Font FontSize="20" FontAttributes ="Bold"/>

				</chart:ChartAxisLabelStyle.Font>

			</chart:ChartAxisLabelStyle>

		</chart: CategoryAxis.LabelStyle>

	</chart:CategoryAxis>

</chart:SfChart.PrimaryAxis>

{% endhighlight %}

{% highlight c# %}
[C#]

chart.PrimaryAxis.LabelStyle.Font = Font.SystemFontOfSize(20, FontAttributes.Bold);

chart.PrimaryAxis.LabelStyle.TextColor = Color.Red;

{% endhighlight %}

![D:/Chart UG/Xamarin/UG images/Xamarin UG Images/Merged UG Images/Axis1-clubbed/AxisLabelStyle.png](axis_images/axis_img19.png)

### Label and tick positioning

Axis labels and ticks can be positioned inside or outside the chart area by using **LabelStyle**.**LabelsPosition** and **LabelStyle**.**TickPosition** properties of ChartAxis. By default labels and ticks will be positioned outside the chart area.

{% highlight xml %}
[XAML]

<chart:SfChart.PrimaryAxis >

	<chart:DateTimeAxis TickPosition="Inside">

		<chart:DateTimeAxis.LabelStyle>

			<chart:ChartAxisLabelStyle LabelsPosition="Inside"/>
		
		</chart:DateTimeAxis.LabelStyle>

	</chart:DateTimeAxis>

</chart:SfChart.PrimaryAxis >

{% endhighlight %}

{% highlight c# %}
[C#]

chart.PrimaryAxis.LabelStyle.LabelsPosition = AxisElementPosition.Inside;

chart.PrimaryAxis.TickPosition = AxisElementPosition.Inside;

{% endhighlight %}

![D:/Chart UG/Xamarin/UG images/Xamarin UG Images/Merged UG Images/Axis1-clubbed/AxisTick.png](axis_images/axis_img20.png)

### Edge labels placement

Labels with long text at the edges of an axis may appear partially outside the chart. The **EdgeLabelsDrawingMode** property can be used to avoid the partial appearance of labels at the corners.

{% highlight xml %}
[XAML]

<chart:CategoryAxis EdgeLabelsDrawingMode="Shift"/>

{% endhighlight %}

{% highlight c# %}
[C#]

chart.PrimaryAxis.EdgeLabelsDrawingMode = EdgeLabelsDrawingMode.Shift;

{% endhighlight %}

![D:/Chart UG/Xamarin/UG images/Xamarin UG Images/Merged UG Images/Axis1-clubbed/edgeLabel.png](axis_images/axis_img21.png)

### Grid lines customization

The **ShowMajorGridLines** and **ShowMinorGridLines** properties are used to control the visibility of grid lines. **MajorGridLineStyle** and **MinorGridLineStyle** properties in axis are used to customize the major grid lines and minor grid lines of an axis respectively. They provide options to change the width, dashes, color of grid lines. By default minor grid lines will not be visible. 

{% highlight xml %}
[XAML]

<chart:SfChart. SecondaryAxis >

	<chart: NumericalAxis ShowMajorGridLines="True" ShowMinorGridLines="True" MinorTicksPerInterval="1"/>

</chart:SfChart. SecondaryAxis >

{% endhighlight %}

{% highlight c# %}
[C#]

chart. SecondaryAxis = new NumericalAxis ()

{

	ShowMajorGridLines = true,

	ShowMinorGridLines = true,

	MinorTicksPerInterval = 1

};

{% endhighlight %}

![D:/Chart UG/Xamarin/UG images/Xamarin UG Images/Merged UG Images/Axis1-clubbed/AxisGridLine.png](axis_images/axis_img22.png)

### Tick lines customization

The **MajorTickStyle** and **MinorTickStyle** properties in axis are used to customize the major tick lines of an axis and minor tick lines of an axis respectively. They provide options to change the width, size, color and visibility of tick lines. By default minor tick lines will not be visible.

{% highlight xml %}
[XAML]

<chart:SfChart. SecondaryAxis >

	<chart: NumericalAxis ShowMinorGridLines="True" MinorTicksPerInterval="1">

		<chart: NumericalAxis.MajorTickStyle >

			<chart:ChartAxisTickStyle TickSize="7" StrokeColor="Blue" StrokeWidth="3"/>

		</chart: NumericalAxis.MajorTickStyle>

		<chart: NumericalAxis.MinorTickStyle>

			<chart:ChartAxisTickStyle TickSize="5" StrokeColor="Green" StrokeWidth="2"/>

		</chart: NumericalAxis.MinorTickStyle>

	<chart:NumericalAxis/>

</chart:SfChart. SecondaryAxis >

{% endhighlight %}

{% highlight c# %}
[C#]

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

![D:/Chart UG/Xamarin/UG images/Xamarin UG Images/Merged UG Images/Axis1-clubbed/AxisTickStyle.png](axis_images/axis_img23.png)

### Inversing axis

Axis can be inversed using the **IsInversed** property of axis. Default value of **IsInversed** property is **false**.

{% highlight c# %}
[XAML]

<chart:SfChart. SecondaryAxis >

	<chart:NumericalAxis IsInversed="True">

</chart:SfChart. SecondaryAxis >

{% endhighlight %}

{% highlight c# %}
[C#]

chart.SecondaryAxis.IsInversed = true;

{% endhighlight %}

![D:/Chart UG/Xamarin/UG images/Xamarin UG Images/Merged UG Images/Axis1-clubbed/AxisInverse.png](axis_images/axis_img24.png)

### Placing axes at the opposite side

The **OpposedPosition** property of axis can be used to place the axis at the opposite side of its default position. Default value of **OpposedPosition** property is **false**. 

{% highlight xml %}
[XAML]

<chart:SfChart. SecondaryAxis >

	<chart:NumericalAxis OpposedPosition="True">

</chart:SfChart. SecondaryAxis >

{% endhighlight %}

{% highlight c# %}
[C#]

chart.SecondaryAxis.OpposedPosition = true;

{% endhighlight %}

![D:/Chart UG/Xamarin/UG images/Xamarin UG Images/Merged UG Images/Axis1-clubbed/AxisOpposedposition.png](axis_images/axis_img25.png)

### Maximum number of labels per 100 pixels

By default, a maximum of 3 labels are displayed for each 100 pixels in axis. The maximum number of labels that should be present within 100 pixels length can be customized using the **MaximumLabels** property of an axis. This property is applicable only for automatic range calculation and will not work if you set value for **Interval** property of an axis.

{% highlight xml %}
[XAML]

<chart:SfChart. SecondaryAxis >

	<chart:NumericalAxis MaximumLabels="5"/>

</chart:SfChart. SecondaryAxis >

{% endhighlight %}

{% highlight c# %}
[C#]

Chart.SecondaryAxis.MaximumLabels = 5;

{% endhighlight %}

![D:/Chart UG/Xamarin/UG images/Xamarin UG Images/Merged UG Images/Axis1-clubbed/AxisMaximumLab.png](axis_images/axis_img26.png)

## Smart Axis Labels

Axis labels may overlap with each other based on chart dimensions and label size. The **LabelsIntersectAction** property of axis is useful in avoiding the overlapping of axis labels with each other. Default value of **LabelsIntersectAction** is **None**. Other available values of **LabelsIntersectAction** are **MultipleRows** and **Hide**.

{% highlight xml %}
[XAML]

<chart:SfChart.PrimaryAxis >

	<chart:CategoryAxis LabelsIntersectAction="MultipleRows"/>

</chart:SfChart.PrimaryAxis >

{% endhighlight %}

{% highlight c# %}
[C#]

chart.PrimaryAxis.LabelsIntersectAction = AxisLabelsIntersectAction.MultipleRows;

{% endhighlight %}

![D:/Chart UG/Xamarin/UG images/Xamarin UG Images/Merged UG Images/Axis1-clubbed/smartlabel.png](axis_images/axis_img27.png)