---
layout: post
title: Chart Striplines
description: Learn how to add horizontal or vertical lines in Chart. 
platform: xamarin
control: Chart
documentation: ug
---

# Striplines

## What is stripline?

Striplines are used to shade the different ranges in different colors in plot area to improve the readability of a chart. You can annotate the striplines with text to indicate the particular region. You can also enable the striplines to be drawn repeatedly at regular intervals—this will be used when you want to mark an event that occurs recursively along the timeline of a chart.

## How to add striplines?

A stripline is classified into **NumericalStripLine** and **DateTimeStripLine** based on the type of input you provide to draw the stripline. Since the striplines are drawn based on the axis, you have to add a stripline instance using the [`StripLines`](http://help.syncfusion.com/cr/cref_files/xamarin/sfchart/Syncfusion.SfChart.XForms~Syncfusion.SfChart.XForms.ChartStripLine.html#) property of the respective axis. You can also add multiple striplines to an axis.

The following properties are used to configure the striplines:

* [`Start`](http://help.syncfusion.com/cr/cref_files/xamarin/sfchart/Syncfusion.SfChart.XForms~Syncfusion.SfChart.XForms.ChartStripLine~SegmentStartProperty.html#)—Used to change the start position of the stripline.
* [`Width`](http://help.syncfusion.com/cr/cref_files/xamarin/sfchart/Syncfusion.SfChart.XForms~Syncfusion.SfChart.XForms.ChartStripLine~WidthProperty.html#)—Used to change the expanding length of the stripline.
* [`Text`](http://help.syncfusion.com/cr/cref_files/xamarin/sfchart/Syncfusion.SfChart.XForms~Syncfusion.SfChart.XForms.ChartStripLine~TextProperty.html#)—Used to change the text of the stripline.
* [`FillColor`](http://help.syncfusion.com/cr/cref_files/xamarin/sfchart/Syncfusion.SfChart.XForms~Syncfusion.SfChart.XForms.ChartStripLine~FillColorProperty.html#)—Used to change the fill color of the stripline.
* [`StrokeWidth`](http://help.syncfusion.com/cr/cref_files/xamarin/sfchart/Syncfusion.SfChart.XForms~Syncfusion.SfChart.XForms.ChartStripLine~StrokeWidthProperty.html#)—Used to change the stroke width of the stripline.
* [`StrokeColor`](http://help.syncfusion.com/cr/cref_files/xamarin/sfchart/Syncfusion.SfChart.XForms~Syncfusion.SfChart.XForms.ChartStripLine~StrokeColorProperty.html#)—Used to change the stroke color of the stripline.

**NumericalStripLine**

The [`NumericalStripLine`](http://help.syncfusion.com/cr/cref_files/xamarin/sfchart/Syncfusion.SfChart.XForms~Syncfusion.SfChart.XForms.NumericalStripLine.html#) property is used to draw the striplines for [`NumericalAxis`](http://help.syncfusion.com/cr/cref_files/xamarin/sfchart/Syncfusion.SfChart.XForms~Syncfusion.SfChart.XForms.NumericalAxis.html#) and [`CategoryAxis`](http://help.syncfusion.com/cr/cref_files/xamarin/sfchart/Syncfusion.SfChart.XForms~Syncfusion.SfChart.XForms.CategoryAxis.html#). To add a stripline, create an instance of the [`NumericalStripLine`](http://help.syncfusion.com/cr/cref_files/xamarin/sfchart/Syncfusion.SfChart.XForms~Syncfusion.SfChart.XForms.NumericalStripLine.html#), and add that instance to the [`StripLines`](http://help.syncfusion.com/cr/cref_files/xamarin/sfchart/Syncfusion.SfChart.XForms~Syncfusion.SfChart.XForms.ChartStripLine.html#) collection property of the respective axis.

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

As the name indicates, the [`DateTimeStripLine`](http://help.syncfusion.com/cr/cref_files/xamarin/sfchart/Syncfusion.SfChart.XForms~Syncfusion.SfChart.XForms.DateTimeStripLine.html#) property is used to draw the striplines for [`DateTimeAxis`](http://help.syncfusion.com/cr/cref_files/xamarin/sfchart/Syncfusion.SfChart.XForms~Syncfusion.SfChart.XForms.DateTimeAxis.html#). To add a stripline for [`DateTimeAxis`](http://help.syncfusion.com/cr/cref_files/xamarin/sfchart/Syncfusion.SfChart.XForms~Syncfusion.SfChart.XForms.DateTimeAxis.html#), create an instance of the [`DateTimeStripLine`](http://help.syncfusion.com/cr/cref_files/xamarin/sfchart/Syncfusion.SfChart.XForms~Syncfusion.SfChart.XForms.DateTimeStripLine.html#), and add that instance to the [`StripLines`](http://help.syncfusion.com/cr/cref_files/xamarin/sfchart/Syncfusion.SfChart.XForms~Syncfusion.SfChart.XForms.ChartStripLine.html#) collection property of [`DateTimeAxis`](http://help.syncfusion.com/cr/cref_files/xamarin/sfchart/Syncfusion.SfChart.XForms~Syncfusion.SfChart.XForms.DateTimeAxis.html#).

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

## Stripline recurrence

This feature is used to enable the striplines to be drawn repeatedly at the regular intervals – this will be used when you want to mark an event that occurs recursively along the timeline of a chart. The following properties are used to configure this feature:

* [`RepeatEvery`](http://help.syncfusion.com/cr/cref_files/xamarin/sfchart/Syncfusion.SfChart.XForms~Syncfusion.SfChart.XForms.ChartStripLine~RepeatEvery.html#)—Used to change the frequency of the strip line that is being repeated.
* [`RepeatUntil`](https://help.syncfusion.com/cr/cref_files/xamarin/sfchart/Syncfusion.SfChart.XForms~Syncfusion.SfChart.XForms.NumericalStripLine~RepeatUntil.html)—Specifies the end value at which point of the strip line has to be stopped repeating.

The following code snippet and screenshot demonstrates this feature by highlighting the weekends. 

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

## Customize text

The [`LabelStyle`](http://help.syncfusion.com/cr/cref_files/xamarin/sfchart/Syncfusion.SfChart.XForms~Syncfusion.SfChart.XForms.ChartStripLine~LabelStyle.html#) property provides options to customize the font-family, font-color, font-size, and font-weight of the stripline text. The following are available in the `LabelStyle` property:

* [`TextColor`](http://help.syncfusion.com/cr/cref_files/xamarin/sfchart/Syncfusion.SfChart.XForms~Syncfusion.SfChart.XForms.ChartLabelStyle~TextColor.html#)—Used to change the color of the text.
* [`BackgroundColor`](http://help.syncfusion.com/cr/cref_files/xamarin/sfchart/Syncfusion.SfChart.XForms~Syncfusion.SfChart.XForms.ChartLabelStyle~BackgroundColor.html#)—Used to change the background color of the label.
* [`BorderColor`](http://help.syncfusion.com/cr/cref_files/xamarin/sfchart/Syncfusion.SfChart.XForms~Syncfusion.SfChart.XForms.ChartLabelStyle~BorderColor.html#)—Used to change the border color.
* [`BorderThickness`](http://help.syncfusion.com/cr/cref_files/xamarin/sfchart/Syncfusion.SfChart.XForms~Syncfusion.SfChart.XForms.ChartLabelStyle~BorderThickness.html#)—Used to change the thickness of the border.
* [`Font`](http://help.syncfusion.com/cr/cref_files/xamarin/sfchart/Syncfusion.SfChart.XForms~Syncfusion.SfChart.XForms.ChartLabelStyle~Font.html#)—Used to change the text size, font-family, and font-weight.
* [`Margin`](http://help.syncfusion.com/cr/cref_files/xamarin/sfchart/Syncfusion.SfChart.XForms~Syncfusion.SfChart.XForms.ChartLabelStyle~Margin.html#)—Used to change the margin size of the text.
* [`Angle`](http://help.syncfusion.com/cr/cref_files/xamarin/sfchart/Syncfusion.SfChart.XForms~Syncfusion.SfChart.XForms.ChartStripLineLabelStyle~Angle.html#)—Used to rotate the text.
* [`HorizontalAlignment`](http://help.syncfusion.com/cr/cref_files/xamarin/sfchart/Syncfusion.SfChart.XForms~Syncfusion.SfChart.XForms.ChartStripLineLabelStyle~HorizontalAlignment.html#)—Used to change the horizontal alignment of text.
* [`VerticalAlignment`](http://help.syncfusion.com/cr/cref_files/xamarin/sfchart/Syncfusion.SfChart.XForms~Syncfusion.SfChart.XForms.ChartStripLineLabelStyle~VerticalAlignment.html#)—Used to change the vertical alignment of text.

{% tabs %} 

{% highlight xaml %}

<chart:SfChart.SecondaryAxis>

	<chart:NumericalAxis Maximum="30" Minimum="48">      

		<chart:NumericalAxis.StripLines>        

			<chart:NumericalStripLine Start="42" Width ="6" Text="High Temperature" FillColor="#EF7878">

				<chart:NumericalStripLine.LabelStyle>

					<chart:ChartStripLineLabelStyle HorizontalAlignment="Near" VerticalAlignment="Center" TextColor="Blue" Font="20"/>
       
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

## Segmented striplines

Typically, if you draw a stripline for a vertical axis, the height of the stripline will be determined by the [`Start`](http://help.syncfusion.com/cr/cref_files/xamarin/sfchart/Syncfusion.SfChart.XForms~Syncfusion.SfChart.XForms.ChartStripLine~SegmentStart.html#) and [`Width`](http://help.syncfusion.com/cr/cref_files/xamarin/sfchart/Syncfusion.SfChart.XForms~Syncfusion.SfChart.XForms.ChartStripLine~Width.html#) properties. The width of the stripline is equivalent to the width of its associated horizontal axis, i.e., stripline will be drawn horizontally to the entire stretch of its associated horizontal axis. For horizontal axis, similar to the vertical axis, width is determined by the [`Start`](http://help.syncfusion.com/cr/cref_files/xamarin/sfchart/Syncfusion.SfChart.XForms~Syncfusion.SfChart.XForms.ChartStripLine~SegmentStart.html#) and [`Width`](http://help.syncfusion.com/cr/cref_files/xamarin/sfchart/Syncfusion.SfChart.XForms~Syncfusion.SfChart.XForms.ChartStripLine~Width.html#) properties, but it will be drawn to the entire stretch of the associated vertical axis.

Suppose, if you want to draw a stripline that should not stretch along its associated axis, set the [`SegmentStart`](http://help.syncfusion.com/cr/cref_files/xamarin/sfchart/Syncfusion.SfChart.XForms~Syncfusion.SfChart.XForms.ChartStripLine~SegmentStart.html#) and [`SegmentEnd`](http://help.syncfusion.com/cr/cref_files/xamarin/sfchart/Syncfusion.SfChart.XForms~Syncfusion.SfChart.XForms.ChartStripLine~SegmentEnd.html#) properties. Values provided in these two properties correspond to its associated axis are specified by the [`SegmentAxisName`](http://help.syncfusion.com/cr/cref_files/xamarin/sfchart/Syncfusion.SfChart.XForms~Syncfusion.SfChart.XForms.ChartStripLine~SegmentAxisName.html#) property. Finally, set the [`IsSegmented`](http://help.syncfusion.com/cr/cref_files/xamarin/sfchart/Syncfusion.SfChart.XForms~Syncfusion.SfChart.XForms.ChartStripLine~IsSegmented.html#) property to true to indicate that stripline should be drawn as a segment.

* [`IsSegmented`](http://help.syncfusion.com/cr/cref_files/xamarin/sfchart/Syncfusion.SfChart.XForms~Syncfusion.SfChart.XForms.ChartStripLine~IsSegmented.html#)—Used to enable/disable the segmented stripline.
* [`SegmentStart`](http://help.syncfusion.com/cr/cref_files/xamarin/sfchart/Syncfusion.SfChart.XForms~Syncfusion.SfChart.XForms.ChartStripLine~SegmentStart.html#)—Used to change the segment start value. The value corresponds to its associated axis.
* [`SegmentEnd`](http://help.syncfusion.com/cr/cref_files/xamarin/sfchart/Syncfusion.SfChart.XForms~Syncfusion.SfChart.XForms.ChartStripLine~SegmentEnd.html#)—Used to change the segment end value. The value corresponds to its associated axis.
* [`SegmentAxisName`](http://help.syncfusion.com/cr/cref_files/xamarin/sfchart/Syncfusion.SfChart.XForms~Syncfusion.SfChart.XForms.ChartStripLine~SegmentAxisName.html#)—Specifies the name of a associated axis.

N> You can set the `double` or `DateTime` value for the `SegmentStart` and `SegmentEnd` properties based on the associated axis type.

The following code snippet shows how to set the segment start and end values if the associated axis type is numerical.

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

The following code snippet shows how to set the segment start and end values if the associated axis type is date-time. 

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