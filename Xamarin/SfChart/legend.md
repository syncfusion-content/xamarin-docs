---
layout: post
title: Chart legend
description: How to cutomize the legend in Essential Xamarin.Forms Chart
platform: xamarin
control: Chart
documentation: ug
---

# Legend

Legend contains list of chart series/data points in the chart. The information provided in each legend item helps in identifying the corresponding data series in chart.

Following code example shows how to enable legend in a chart,

{% tabs %} 

{% highlight xaml %}

<chart:SfChart>

	<chart:SfChart.Legend>

		<chart:ChartLegend/>

	</chart:SfChart.Legend>

</chart:SfChart>

{% endhighlight %}

{% highlight c# %}

chart.Legend = new ChartLegend();

{% endhighlight %}

{% endtabs %}

![](legend_images/legend_img1.png)

## Customizing Labels

`Label` property of `ChartSeries` is used to define the label for the corresponding series legend item. The following properties are used to customize the legend items label appearance.

* `TextColor` – used to change the color of the label.
* `Font` – used to change the text size, font family and font weight.
* `Margin` - used to change the margin size for labels.

{% tabs %} 

{% highlight xaml %}

<chart:SfChart.Legend>

	<chart:ChartLegend>

		<chart:ChartLegend.LabelStyle>

			<chart:ChartLegendLabelStyle TextColor="Blue" Margin="5">

				<chart:ChartLegendLabelStyle.Font>

					<Font FontSize="18" FontAttributes ="Bold"/>

				</chart:ChartLegendLabelStyle.Font>

			</chart:ChartLegendLabelStyle>

		</chart:ChartLegend.LabelStyle>

	</chart:ChartLegend>

</chart:SfChart.Legend>

{% endhighlight %}

{% highlight c# %}

chart.Legend = new ChartLegend();

chart.Legend.LabelStyle.TextColor = Color.Blue;

chart.Legend.LabelStyle.Font = Font.SystemFontOfSize(18, FontAttributes.Bold);

chart.Legend.LabelStyle.Margin = 5;

{% endhighlight %}

{% endtabs %}

![](legend_images/legend_img2.png)

## Legend Icons

Legend icons are enabled by default, however, you can control its visibility using `IsIconVisible` property. Also you can specify the icon type using `LegendIcon` property in ChartSeries. `IconWidth` and `IconHeight` properties are used to adjust the width and height of the legend icons respectively.

{% tabs %} 

{% highlight xaml %}

<chart:SfChart>

	<chart:SfChart.Legend>

		<chart:ChartLegend IsIconVisible="True" IconHeight="20" IconWidth="20"/>

	</chart:SfChart.Legend>

	<chart:PieSeries ItemsSource ="{Binding Data1}" LegendIcon="SeriesType"/>

</chart:SfChart>

{% endhighlight %}

{% highlight c# %}

chart.Legend = new ChartLegend();

chart.Legend.IconHeight = 20;

chart.Legend.IconWidth = 20;

chart.Legend.IsIconVisible = true;

pieSeries.LegendIcon = ChartLegendIcon.SeriesType;

{% endhighlight %}

{% endtabs %}

![](legend_images/legend_img3.png)

## Legend Title

Following properties are used to define and customize the legend title.

* `Text` – used to change the title text.
* `TextColor` – used to change the color of the title text.
* `Font` – used to change the text size, font family and font weight of the title.
* `Margin` – used to change the margin size for title.
* `TextAlignment` – used to change the alignment of the title text, it can be start, end and center.
* `BackgroundColor` – used to change the title background color.
* `BorderColor` – used to change the border color.
* `BorderWidth` – used to adjust the title border width.

{% tabs %} 

{% highlight xaml %}

<chart:SfChart.Legend>

	<chart:ChartLegend>

		<chart:ChartLegend.Title >

			<chart:ChartTitle Text="Years" TextColor="Maroon" TextAlignment="Center" BackgroundColor="Silver" BorderWidth="3" BorderColor="Blue">

				<chart:ChartTitle.Font>

					<Font FontSize="20" FontAttributes ="Bold"/>

				</chart:ChartTitle.Font>

			</chart:ChartTitle>

		</chart:ChartLegend.Title>

	</chart:ChartLegend>

</chart:SfChart.Legend>

{% endhighlight %}

{% highlight c# %}

chart.Legend = new ChartLegend();

chart.Legend.Title.Text = "Year";

chart.Legend.Title.TextColor = Color.Maroon;

chart.Legend.Title.Font = Font.SystemFontOfSize(20, FontAttributes.Bold);

chart.Legend.Title.TextAlignment = TextAlignment.Center;

chart.Legend.Title.BackgroundColor = Color.Silver;

chart.Legend.Title.BorderWidth = 3;

chart.Legend.Title.BorderColor = Color.Blue;

{% endhighlight %}

{% endtabs %}

![](legend_images/legend_img4.png)

## Toggle the series visibility

You can control the visibility of the series by tapping on the legend item. You can enable this feature by enabling `ToggleSeriesVisibility` property.

{% tabs %} 

{% highlight xaml %}

<chart:SfChart>

	<chart:SfChart.Legend>

		<chart:ChartLegend ToggleSeriesVisibility="True"/>

	</chart:SfChart.Legend>

</chart:SfChart>

{% endhighlight %}

{% highlight c# %}

chart.Legend = new ChartLegend();

chart.Legend.ToggleSeriesVisibility = true;

{% endhighlight %}

{% endtabs %}

## Positioning the Legend

You can position the legend anywhere inside the chart. Following properties are used to customize the legend positions.

* `DockPosition`– used to position the legend relatively. Options available are: Left, Right, Top, Bottom and Floating. If the DockPosition is Floating, you can position the legend using x and y coordinates.
* `OffsetX`– used to move the legend on x coordinate by the given offset value, this will work only if the dock position is Floating.
* `OffsetY` - used to move the legend on y coordinate by the given offset value, this will work only if the dock position is Floating.

{% tabs %} 

{% highlight xaml %}

<chart:SfChart>

	<chart:SfChart.Legend>

		<chart:ChartLegend DockPosition="Floating" OffsetX="70" OffsetY="90" Orientation="Vertical">        

	</chart:SfChart.Legend>           

</chart:SfChart>

{% endhighlight %}

{% highlight c# %}

chart.Legend = new ChartLegend();

chart.Legend.DockPosition = LegendPlacement.Floating;

chart.Legend.Orientation = ChartOrientation.Vertical;

chart.Legend.OffsetX = 70;

chart.Legend.OffsetY = 90;

{% endhighlight %}

{% endtabs %}

![](legend_images/legend_img5.png)