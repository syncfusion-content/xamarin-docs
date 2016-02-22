---
layout: post
title: Chart Striplines
description: Learn how to add horizontal or vertical lines in Chart. 
platform: xamarin
control: Chart
documentation: ug
---

# Strip Lines

## What is strip line?

Strip lines are used to shade the different ranges in plot area in different colors to improve the readability of the chart. You can annotate it with text to indicate what that particular region indicates. You can also enable the strip lines to be drawn repeatedly at regular intervals – this will be useful when you want to mark an event that occurs recursively along the timeline of the chart.

## How to add strip lines?

Strip line is classified into **NumericalStripLine** and **DateTimeStripLine** based on the type of input you provide to draw the strip line. Since strip lines are drawn based on the axis, you have to add strip line instance using the `StripLines` property of the respective axis. You can also add multiple strip lines to an axis.

Following properties are used to configure the strip line.

* `Start` – used to change the start position of the strip line.
* `Width` – used to change how long strip line should expand.
* `Text` – used to change the text of the strip line.
* `FillColor` – used to change the fill color of the strip line.
* `StrokeWidth` – used to change the stroke width of the strip line.
* `StrokeColor` – used to change the stroke color of the strip line.

**NumericalStripLine**

`NumericalStripLine` are used to draw strip lines for `NumericalAxis` and `CategoryAxis`. To add a strip line, create an instance of `NumericalStripLine` and add to the `StripLines` collection property of the respective axis.

{% tabs %} 

{% highlight xaml %}

<chart:SfChart.SecondaryAxis>

	<chart:NumericalAxis Maximum="52" Minimum="28">      

		<chart:NumericalAxis.StripLines>         

			<chart:NumericalStripLine Start="36" Width ="8" Text="Average Temperature" FillColor="#F4C762"/>

		</chart:NumericalAxis.StripLines>

	</chart:NumericalAxis>

</chart:SfChart.SecondaryAxis>

{% endhighlight %}

{% highlight c# %}

NumericalAxis numericalAxis = new NumericalAxis() 
{

	Minimum=28, 
	Maximum=52 

};

chart.SecondaryAxis = numericalAxis;

NumericalStripLine stripLine1 = new NumericalStripLine() 
{ 

	Start = 36,  
	Width = 8, 
	Text = "Average Temperature",
	FillColor = Color.FromHex("#F4C762") 

};

numericalAxis.StripLines.Add(stripLine1);

{% endhighlight %}

{% endtabs %}

![](striplines_images/stripline_img1.png)

**DateTimeStripLine**

As the name indicates, `DateTimeStripLine` are used to draw strip lines for `DateTimeAxis`. To add a strip line for `DateTimeAxis`, create an instance of `DateTimeStripLine` and add to the `StripLines` collection property of `DateTimeAxis`.

{% tabs %} 

{% highlight xaml %}

<chart:SfChart.PrimaryAxis  >

	<chart:DateTimeAxis>

		<chart:DateTimeAxis.StripLines>         

			<chart:DateTimeStripLine WidthType="Month" Width ="3" Text="Quarter-2" FillColor="#3FAA38">

				<chart:DateTimeStripLine.Start>

					<sys:DateTime x:FactoryMethod="Parse">

						<x:Arguments>

							<x:String>Apr 01 2000</x:String>

						</x:Arguments>

					</sys:DateTime>

				</chart:DateTimeStripLine.Start>

			</chart:DateTimeStripLine >

		</chart:DateTimeAxis.StripLines>

	</chart:DateTimeAxis>

</chart:SfChart.PrimaryAxis>

{% endhighlight %}

{% highlight c# %}

DateTimeAxis dateTimeAxis  =  new DateTimeAxis() 
{

	Interval = 3, 
	IntervalType = DateTimeIntervalType.Months,
	Minimum =  new DateTime(2000, 01,01), 
	Maximum = new DateTime(2000, 12, 30)

};

chart.PrimaryAxis = dateTimeAxis;

DateTimeStripLine stripLine = new DateTimeStripLine() 
{ 

	Start = new DateTime(2000, 04, 01), 
	WidthType = DateTimeComponent.Month, 
	Width = 3, 
	Text = "Quarter-2",
	FillColor = Color.FromHex("#3FAA38")

};

dateTimeAxis.StripLines.Add(stripLine);

{% endhighlight %}

{% endtabs %}

![](striplines_images/stripline_img2.png)

## Strip Line Recurrence

This feature is used to enable the strip lines to be drawn repeatedly at the regular intervals – this will be useful when you want to mark an event that occurs recursively along the timeline of the chart. Following properties are used to configure this feature.

* `RepeatEvery` – used to change the frequency of the strip line being repeated.
* `RepeatUntil` – specifies the end value at which point strip line has to stop repeating.

Following code snippet and screenshot demonstrates this feature by highlighting weekends. 

{% tabs %} 

{% highlight xaml %}

<chart:SfChart.PrimaryAxis>

	<chart:NumericalAxis>

		<chart:NumericalAxis.StripLines>

			<chart:NumericalStripLine Start="6" Width ="1" RepeatEvery="7" Text="Weekend" FillColor="#ECE6F1">

				<chart:NumericalStripLine.LabelStyle>

					<chart:ChartStripLineLabelStyle Angle="270" TextColor="Red"/>

				</chart:NumericalStripLine.LabelStyle>

			</chart:NumericalStripLine>

		</chart:NumericalAxis.StripLines>

	</chart:NumericalAxis>

</chart:SfChart.PrimaryAxis>

{% endhighlight %}

{% highlight c# %}

NumericalAxis numericalAxis = new NumericalAxis() 
{ 

	EdgeLabelsDrawingMode = EdgeLabelsDrawingMode.Shift

};

sfChart.PrimaryAxis = numericalAxis;

NumericalStripLine stripLine = new NumericalStripLine();

stripLine.FillColor = Color.FromHex("FFECE6F1");

stripLine.Start = 6;

stripLine.Width = 1;

stripLine.RepeatEvery = 7;

stripLine.Text = "Weekend";

stripLine.LabelStyle.Angle = 270;

stripLine.LabelStyle.TextColor = Color.Red;          

numericalAxis.StripLines.Add(stripLine);

{% endhighlight %}

{% endtabs %}

![](striplines_images/stripline_img3.png)

## Customize Text

The `LabelStyle` property provide options to customize the font-family, color, size and font-weight of strip line text. Following are the options available,

* `TextColor` – used to change the color of the text.
* `BackgroundColor` – used to change the label background color.
* `BorderColor` – used to change the border color.
* `BorderThickness` – used to change the thickness of the border.
* `Font`– used to change the text size, font family and font weight.
* `Margin` - used to change the margin size for text.
* `Angle` – used to rotate the text.
* `HorizontalAlignment` – used to change the horizontal alignment of text.
* `VerticalAlignment`  - used to change the vertical alignment of text.

{% tabs %} 

{% highlight xaml %}

<chart:SfChart.SecondaryAxis>

	<chart:NumericalAxis Maximum="30" Minimum="48">      

		<chart:NumericalAxis.StripLines>        

			<chart:NumericalStripLine Start="42" Width ="6" Text="High Temperature" FillColor="#EF7878">

				<chart:NumericalStripLine.LabelStyle>

					<chart:ChartStripLineLabelStyle HorizontalAlignment="Near" VerticalAlignment="Center" TextColor="Blue">

						<chart:ChartStripLineLabelStyle.Font>

							<Font FontSize="20" />

						</chart:ChartStripLineLabelStyle.Font>

					</chart:ChartStripLineLabelStyle>              

				</chart:NumericalStripLine.LabelStyle>

			</chart:NumericalStripLine>

		</chart:NumericalAxis.StripLines>

	</chart:NumericalAxis>

</chart:SfChart.SecondaryAxis>

{% endhighlight %}

{% highlight c# %}

NumericalAxis numericalAxis = new NumericalAxis() 
{
	
	Minimum=30, 
	Maximum=48 
	
};

chart.SecondaryAxis = numericalAxis;

chart.SecondaryAxis.Title.Text = "Temperature in Celsius";

NumericalStripLine stripLine = new NumericalStripLine() 
{ 
	
	Start = 42, 
	Width = 6, 
	Text = "High Temperature", 
	FillColor = Color.FromHex("#EF7878") 
	
};    

stripLine.LabelStyle.TextColor = Color.Blue;

stripLine.LabelStyle.Font = Font.SystemFontOfSize(20);    

stripLine.LabelStyle.HorizontalAlignment = ChartLabelAlignment.Near;

stripLine.LabelStyle.VerticalAlignment = ChartLabelAlignment.Center;    

numericalAxis.StripLines.Add(stripLine);

{% endhighlight %}

{% endtabs %}

![](striplines_images/stripline_img4.png)

## Segmented StripLine

Typically, if you draw a strip line for a vertical axis, the height of the strip line is determined by the `Start` and `Width` properties and width of the strip line is equivalent to the width of its associated horizontal axis i.e., strip line is drawn horizontally to the entire stretch of its associated horizontal axis. Similarly, for horizontal axis, width is determined by `Start` and `Width` properties, and vertically, it is drawn to the entire stretch of the associated vertical axis.

Suppose, you want to draw a strip line that should not stretch along its associated axis, you have to set `SegmentStart` and `SegmentEnd` properties. Values provided in these two properties correspond to its associated axis specified by `SegmentAxisName` property. Finally, you need to set `IsSegmented` property to true to indicate that strip line should be drawn as a segment.

* `IsSegmented` – Used to enable / disable the segmented strip line.
* `SegmentStart` – Used to change the segment start value. Value correspond to associated axis.
* `SegmentEnd` – Used to change the segment end value. Value correspond to associated axis.
* `SegmentAxisName` – Specify the name of the associated axis name.

N> You can set the double or DateTime value for SegmentStart and SegmentEnd properties based on the associated axis type.

Following code snippet shows how to set the segment start and end value if the associated axis type is numerical.

{% tabs %} 

{% highlight xaml %}

<chart:SfChart.PrimaryAxis>

	<chart:CategoryAxis EdgeLabelsDrawingMode="Shift" Interval="3">

		<chart:CategoryAxis.StripLines>

			<chart:NumericalStripLine IsSegmented="True" SegmentAxisName="Amount" SegmentStart="40" SegmentEnd="46" Start="3" Width ="3" Text="Quarter-2" FillColor="#EF7878"/>

		</chart:CategoryAxis.StripLines>

	</chart:CategoryAxis>        

</chart:SfChart.PrimaryAxis>

<chart:SfChart.SecondaryAxis>

	<chart:NumericalAxis Minimum="30" Maximum="48" Name="Amount"/>          

</chart:SfChart.SecondaryAxis>

{% endhighlight %}

{% highlight c# %}

NumericalStripLine stripLine = new NumericalStripLine()

{

	Start = 3,
	Width = 3,
	Text = "Quarter-2",
	FillColor = Color.FromHex("#EF7878"),
	IsSegmented = true,
	SegmentAxisName = "Amount",
	SegmentStart = 40,
	SegmentEnd = 46

};

CategoryAxis categoryAxis = new CategoryAxis()
{

	EdgeLabelsDrawingMode = EdgeLabelsDrawingMode.Shift,
	Interval = 3

};

NumericalAxis numericalAxis = new NumericalAxis() 
{ 

	Minimum = 30, 
	Maximum = 48,
	Name = "Amount"

};

categoryAxis.StripLines.Add(stripLine);
chart.PrimaryAxis = categoryAxis;
chart.SecondaryAxis = numericalAxis;

{% endhighlight %}

{% endtabs %}

![](striplines_images/stripline_img5.png)

Following code snippet shows how to set the segment start and end value if the associated axis type is date time. 

{% tabs %} 

{% highlight xaml %}

<chart:SfChart.PrimaryAxis>

	<chart:DateTimeAxis EdgeLabelsDrawingMode="Shift" Name="Period"/>

</chart:SfChart.PrimaryAxis>

<chart:SfChart.SecondaryAxis>

	<chart:NumericalAxis>

		<chart:NumericalAxis.StripLines>

			<chart:NumericalStripLine IsSegmented="True" SegmentAxisName="Period" Start="42" Width ="4" Text="Quarter-2" FillColor="#3FAA38">

				<chart:NumericalStripLine.SegmentStart>

					<sys:DateTime x:FactoryMethod="Parse">

						<x:Arguments>

							<x:String>Jan 1 2000</x:String>

						</x:Arguments>

					</sys:DateTime>

				</chart:NumericalStripLine.SegmentStart>

				<chart:NumericalStripLine.SegmentEnd>

					<sys:DateTime x:FactoryMethod="Parse">

						<x:Arguments>

							<x:String>Jun 30 2000</x:String>

						</x:Arguments>

					</sys:DateTime>

				</chart:NumericalStripLine.SegmentEnd>

			</chart:NumericalStripLine>

		</chart:NumericalAxis.StripLines>

	</chart:NumericalAxis>

</chart:SfChart.SecondaryAxis>

{% endhighlight %}

{% highlight c# %}

NumericalStripLine stripLine = new NumericalStripLine()
{

	Start = 42,
	Width = 4,
	Text = "Quarter-2",
	FillColor = Color.FromHex("#3FAA38"),
	IsSegmented = true,
	SegmentAxisName = "Period",
	SegmentStart = new DateTime(2000, 4, 1),
	SegmentEnd = new DateTime(2000, 6, 30)

};

chart.PrimaryAxis = new DateTimeAxis() 
{ 

	EdgeLabelsDrawingMode = EdgeLabelsDrawingMode.Shift, 
	Name = "Period" 
	
};

NumericalAxis numericalAxis = new NumericalAxis() 
{ 

	Minimum = 30, 
	Maximum = 48 

};

chart.SecondaryAxis = numericalAxis;

numericalAxis.StripLines.Add(stripLine);

{% endhighlight %}

{% endtabs %}

![](striplines_images/stripline_img6.png)