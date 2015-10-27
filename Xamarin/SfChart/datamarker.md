---
layout: post
title: Markers and data labels in Essential Xamarin.Forms Chart
description: Learn how to add markers and data point labels to a Chart series
platform: xamarin
control: Chart
documentation: ug
---

# Data Markers

Data markers are used to provide information about the data points to the user. You can add a shape and label to adorn each data point. This can be enabled using following code snippet,

{% highlight xml %}
[XAML]

<chart:LineSeries>

	<chart:LineSeries.DataMarker>

		<chart:ChartDataMarker/>

	</chart:LineSeries.DataMarker>

</chart:LineSeries>


{% endhighlight %}

{% highlight c# %}
[C#]

lineSeries.DataMarker = new ChartDataMarker();

{% endhighlight %}

![D:/Chart UG/Xamarin/UG images/Xamarin UG Images/Merged UG Images/Datamaker - clubbed/Datamacker.png](datamarker_images/datamarker_img1.png)

## Customizing Labels

Data labels are enabled by default but you can also change the visibility of the labels using **ShowLabel** property of ChartDataMarker. The label appearance can be customized using following properties,

* **TextColor** – used to change the color of the label.
* **BackgroundColor** – used to change the label background color.
* **BorderColor** – used to change the border color.
* **BorderThickness** – used to change the thickness of the border.
* **Font** – used to change the text size, font family and font weight.
* **Margin** - used to change the margin size for labels.
* **Angle** – used to rotate the labels.

Following code snippet illustrates the customization of label and its background,

{% highlight xml %}
[XAML]

<chart:LineSeries.DataMarker>

	<chart:ChartDataMarker ShowLabel="True">

		<chart:ChartDataMarker.LabelStyle>

			<chart:DataMarkerLabelStyle TextColor="Blue" BorderColor="Red" BorderThickness="2" BackgroundColor="Aqua" Angle="315" Margin="5">

				<chart:DataMarkerLabelStyle.Font>

					<Font FontSize="18" FontAttributes="Italic"/>

				</chart:DataMarkerLabelStyle.Font>

			</chart:DataMarkerLabelStyle>

		</chart:ChartDataMarker.LabelStyle>

	</chart:ChartDataMarker>

</chart:LineSeries.DataMarker>

{% endhighlight %}

{% highlight c# %}
[C#]

lineSeries.DataMarker = new ChartDataMarker();

lineSeries.DataMarker.ShowLabel = true;

lineSeries.DataMarker.LabelStyle.TextColor = Color.Blue;

lineSeries.DataMarker.LabelStyle.BorderColor = Color.Red;

lineSeries.DataMarker.LabelStyle.BorderThickness = 2;

lineSeries.DataMarker.LabelStyle.BackgroundColor = Color.Aqua;

lineSeries.DataMarker.LabelStyle.Angle = 315;

lineSeries.DataMarker.LabelStyle.Margin = 5;

lineSeries.DataMarker.LabelStyle.Font = Font.SystemFontOfSize(18, FontAttributes.Italic);

{% endhighlight %}

![D:/Chart UG/Xamarin/UG images/Xamarin UG Images/Merged UG Images/Datamaker - clubbed/DataMarkerlabelStyle.png](datamarker_images/datamarker_img2.png)

## Formatting Label Content

You can customize the content of the label using LabelContent property. Following are the two options that are supported now,

* **Percentage** – This will show the percentage value of corresponding data point Y value, this is often used in pie, doughnut, funnel and pyramid series types.
* **YValue** – This will show the corresponding Y value.
{% highlight xml %}

[XAML]

<chart:PieSeries>

	<chart:PieSeries.DataMarker>

		<chart:ChartDataMarker LabelContent="Percentage"/>

	</chart:PieSeries.DataMarker>

</chart:PieSeries>

{% endhighlight %}

{% highlight c# %}
[C#]

pieSeries.DataMarker.LabelContent = LabelContent.Percentage;

{% endhighlight %}

![D:/Chart UG/Xamarin/UG images/Xamarin UG Images/Merged UG Images/Datamaker - clubbed/DatamarkerlabalContent.png](datamarker_images/datamarker_img3.png)

## Label Position

This feature is used to position the data marker labels at Center, Inner and Outer position of the actual data point position. By default, labels are positioned based on the series types for better readability. You can move the labels horizontally and vertically using **OffsetX** and **OffsetY** properties respectively.

The following screenshot illustrates the default position of data marker labels,

![D:/Chart UG/Xamarin/UG images/Xamarin UG Images/Merged UG Images/Datamaker - clubbed/Auto.png](datamarker_images/datamarker_img4.png)


The following code sample illustrates the center position of data marker labels,

{% highlight xml %}
[XAML]

<chart:ChartDataMarker>

	<chart:ChartDataMarker.LabelStyle>

		<chart:DataMarkerLabelStyle LabelPosition="Center"/>

	</chart:ChartDataMarker.LabelStyle>

</chart:ChartDataMarker>

{% endhighlight %}

{% highlight c# %}
[C#]

series.DataMarker.LabelStyle.LabelPosition = DataMarkerLabelPosition.Center;

{% endhighlight %}

![D:/Chart UG/Xamarin/UG images/Xamarin UG Images/Merged UG Images/Datamaker - clubbed/Center.png](datamarker_images/datamarker_img5.png)

The following code sample illustrates the Inner position of data marker labels,

{% highlight xml %}
[XAML]

<chart:ChartDataMarker>

	<chart:ChartDataMarker.LabelStyle>

		<chart:DataMarkerLabelStyle LabelPosition="Inner"/>

	</chart:ChartDataMarker.LabelStyle>

</chart:ChartDataMarker>

{% endhighlight %}

{% highlight c# %}
[C#]

series.DataMarker.LabelStyle.LabelPosition = DataMarkerLabelPosition.Inner;

{% endhighlight %}

![D:/Chart UG/Xamarin/UG images/Xamarin UG Images/Merged UG Images/Datamaker - clubbed/inner.png](datamarker_images/datamarker_img6.png)


The following code sample illustrates the outer position of data marker labels, 

{% highlight xml %}
[XAML]

<chart:ChartDataMarker>

	<chart:ChartDataMarker.LabelStyle>

		<chart:DataMarkerLabelStyle LabelPosition="Outer"/>

	</chart:ChartDataMarker.LabelStyle>

</chart:ChartDataMarker>

{% endhighlight %}

{% highlight c# %}
[C#]

series.DataMarker.LabelStyle.LabelPosition = DataMarkerLabelPosition.Outer;

{% endhighlight %}

![D:/Chart UG/Xamarin/UG images/Xamarin UG Images/Merged UG Images/Datamaker - clubbed/outer.png](datamarker_images/datamarker_img7.png)


## Customizing Marker Shapes

Shapes can be added to chart data marker by setting the ShowMarker property to true. There are different shapes you can set to the chart using MarkerType property such as rectangle, circle, diamond etc. Following properties are used to customize marker appearance,

* **MarkerWidth** - used to change the width of the marker
* **MarkerHeight** - used to change the height of the marker
* **MarkerColor** - used to change the color of the marker
* **MarkerBorderColor** - used to change the border color of the shape
* **MarkerBorderWidth** – used to change the marker border thickness

The following code example shows how to enable marker and specify its types,

{% highlight xml %}
[XAML]

<chart:LineSeries.DataMarker>

	<chart:ChartDataMarker ShowLabel="False" ShowMarker="True" MarkerType="Hexagon" MarkerWidth="20" MarkerHeight="20" MarkerColor="Aqua" MarkerBorderColor="Red" MarkerBorderWidth="2"/>

</chart:LineSeries.DataMarker>

{% endhighlight %}

{% highlight c# %}
[C#]          

lineSeries.DataMarker = new ChartDataMarker();

lineSeries.DataMarker.ShowLabel = false;

lineSeries.DataMarker.ShowMarker = true;

lineSeries.DataMarker.MarkerType = DataMarkerType.Hexagon;

lineSeries.DataMarker.MarkerWidth = 20;

lineSeries.DataMarker.MarkerHeight = 20;

lineSeries.DataMarker.MarkerColor = Color.Aqua;

lineSeries.DataMarker.MarkerBorderColor = Color.Red;

lineSeries.DataMarker.MarkerBorderWidth = 2;

{% endhighlight %}

![D:/Chart UG/Xamarin/UG images/Xamarin UG Images/Merged UG Images/Datamaker - clubbed/MarkerType.png](datamarker_images/datamarker_img8.png)


## Connector Line

This feature is used to connect label and data point using a line. It can be enabled for any chart types but this is often used with Pie and Doughnut chart types. Following properties used to customize connector line,

* **StrokeColor** – used to change the color of the line
* **StrokeWidth** – used to change the stroke thickness of the line
* **StrokeDashArray** – used to set the dashes for the line

The following code illustrates how to specify the connector height and its angle,

{% highlight xml %}
[XAML]      

<chart:LineSeries.DataMarker>

	<chart:ChartDataMarker>

		<chart:ChartDataMarker.ConnectorLineStyle>

			<chart:ConnectorLineStyle ConnectorHeight="40" ConnectorRotationAngle="175" StrokeColor="Blue" StrokeWidth="3"/>

		</chart:ChartDataMarker.ConnectorLineStyle>

	</chart:ChartDataMarker>

</chart:LineSeries.DataMarker>

{% endhighlight %}

{% highlight c# %}
[C#]

lineSeries.DataMarker.ConnectorLineStyle.ConnectorHeight = 50;

lineSeries.DataMarker.ConnectorLineStyle.ConnectorRotationAngle = 175;

lineSeries.DataMarker.ConnectorLineStyle.StrokeColor = Color.Blue;

lineSeries.DataMarker.ConnectorLineStyle.StrokeWidth = 3;

lineSeries.DataMarker.ConnectorLineStyle.StrokeDashArray = new double[2] { 2, 3 };

{% endhighlight %}

![D:/Chart UG/Xamarin/UG images/Xamarin UG Images/Merged UG Images/Datamaker - clubbed/ConnectorLine.png](datamarker_images/datamarker_img9.png)

N> For Pie and Doughnut series, you can set the Bezier curve for connector line using ConnectorType property of Pie and Doughnut series.