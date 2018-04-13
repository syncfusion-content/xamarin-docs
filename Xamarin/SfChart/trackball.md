---
layout: post
title: Chart Trackball
description: How to enable and customize the trackball behavior in Essential Xamarin.Forms Chart
platform: xamarin
control: Chart
documentation: ug
---

# Trackball

Trackball feature displays the tooltip for the data points that are closer to the point where you touch on the chart area. This feature, especially, can be used instead of data label feature when you cannot show data labels for all data points due to space constraint. To enable this feature, add an instance of [`ChartTrackballBehavior`](http://help.syncfusion.com/cr/cref_files/xamarin/sfchart/Syncfusion.SfChart.XForms~Syncfusion.SfChart.XForms.ChartTrackballBehavior.html#) to the [`ChartBehaviors`](http://help.syncfusion.com/cr/cref_files/xamarin/sfchart/Syncfusion.SfChart.XForms~Syncfusion.SfChart.XForms.ChartBehavior.html#) collection property of [`SfChart`](http://help.syncfusion.com/cr/cref_files/xamarin/sfchart/Syncfusion.SfChart.XForms~Syncfusion.SfChart.XForms.SfChart.html#). Trackball will be activated once you long-press anywhere on the chart area. Once it is activated, it will appear in the UI and move based on your touch movement until you stop touching on the chart.

You can use the following properties to show/hide the line and labels.

* [`ShowLabel`](http://help.syncfusion.com/cr/cref_files/xamarin/sfchart/Syncfusion.SfChart.XForms~Syncfusion.SfChart.XForms.ChartTrackballBehavior~ShowLabel.html#) – Shows/hides trackball label. Default value is true.

* [`ShowLine`](http://help.syncfusion.com/cr/cref_files/xamarin/sfchart/Syncfusion.SfChart.XForms~Syncfusion.SfChart.XForms.ChartTrackballBehavior~ShowLine.html#) – Shows/hides the trackball line. Default value is true.

{% tabs %} 

{% highlight xaml %}

<chart:SfChart>
...

	<chart:SfChart.ChartBehaviors>

		<chart:ChartTrackballBehavior ShowLabel="True" ShowLine="True"/>

	</chart:SfChart.ChartBehaviors>

</chart:SfChart>

{% endhighlight %}

{% highlight c# %}

SfChart chart = new SfChart();
...

ChartTrackballBehavior trackballBehavior = new ChartTrackballBehavior();

trackballBehavior.ShowLabel = true;

trackballBehavior.ShowLine = true;

chart.ChartBehaviors.Add(trackballBehavior);

{% endhighlight %}

{% endtabs %}

![](trackball_images/trackball_img1.png)

## Label Display Mode

[`TrackballLabelDisplayMode`](https://help.syncfusion.com/cr/cref_files/xamarin/sfchart/Syncfusion.SfChart.XForms~Syncfusion.SfChart.XForms.ChartTrackballBehavior~LabelDisplayMode.html) property is used to specify whether to display label for all the data points along the vertical line or display only single label. Following are the two options you can set to this property,

* [`FloatAllPoints`](http://help.syncfusion.com/cr/cref_files/xamarin/sfchart/Syncfusion.SfChart.XForms~Syncfusion.SfChart.XForms.TrackballLabelDisplayMode.html#) – Displays label for all the data points along the vertical line.
* [`NearestPoint`](http://help.syncfusion.com/cr/cref_files/xamarin/sfchart/Syncfusion.SfChart.XForms~Syncfusion.SfChart.XForms.TrackballLabelDisplayMode.html#) – Displays label for single data point that is nearer to the touch contact position.

{% tabs %} 

{% highlight xaml %}

<chart:ChartTrackballBehavior LabelDisplayMode="NearestPoint" ShowLine="False"/>

{% endhighlight %}

{% highlight c# %}

ChartTrackballBehavior trackballBehavior = new ChartTrackballBehavior();

trackballBehavior.ShowLine = false;

trackballBehavior.LabelDisplayMode = TrackballLabelDisplayMode.NearestPoint;

{% endhighlight %}

{% endtabs %}

In the following screenshot, trackball label is shown for only single data point,

![](trackball_images/trackball_img2.png)

## Customizing appearance

**Customize Trackball Labels**

The [`LabelStyle`](https://help.syncfusion.com/cr/cref_files/xamarin/sfchart/Syncfusion.SfChart.XForms~Syncfusion.SfChart.XForms.ChartTrackballBehavior~LabelStyle.html) property provides options to  customize the trackball labels.

* [`BorderColor`](http://help.syncfusion.com/cr/cref_files/xamarin/sfchart/Syncfusion.SfChart.XForms~Syncfusion.SfChart.XForms.ChartLabelStyle~BorderColor.html#) – used to change the label border color.
* [`BackgroundColor`](http://help.syncfusion.com/cr/cref_files/xamarin/sfchart/Syncfusion.SfChart.XForms~Syncfusion.SfChart.XForms.ChartLabelStyle~BackgroundColor.html#) – used to change the label background color.
* [`BorderThickness`](http://help.syncfusion.com/cr/cref_files/xamarin/sfchart/Syncfusion.SfChart.XForms~Syncfusion.SfChart.XForms.ChartLabelStyle~BorderThickness.html#) – used to change label border thickness.
* [`TextColor`](http://help.syncfusion.com/cr/cref_files/xamarin/sfchart/Syncfusion.SfChart.XForms~Syncfusion.SfChart.XForms.ChartLabelStyle~TextColor.html#) – used to change the text color.
* [`Font`](http://help.syncfusion.com/cr/cref_files/xamarin/sfchart/Syncfusion.SfChart.XForms~Syncfusion.SfChart.XForms.ChartLabelStyle~Font.html#) – used to change label font size, family and weight.

{% tabs %} 

{% highlight xaml %}

<chart:SfChart>
...

	<chart:SfChart.ChartBehaviors>

		<chart:ChartTrackballBehavior>

			<chart:ChartTrackballBehavior.LabelStyle>

				<chart:ChartTrackballLabelStyle BorderColor="Maroon" BackgroundColor="Aqua" BorderThickness="2" TextColor="Red" Font="Italic,18"/>

			</chart:ChartTrackballBehavior.LabelStyle>

		</chart:ChartTrackballBehavior>

	</chart:SfChart.ChartBehaviors>

</chart:SfChart>

{% endhighlight %}

{% highlight c# %}

SfChart chart = new SfChart();
...

ChartTrackballBehavior trackBallBehavior = new ChartTrackballBehavior();

trackBallBehavior.LabelStyle.BorderColor = Color.Maroon;

trackBallBehavior.LabelStyle.BorderThickness = 2;

trackBallBehavior.LabelStyle.Font = Font.SystemFontOfSize(18, FontAttributes.Italic);

trackBallBehavior.LabelStyle.BackgroundColor = Color.Aqua;

trackBallBehavior.LabelStyle.TextColor = Color.Red;

chart.ChartBehaviors.Add(trackballBehavior);

{% endhighlight %}

{% endtabs %}

**Customize Trackball Marker**

The [`MarkerStyle`](https://help.syncfusion.com/cr/cref_files/xamarin/sfchart/Syncfusion.SfChart.XForms~Syncfusion.SfChart.XForms.ChartTrackballBehavior~MarkerStyle.html) property provides options to  customize the trackball markers.

Following properties are used to customize the trackball marker.

* [`ShowMarker`](http://help.syncfusion.com/cr/cref_files/xamarin/sfchart/Syncfusion.SfChart.XForms~Syncfusion.SfChart.XForms.ChartTrackballMarkerStyle~ShowMarker.html#) – used to enable / disable the marker. Default value is true.
* [`BorderColor`](http://help.syncfusion.com/cr/cref_files/xamarin/sfchart/Syncfusion.SfChart.XForms~Syncfusion.SfChart.XForms.ChartTrackballMarkerStyle~BorderColor.html#) – used to change the marker border color.
* [`Color`](http://help.syncfusion.com/cr/cref_files/xamarin/sfchart/Syncfusion.SfChart.XForms~Syncfusion.SfChart.XForms.ChartTrackballMarkerStyle~Color.html#) – used to change the marker background color.
* [`BorderWidth`](http://help.syncfusion.com/cr/cref_files/xamarin/sfchart/Syncfusion.SfChart.XForms~Syncfusion.SfChart.XForms.ChartTrackballMarkerStyle~BorderWidth.html#) – used to change the width of the marker border.
* [`Width`](http://help.syncfusion.com/cr/cref_files/xamarin/sfchart/Syncfusion.SfChart.XForms~Syncfusion.SfChart.XForms.ChartTrackballMarkerStyle~Width.html#) – used to change the width of the marker.
* [`Height`](http://help.syncfusion.com/cr/cref_files/xamarin/sfchart/Syncfusion.SfChart.XForms~Syncfusion.SfChart.XForms.ChartTrackballMarkerStyle~Height.html#) – used to change the height of the marker.

{% tabs %} 

{% highlight xaml %}

<chart:SfChart HorizontalOptions="FillAndExpand" VerticalOptions="FillAndExpand">
...

	<chart:SfChart.ChartBehaviors>

		<chart:ChartTrackballBehavior>

			<chart:ChartTrackballBehavior.MarkerStyle>

				<chart:ChartTrackballMarkerStyle BorderColor="Purple" ShowMarker="True" BorderWidth="1" Width="8" Height="8" Color="Green"/>

			</chart:ChartTrackballBehavior.MarkerStyle>

		</chart:ChartTrackballBehavior>

	</chart:SfChart.ChartBehaviors>

</chart:SfChart>

{% endhighlight %}

{% highlight c# %}

SfChart chart = new SfChart();
...

ChartTrackballBehavior trackBallBehavior = new ChartTrackballBehavior();

trackBallBehavior.MarkerStyle.BorderWidth = 1;

trackBallBehavior.MarkerStyle.BorderColor = Color.Purple;

trackBallBehavior.MarkerStyle.Width = 8;

trackBallBehavior.MarkerStyle.Height = 8;

trackBallBehavior.MarkerStyle.Color = Color.Green;

trackBallBehavior.MarkerStyle.ShowMarker = true;

chart.ChartBehaviors.Add(trackballBehavior);

{% endhighlight %}

{% endtabs %}

**Customize Trackball Line**

The [`LineStyle`](https://help.syncfusion.com/cr/cref_files/xamarin/sfchart/Syncfusion.SfChart.XForms~Syncfusion.SfChart.XForms.ChartTrackballBehavior~LineStyle.html) property provides options to  customize the trackball line.

* [`ShowLine`](http://help.syncfusion.com/cr/cref_files/xamarin/sfchart/Syncfusion.SfChart.XForms~Syncfusion.SfChart.XForms.ChartTrackballBehavior~ShowLine.html#) – used to enable / disable the line. Default value is true.
* [`StrokeWidth`](http://help.syncfusion.com/cr/cref_files/xamarin/sfchart/Syncfusion.SfChart.XForms~Syncfusion.SfChart.XForms.ChartLineStyle~StrokeWidth.html#) – used to change the stroke width of the line.
* [`StrokeColor`](http://help.syncfusion.com/cr/cref_files/xamarin/sfchart/Syncfusion.SfChart.XForms~Syncfusion.SfChart.XForms.ChartLineStyle~StrokeColor.html#) – used to change the stroke color of the line.
* [`StrokeDashArray`](http://help.syncfusion.com/cr/cref_files/xamarin/sfchart/Syncfusion.SfChart.XForms~Syncfusion.SfChart.XForms.ChartLineStyle~StrokeDashArray.html#) – Specifies the dashes to be applied on the line.

{% tabs %} 

{% highlight xaml %}

<chart:SfChart HorizontalOptions="FillAndExpand" VerticalOptions="FillAndExpand">
...

	<chart:SfChart.ChartBehaviors>

		<chart:ChartTrackballBehavior>

			<chart:ChartTrackballBehavior.LineStyle>

				<chart:ChartLineStyle StrokeColor="Blue" StrokeWidth="2"/>

			</chart:ChartTrackballBehavior.LineStyle>

		</chart:ChartTrackballBehavior>

	</chart:SfChart.ChartBehaviors>

</chart:SfChart>

{% endhighlight %}

{% highlight c# %}

SfChart chart = new SfChart();
...

ChartTrackballBehavior trackBallBehavior = new ChartTrackballBehavior();

trackBallBehavior.ShowLine = true;

trackBallBehavior.LineStyle.StrokeWidth = 2;

trackBallBehavior.LineStyle.StrokeColor = Color.Blue;

trackBallBehavior.LineStyle.StrokeDashArray = new double[2] { 2, 3 };

chart.ChartBehaviors.Add(trackballBehavior);

{% endhighlight %}

{% endtabs %}

Following screenshot illustrates the customization of trackball elements.

![](trackball_images/trackball_img3.png)

## Show/hide the trackball label in axis

This feature is used to highlight the respective axis label when the trackball is moving across the axis. [`ChartAxis.ShowTrackballInfo`](http://help.syncfusion.com/cr/cref_files/xamarin/sfchart/Syncfusion.SfChart.XForms~Syncfusion.SfChart.XForms.ChartAxis~ShowTrackballInfo.html) property is used show/hide the trackball label of the axis. [`ChartAxis.TrackballLabelStyle`](https://help.syncfusion.com/cr/cref_files/xamarin/sfchart/Syncfusion.SfChart.XForms~Syncfusion.SfChart.XForms.ChartAxis~TrackballLabelStyle.html) property is used to customize its appearance. Default value of [`ChartAxis.ShowTrackballInfo`](http://help.syncfusion.com/cr/cref_files/xamarin/sfchart/Syncfusion.SfChart.XForms~Syncfusion.SfChart.XForms.ChartAxis~ShowTrackballInfo.html) is `False`.

{% tabs %} 

{% highlight xaml %}

<chart:SfChart.PrimaryAxis >

    <chart:CategoryAxis ShowTrackballInfo = "true" />

</chart:SfChart.PrimaryAxis >

{% endhighlight %}

{% highlight c# %}

chart.PrimaryAxis.ShowTrackballInfo = true;

{% endhighlight %}

{% endtabs %}

![](trackball_images/trackball_img5.png)

## Axis label alignment

The position of trackball's axis label can be changed using the [`AxisLabelAlignment`](https://help.syncfusion.com/cr/cref_files/xamarin/sfchart/Syncfusion.SfChart.XForms~Syncfusion.SfChart.XForms.ChartTrackballAxisLabelStyle~AxisLabelAlignment.html) property of [`ChartTrackballAxisLabelStyle`](https://help.syncfusion.com/cr/cref_files/xamarin/sfchart/Syncfusion.SfChart.XForms~Syncfusion.SfChart.XForms.ChartTrackballAxisLabelStyle.html). The following options are available in [`AxisLabelAlignment`]().

*	[`Far`](https://help.syncfusion.com/cr/cref_files/xamarin/sfchart/Syncfusion.SfChart.XForms~Syncfusion.SfChart.XForms.ChartAxisLabelAlignment.html) -  The label will be positioned below the tick in vertical axis and right of the tick in horizontal axis.
*	[`Near`](https://help.syncfusion.com/cr/cref_files/xamarin/sfchart/Syncfusion.SfChart.XForms~Syncfusion.SfChart.XForms.ChartAxisLabelAlignment.html) -  The label will be positioned above the tick in vertical axis and left of the tick in horizontal axis.
*   [`Center`](https://help.syncfusion.com/cr/cref_files/xamarin/sfchart/Syncfusion.SfChart.XForms~Syncfusion.SfChart.XForms.ChartAxisLabelAlignment.html) - The label will be positioned at the center of tick. This is the default value.

The following code snippet and screenshot demonstrate the placement of label at the left to tick line.

{% tabs %} 

{% highlight xaml %}

<chart:SfChart>
 ...
<chart:CategoryAxis.TrackballLabelStyle>

    <chart:ChartTrackballAxisLabelStyle AxisLabelAlignment="Near"/>

</chart:CategoryAxis.TrackballLabelStyle>
 ...
</chart:SfChart>

{% endhighlight %}

{% highlight c# %}

primaryAxis.TrackballLabelStyle.AxisLabelAlignment = ChartLabelAlignment.Near;

{% endhighlight %}

{% endtabs %}

![](trackball_images/AxisLabelAlignment-Near.png)

## Show/hide the series label

This feature is used to show/hide the trackball label of the series by using [`CartesianSeries.ShowTrackballInfo`](https://help.syncfusion.com/cr/cref_files/xamarin/sfchart/Syncfusion.SfChart.XForms~Syncfusion.SfChart.XForms.CartesianSeries~ShowTrackballInfo.html) property. Default value of [`CartesianSeries.ShowTrackballInfo`](https://help.syncfusion.com/cr/cref_files/xamarin/sfchart/Syncfusion.SfChart.XForms~Syncfusion.SfChart.XForms.CartesianSeries~ShowTrackballInfo.html) property is `True`.

{% tabs %} 

{% highlight xaml %}

<chart:SfChart>
...

    <chart:LineSeries ItemsSource ="{Binding Data}" XBindingPath="Year"
    YBindingPath="Value" ShowTrackballInfo = "false" />

</chart:SfChart>

{% endhighlight %}

{% highlight c# %}

SfChart chart = new SfChart();
...

LineSeries lineSeries = new LineSeries()
{
    ItemsSource = Data,
    XBindingPath = "Year",
    YBindingPath = "Value",
    ShowTrackballInfo = false

};
chart.Series.Add(lineSeries);

{% endhighlight %}

{% endtabs %}

![](trackball_images/trackball_img6.png)

## Label Template

You can customize the appearance of the Trackball label with your own template by using [`TrackballLabelTemplate`](https://help.syncfusion.com/cr/cref_files/xamarin/sfchart/Syncfusion.SfChart.XForms~Syncfusion.SfChart.XForms.CartesianSeries~TrackballLabelTemplate.html) property of [`ChartSeries`](http://help.syncfusion.com/cr/cref_files/xamarin/sfchart/Syncfusion.SfChart.XForms~Syncfusion.SfChart.XForms.ChartSeries.html).

{% tabs %} 

{% highlight xaml %}

<ContentPage.Resources>
    <ResourceDictionary>
       <DataTemplate x:Key="trackballTemplate">
          <StackLayout  Orientation="Horizontal">
             <Label  Text="{Binding Value}" TextColor="White" FontSize ="15" VerticalTextAlignment="Center"/>
             <Image Source ="grain.jpg" WidthRequest="30" HeightRequest="30"/>
          </StackLayout>
       </DataTemplate>
    </ResourceDictionary>
</ContentPage.Resources>

<chart:SfChart.Series>
    <chart:LineSeries TrackballLabelTemplate="{StaticResource trackballTemplate}" ItemsSource="{Binding Data1}" XBindingPath="Name" YBindingPath="Value"/>
    <chart:LineSeries TrackballLabelTemplate="{StaticResource trackballTemplate}" ItemsSource="{Binding Data2}" XBindingPath="Name" YBindingPath="Value"/>
</chart:SfChart.Series>

<chart:SfChart.ChartBehaviors>
    <chart:ChartTrackballBehavior/>
</chart:SfChart.ChartBehaviors>


{% endhighlight %}

{% highlight c# %}

SfChart chart = new SfChart ();
...

var lineSeries1 = new LineSeries();
lineSeries1.ItemsSource = Data1;
lineSeries1.XBindingPath = "Name";
lineSeries1.YBindingPath = "Value";

var lineSeries2 = new LineSeries();
lineSeries2.ItemsSource = Data2;
lineSeries2.XBindingPath = "Name";
lineSeries2.YBindingPath = "Value";

DataTemplate trackBallTemplate = new DataTemplate(() =>
{
     StackLayout stack = new StackLayout();
     stack.Orientation = StackOrientation.Horizontal;
     Label label = new Label();
     label.SetBinding(Label.TextProperty, "Value");
     label.FontSize = 15;
     label.VerticalTextAlignment = TextAlignment.Center;
     label.TextColor = Color.White;
     Image image = new Image();
     image.Source = "grain.jpg";
     image.WidthRequest = 30;
     image.HeightRequest = 30;
     stack.Children.Add(label);
     stack.Children.Add(image);
     return stack;
});

lineSeries1.TrackballLabelTemplate = trackBallTemplate;
lineSeries2.TrackballLabelTemplate = trackBallTemplate;

chart.Series.Add(lineSeries1);
chart.Series.Add(lineSeries2);

chart.ChartBehaviors.Add(new ChartTrackballBehavior());

{% endhighlight %}

{% endtabs %}

![](trackball_images/trackball_img4.png)

**customization of Axis Label**

You can change the default appearance of the axis label in trackball using [`TrackballLabelTemplate`](https://help.syncfusion.com/cr/cref_files/xamarin/sfchart/Syncfusion.SfChart.XForms~Syncfusion.SfChart.XForms.ChartAxis~TrackballLabelTemplate.html) property in [`ChartAxis`](https://help.syncfusion.com/cr/cref_files/xamarin/sfchart/Syncfusion.SfChart.XForms~Syncfusion.SfChart.XForms.ChartAxis.html).

{% tabs %} 

{% highlight xaml %}
<ContentPage.Resources>
    <ResourceDictionary>
      <DataTemplate x:Key="axisLabelTemplate">
        <Label WidthRequest="50" HeightRequest="20" HorizontalTextAlignment="Center" BackgroundColor="Blue" Text="{Binding }" TextColor="White" FontSize ="15" />
      </DataTemplate>
    </ResourceDictionary>
</ContentPage.Resources>

 <chart:SfChart.PrimaryAxis>
       <chart:CategoryAxis  ShowTrackballInfo="True" TrackballLabelTemplate="{StaticResource axisLabelTemplate}">
        <chart:CategoryAxis.TrackballLabelStyle>
          <chart:ChartTrackballAxisLabelStyle   BackgroundColor="Transparent"/>
        </chart:CategoryAxis.TrackballLabelStyle>  
      </chart:CategoryAxis>  
</chart:SfChart.PrimaryAxis>

<chart:SfChart.ChartBehaviors>
     <chart:ChartTrackballBehavior />
</chart:SfChart.ChartBehaviors>

{% endhighlight %}

{% highlight c# %}

Chart.PrimaryAxis = new CategoryAxis(); 
Chart.PrimaryAxis.ShowTrackballInfo = true;
Chart.PrimaryAxis.TrackballLabelStyle.BackgroundColor = Color.Transparent;
DataTemplate axisLabelTemplate = new DataTemplate(() =>
{              
     Label label = new Label();
     label.SetBinding(Label.TextProperty, ".");
     label.FontSize = 15;
     label.HorizontalTextAlignment = TextAlignment.Center;
     label.TextColor = Color.White;
     label.BackgroundColor = Color.Blue;                       
     label.WidthRequest = 50;
     label.HeightRequest = 20;           
     return label;
});
Chart.PrimaryAxis.TrackballLabelTemplate = axisLabelTemplate;
Chart.ChartBehaviors.Add(new ChartTrackballBehavior());

{% endhighlight %}

{% endtabs %}

![](trackball_images/axislabelTemplate.png)