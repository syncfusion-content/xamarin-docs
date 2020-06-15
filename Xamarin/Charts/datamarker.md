---
layout: post
title: Markers and data labels in Essential Syncfusion.Xamarin.Forms Chart
description: Learn how to add markers and data point labels, connector lines, event, formatting label content, configure the data marker label template to the Chart series.
platform: xamarin
control: Chart
documentation: ug
---

# Data Markers in Xamarin Charts (SfChart) 

The data markers are used to provide information about the data points to the user. You can add a shape and label to adorn each data point. This can be enabled using the following code snippet,

{% tabs %} 

{% highlight xaml %}

<chart:LineSeries>

	<chart:LineSeries.DataMarker>

		<chart:ChartDataMarker/>

	</chart:LineSeries.DataMarker>

</chart:LineSeries>

{% endhighlight %}

{% highlight c# %}

lineSeries.DataMarker = new ChartDataMarker();

{% endhighlight %}

{% endtabs %}

![Data markers support in Xamarin.Forms Chart](datamarker_images/datamarker_img1.png)

## Customizing labels

Data labels are enabled by default but you can also change the visibility of the labels using [`ShowLabel`](https://help.syncfusion.com/cr/cref_files/xamarin/Syncfusion.SfChart.XForms~Syncfusion.SfChart.XForms.ChartDataMarker~ShowLabel.html) property of [`ChartDataMarker`](https://help.syncfusion.com/cr/cref_files/xamarin/Syncfusion.SfChart.XForms~Syncfusion.SfChart.XForms.ChartDataMarker.html). The label appearance can be customized using [`LabelStyle`](https://help.syncfusion.com/cr/cref_files/xamarin/Syncfusion.SfChart.XForms~Syncfusion.SfChart.XForms.ChartDataMarker~LabelStyle.html) property. 

* [`TextColor`](https://help.syncfusion.com/cr/cref_files/xamarin/Syncfusion.SfChart.XForms~Syncfusion.SfChart.XForms.ChartLabelStyle~TextColor.html) – used to change the color of the label.
* [`BackgroundColor`](https://help.syncfusion.com/cr/cref_files/xamarin/Syncfusion.SfChart.XForms~Syncfusion.SfChart.XForms.ChartLabelStyle~BackgroundColor.html) – used to change the label background color.
* [`BorderColor`](https://help.syncfusion.com/cr/cref_files/xamarin/Syncfusion.SfChart.XForms~Syncfusion.SfChart.XForms.ChartLabelStyle~BorderColor.html) – used to change the border color.
* [`BorderThickness`](https://help.syncfusion.com/cr/cref_files/xamarin/Syncfusion.SfChart.XForms~Syncfusion.SfChart.XForms.ChartLabelStyle~BorderThickness.html) – used to change the thickness of the border.
* [`Font`](https://help.syncfusion.com/cr/cref_files/xamarin/Syncfusion.SfChart.XForms~Syncfusion.SfChart.XForms.ChartLabelStyle~Font.html) – used to change the text size, font family and font weight.
* [`Margin`](https://help.syncfusion.com/cr/cref_files/xamarin/Syncfusion.SfChart.XForms~Syncfusion.SfChart.XForms.ChartLabelStyle~Margin.html) - used to change the margin size for labels.
* [`Angle`](https://help.syncfusion.com/cr/cref_files/xamarin/Syncfusion.SfChart.XForms~Syncfusion.SfChart.XForms.DataMarkerLabelStyle~Angle.html) – used to rotate the labels.
* [`LabelPadding`](https://help.syncfusion.com/cr/cref_files/xamarin/Syncfusion.SfChart.XForms~Syncfusion.SfChart.XForms.DataMarkerLabelStyle~LabelPadding.html) - used to move the data label in the respective direction. For example, the positive labels in column series will be moved upwards and negative labels in column series will be moved downwards.

Following code snippet illustrates the customization of label and its background,

{% tabs %} 

{% highlight xaml %}

<chart:LineSeries.DataMarker>

	<chart:ChartDataMarker ShowLabel="True">

		<chart:ChartDataMarker.LabelStyle>

			<chart:DataMarkerLabelStyle TextColor="Blue"
										BorderColor="Red" 
										BorderThickness="2"
										BackgroundColor="Aqua"
										Angle="315"
										Margin="5"
										Font="Italic,18"/>

		</chart:ChartDataMarker.LabelStyle>

	</chart:ChartDataMarker>

</chart:LineSeries.DataMarker>

{% endhighlight %}

{% highlight c# %}

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

{% endtabs %}

![Customizing the labels of data markers in Xamarin.Forms Chart](datamarker_images/datamarker_img2.png)

## Formatting label content

You can customize the content of the label using [`LabelContent`](https://help.syncfusion.com/cr/cref_files/xamarin/Syncfusion.SfChart.XForms~Syncfusion.SfChart.XForms.ChartDataMarker~LabelContent.html) property. Following are the two options that are supported now,

* [`Percentage`](https://help.syncfusion.com/cr/cref_files/xamarin/Syncfusion.SfChart.XForms~Syncfusion.SfChart.XForms.LabelContent.html) – This will show the percentage value of corresponding data point Y value, this is often used in pie, doughnut, funnel and pyramid series types.
* [`YValue`](https://help.syncfusion.com/cr/cref_files/xamarin/Syncfusion.SfChart.XForms~Syncfusion.SfChart.XForms.LabelContent.html) – This will show the corresponding Y value.

{% tabs %} 

{% highlight xaml %}

<chart:PieSeries>

	<chart:PieSeries.DataMarker>

		<chart:ChartDataMarker LabelContent="Percentage"/>

	</chart:PieSeries.DataMarker>

</chart:PieSeries>

{% endhighlight %}

{% highlight c# %}

pieSeries.DataMarker.LabelContent = LabelContent.Percentage;

{% endhighlight %}

{% endtabs %}

![Formatting the label content of data markers in Xamarin.Forms Chart](datamarker_images/datamarker_img3.png)

### DataMarker LabelFormat

Data marker labels can be formatted by using the [`LabelFormat`](http://help.syncfusion.com/cr/cref_files/xamarin/sfchart/Syncfusion.SfChart.XForms~Syncfusion.SfChart.XForms.ChartLabelStyle~LabelFormat.html) property. Data marker label values can be formatted with n (number with decimal points), c (Currency) and p (percentage) commands.

{% tabs %} 

{% highlight xaml %}

<chart:LineSeries.DataMarker>

    <chart:ChartDataMarker ShowLabel="True">
	
        <chart:ChartDataMarker.LabelStyle>
		
            <chart:DataMarkerLabelStyle LabelFormat="$##.##"/>
			
        </chart:ChartDataMarker.LabelStyle>
		
    </chart:ChartDataMarker>	
	
</chart:LineSeries.DataMarker>

{% endhighlight %}

{% highlight xaml %}

ChartDataMarker chartDataMarker = new ChartDataMarker();
chartDataMarker.LabelStyle = new DataMarkerLabelStyle { LabelFormat = "$##.##" };
series.DataMarker = chartDataMarker;

{% endhighlight %}

{% endtabs %}

![LabelFormat support in Xamarin.Forms Chart](datamarker_images/DataMarkerLabelFormat.png)

## Label position

The [`LabelPosition`](https://help.syncfusion.com/cr/cref_files/xamarin/Syncfusion.SfChart.XForms~Syncfusion.SfChart.XForms.DataMarkerLabelStyle~LabelPosition.html) property is used to position the data marker labels at [`Center`](https://help.syncfusion.com/cr/cref_files/xamarin/Syncfusion.SfChart.XForms~Syncfusion.SfChart.XForms.DataMarkerLabelPosition.html), [`Inner`](https://help.syncfusion.com/cr/cref_files/xamarin/Syncfusion.SfChart.XForms~Syncfusion.SfChart.XForms.DataMarkerLabelPosition.html) and [`Outer`](https://help.syncfusion.com/cr/cref_files/xamarin/Syncfusion.SfChart.XForms~Syncfusion.SfChart.XForms.DataMarkerLabelPosition.html) position of the actual data point position. By default, labels are positioned based on the series types for better readability. You can move the labels horizontally and vertically using [`OffsetX`](https://help.syncfusion.com/cr/cref_files/xamarin/Syncfusion.SfChart.XForms~Syncfusion.SfChart.XForms.DataMarkerLabelStyle~OffsetX.html) and [`OffsetY`](https://help.syncfusion.com/cr/cref_files/xamarin/Syncfusion.SfChart.XForms~Syncfusion.SfChart.XForms.DataMarkerLabelStyle~OffsetY.html) properties respectively.

The following screenshot illustrates the default position of data marker labels,

![Positioning the data marker labels support in Xamarin.Forms Chart](datamarker_images/datamarker_img4.png)

The following code sample illustrates the center position of data marker labels,

{% tabs %} 

{% highlight xaml %}

<chart:ChartDataMarker>

	<chart:ChartDataMarker.LabelStyle>

		<chart:DataMarkerLabelStyle LabelPosition="Center"/>

	</chart:ChartDataMarker.LabelStyle>

</chart:ChartDataMarker>

{% endhighlight %}

{% highlight c# %}

series.DataMarker.LabelStyle.LabelPosition = DataMarkerLabelPosition.Center;

{% endhighlight %}

{% endtabs %}

![Positioning the data marker labels support in Xamarin.Forms Chart](datamarker_images/datamarker_img5.png)

The following code sample illustrates the Inner position of data marker labels,

{% tabs %} 

{% highlight xaml %}

<chart:ChartDataMarker>

	<chart:ChartDataMarker.LabelStyle>

		<chart:DataMarkerLabelStyle LabelPosition="Inner"/>

	</chart:ChartDataMarker.LabelStyle>

</chart:ChartDataMarker>

{% endhighlight %}

{% highlight c# %}

series.DataMarker.LabelStyle.LabelPosition = DataMarkerLabelPosition.Inner;

{% endhighlight %}

{% endtabs %}

![Positioning the data marker labels support in Xamarin.Forms Chart](datamarker_images/datamarker_img6.png)

The following code sample illustrates the outer position of data marker labels, 

{% tabs %} 

{% highlight xaml %}

<chart:ChartDataMarker>

	<chart:ChartDataMarker.LabelStyle>

		<chart:DataMarkerLabelStyle LabelPosition="Outer"/>

	</chart:ChartDataMarker.LabelStyle>

</chart:ChartDataMarker>

{% endhighlight %}

{% highlight c# %}

series.DataMarker.LabelStyle.LabelPosition = DataMarkerLabelPosition.Outer;

{% endhighlight %}

{% endtabs %}

![Positioning the data marker labels support in Xamarin.Forms Chart](datamarker_images/datamarker_img7.png)

## Smart labels

This feature is used to arrange the data marker labels smartly and avoid the intersection when there is overlapping of labels. The property [`EnableSmartLabels`](https://help.syncfusion.com/cr/cref_files/xamarin/Syncfusion.SfChart.XForms~Syncfusion.SfChart.XForms.CircularSeries~EnableSmartLabels.html) in [`CircularSeries`](https://help.syncfusion.com/cr/cref_files/xamarin/Syncfusion.SfChart.XForms~Syncfusion.SfChart.XForms.CircularSeries.html), is used to arrange the data marker labels smartly. By default, it is false, we need to enable this property.

The following code sample illustrates how to enable the smart labels.

{% tabs %} 

{% highlight xaml %}

<chart:SfChart.Series>

	<chart:PieSeries ItemsSource="{Binding Data}"
					 XBindingPath="Expense"
					 YBindingPath="Value" 
					 StartAngle="75"
					 EndAngle ="435"
					 EnableSmartLabels="True"
					 ConnectorLineType = "Bezier" 
					 DataMarkerPosition = "OutsideExtended">
	
		<chart:PieSeries.DataMarker>
			<chart:ChartDataMarker />
		</chart:PieSeries.DataMarker>
		
	</chart:PieSeries>
	
</chart:SfChart.Series> 

{% endhighlight %}

{% highlight c# %}        

SfChart chart = new SfChart();
...

PieSeries pieSeries = new PieSeries()
{
	
	ItemsSource = Data,
	XBindingPath = "Expense",
	YBindingPath = "Value",
	EnableSmartLabels = true,
	DataMarkerPosition = CircularSeriesDataMarkerPosition.OutsideExtended,
	ConnectorLineType= ConnectorLineType.Bezier,
	StartAngle=75,
	EndAngle=435,
	DataMarker=new ChartDataMarker(),
	
};

chart.Series.Add(pieSeries);

{% endhighlight %}

{% endtabs %}

![Smart labels support for data markers in Xamarin.Forms Chart](datamarker_images/smartlabels.png)

## Customizing marker shapes

Shapes can be added to chart data marker by setting the [`ShowMarker`](https://help.syncfusion.com/cr/cref_files/xamarin/Syncfusion.SfChart.XForms~Syncfusion.SfChart.XForms.ChartDataMarker~ShowMarker.html) property to `true`. There are different shapes you can set to the chart using [`MarkerType`](https://help.syncfusion.com/cr/cref_files/xamarin/Syncfusion.SfChart.XForms~Syncfusion.SfChart.XForms.ChartDataMarker~MarkerType.html) property such as [`Triangle`](https://help.syncfusion.com/cr/cref_files/xamarin/Syncfusion.SfChart.XForms~Syncfusion.SfChart.XForms.DataMarkerType.html), [`Circle`](https://help.syncfusion.com/cr/cref_files/xamarin/Syncfusion.SfChart.XForms~Syncfusion.SfChart.XForms.DataMarkerType.html), [`Diamond`](https://help.syncfusion.com/cr/cref_files/xamarin/Syncfusion.SfChart.XForms~Syncfusion.SfChart.XForms.DataMarkerType.html) etc. Following properties are used to customize marker appearance,

* [`MarkerWidth`](https://help.syncfusion.com/cr/cref_files/xamarin/Syncfusion.SfChart.XForms~Syncfusion.SfChart.XForms.ChartDataMarker~MarkerWidth.html) - used to change the width of the marker
* [`MarkerHeight`](https://help.syncfusion.com/cr/cref_files/xamarin/Syncfusion.SfChart.XForms~Syncfusion.SfChart.XForms.ChartDataMarker~MarkerHeight.html) - used to change the height of the marker
* [`MarkerColor`](https://help.syncfusion.com/cr/cref_files/xamarin/Syncfusion.SfChart.XForms~Syncfusion.SfChart.XForms.ChartDataMarker~MarkerColor.html) - used to change the color of the marker
* [`MarkerBorderColor`](https://help.syncfusion.com/cr/cref_files/xamarin/Syncfusion.SfChart.XForms~Syncfusion.SfChart.XForms.ChartDataMarker~MarkerBorderColor.html) - used to change the border color of the shape
* [`MarkerBorderWidth`](https://help.syncfusion.com/cr/cref_files/xamarin/Syncfusion.SfChart.XForms~Syncfusion.SfChart.XForms.ChartDataMarker~MarkerBorderWidth.html) – used to change the marker border thickness

The following code example shows how to enable marker and specify its types,

{% tabs %} 

{% highlight xaml %}

<chart:LineSeries.DataMarker>

	<chart:ChartDataMarker ShowLabel="False" 
						   ShowMarker="True"
						   MarkerType="Hexagon"
						   MarkerWidth="20" 
						   MarkerHeight="20"
						   MarkerColor="Aqua" 
						   MarkerBorderColor="Red"
						   MarkerBorderWidth="2"/>

</chart:LineSeries.DataMarker>

{% endhighlight %}

{% highlight c# %}  

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

{% endtabs %}

![Data markers shape customization support in Xamarin.Forms Chart](datamarker_images/datamarker_img8.png)

## Apply series color

The [`UseSeriesPalette`](https://help.syncfusion.com/cr/cref_files/xamarin/Syncfusion.SfChart.XForms~Syncfusion.SfChart.XForms.ChartDataMarker~UseSeriesPalette.html) property is used to apply the series color to background color of data marker labels. The default value of this property is true.

{% tabs %} 

{% highlight xaml %}

<chart:ColumnSeries>

	<chart:ColumnSeries.DataMarker>

		<chart:ChartDataMarker UseSeriesPalette="False"/>

	</chart:ColumnSeries.DataMarker>

</chart:ColumnSeries>

{% endhighlight %}

{% highlight c# %}

columnSeries.DataMarker = new ChartDataMarker();
columnSeries.DataMarker.UseSeriesPalette = false;

{% endhighlight %}

{% endtabs %}

## Connector line

This feature is used to connect label and data point using a line. It can be enabled for any chart types but this is often used with Pie and Doughnut chart types. The [`ConnectorLineStyle`](https://help.syncfusion.com/cr/cref_files/xamarin/Syncfusion.SfChart.XForms~Syncfusion.SfChart.XForms.ChartDataMarker~ConnectorLineStyle.html) property used to customize the connector line.

* [`StrokeColor`](https://help.syncfusion.com/cr/cref_files/xamarin/Syncfusion.SfChart.XForms~Syncfusion.SfChart.XForms.ChartLineStyle~StrokeColor.html) – used to change the color of the line
* [`StrokeWidth`](https://help.syncfusion.com/cr/cref_files/xamarin/Syncfusion.SfChart.XForms~Syncfusion.SfChart.XForms.ChartLineStyle~StrokeWidth.html) – used to change the stroke thickness of the line
* [`StrokeDashArray`](https://help.syncfusion.com/cr/cref_files/xamarin/Syncfusion.SfChart.XForms~Syncfusion.SfChart.XForms.ChartLineStyle~StrokeDashArray.html) – used to set the dashes for the line
* [`ConnectorHeight`](https://help.syncfusion.com/cr/cref_files/xamarin/Syncfusion.SfChart.XForms~Syncfusion.SfChart.XForms.ConnectorLineStyle~ConnectorHeight.html) - used to set the height of the line.
* [`ConnectorRotationAngle`](https://help.syncfusion.com/cr/cref_files/xamarin/Syncfusion.SfChart.XForms~Syncfusion.SfChart.XForms.ConnectorLineStyle~ConnectorRotationAngle.html) - used to set the rotation angle of the line.

The following code illustrates how to specify the connector height and its angle,

{% tabs %} 

{% highlight xaml %}
      
<chart:LineSeries.DataMarker>

	<chart:ChartDataMarker>

		<chart:ChartDataMarker.ConnectorLineStyle>

			<chart:ConnectorLineStyle ConnectorHeight="50"
									  ConnectorRotationAngle="175" 
									  StrokeColor="Blue"
									  StrokeWidth="3"/>

		</chart:ChartDataMarker.ConnectorLineStyle>

	</chart:ChartDataMarker>

</chart:LineSeries.DataMarker>

{% endhighlight %}

{% highlight c# %}

lineSeries.DataMarker.ConnectorLineStyle.ConnectorHeight = 50;

lineSeries.DataMarker.ConnectorLineStyle.ConnectorRotationAngle = 175;

lineSeries.DataMarker.ConnectorLineStyle.StrokeColor = Color.Blue;

lineSeries.DataMarker.ConnectorLineStyle.StrokeWidth = 3;

lineSeries.DataMarker.ConnectorLineStyle.StrokeDashArray = new double[2] { 2, 3 };

{% endhighlight %}

{% endtabs %}

![Connector line support for data markers in Xamarin.Forms Chart](datamarker_images/datamarker_img9.png)

N> For Pie and Doughnut series, you can set different connector line types such as [`Line`](https://help.syncfusion.com/cr/cref_files/xamarin/Syncfusion.SfChart.XForms~Syncfusion.SfChart.XForms.ConnectorLineType.html), [`StraightLine`](https://help.syncfusion.com/cr/cref_files/xamarin/Syncfusion.SfChart.XForms~Syncfusion.SfChart.XForms.ConnectorLineType.html) and  [`Bezier`](https://help.syncfusion.com/cr/cref_files/xamarin/Syncfusion.SfChart.XForms~Syncfusion.SfChart.XForms.ConnectorLineType.html) curve using the [`ConnectorType`](https://help.syncfusion.com/cr/cref_files/xamarin/Syncfusion.SfChart.XForms~Syncfusion.SfChart.XForms.CircularSeries~ConnectorLineType.html) property of pie and doughnut series.

## Label template

You can customize the appearance of the data marker label with your own template using the [`LabelTemplate`](https://help.syncfusion.com/cr/cref_files/xamarin/Syncfusion.SfChart.XForms~Syncfusion.SfChart.XForms.ChartDataMarker~LabelTemplate.html) property of [`ChartDataMarker`](https://help.syncfusion.com/cr/cref_files/xamarin/Syncfusion.SfChart.XForms~Syncfusion.SfChart.XForms.ChartDataMarker.html).

N> The BindingContext of template is the corresponding underlying model provided in the items source of chart series.You can also bind the corresponding [`ChartDataMarkerLabel`](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfChart.XForms~Syncfusion.SfChart.XForms.ChartDataMarkerLabel.html) class object using the [`LabelContent`](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfChart.XForms~Syncfusion.SfChart.XForms.ChartDataMarker~LabelContent.html) property set as [`DataMarkerLabel`](http://help.syncfusion.com/cr/cref_files/xamarin/Syncfusion.SfChart.XForms~Syncfusion.SfChart.XForms.LabelContent.html).

{% tabs %} 

{% highlight xaml %}

<ContentPage.Resources>
    <ResourceDictionary>
        <DataTemplate x:Key="dataMarkerTemplate">
            <StackLayout Orientation="Horizontal">
                <Label Text="{Binding Value}" VerticalOptions="Center" FontSize = "15"/>
                <Image Source="Down.jpg" WidthRequest="30" HeightRequest="30"/>
            </StackLayout>
        </DataTemplate>    
    </ResourceDictionary>
</ContentPage.Resources>

<chart:SfChart.Series>
    <chart:BarSeries ItemsSource="{Binding Data}" XBindingPath="Name" YBindingPath="Value">
        <chart:BarSeries.DataMarker>
            <chart:ChartDataMarker ShowLabel="True" LabelTemplate="{StaticResource dataMarkerTemplate}">
                <chart:ChartDataMarker.LabelStyle>
                    <chart:DataMarkerLabelStyle LabelPosition="Outer" />
                </chart:ChartDataMarker.LabelStyle>  
            </chart:ChartDataMarker>
        </chart:BarSeries.DataMarker>
    </chart:BarSeries>
</chart:SfChart.Series>


{% endhighlight %}

{% highlight c# %}

SfChart chart = new SfChart ();
...

var barSeries = new BarSeries();
barSeries.Color = Color.FromRgb(231, 87, 89);
barSeries.ItemsSource = Data;
barSeries.XBindingPath = "Name";
barSeries.YBindingPath = "Value";
barSeries.DataMarker = new ChartDataMarker();
barSeries.DataMarker.ShowLabel = true;
barSeries.DataMarker.LabelStyle.LabelPosition = DataMarkerLabelPosition.Outer;

DataTemplate dataMarkerTemplate = new DataTemplate(() => 
{
    StackLayout stack = new StackLayout();
    stack.Orientation = StackOrientation.Horizontal;
    Label label = new Label();
    label.SetBinding(Label.TextProperty, "Value");
    label.FontSize = 15;
    label.VerticalOptions = LayoutOptions.Center;
    Image image = new Image();
    image.Source = "Down.jpg";
    image.WidthRequest = 30;
    image.HeightRequest = 30;
    stack.Children.Add(label);
    stack.Children.Add(image);
    return stack;
});

barSeries.DataMarker.LabelTemplate = dataMarkerTemplate;
chart.Series.Add(barSeries);

{% endhighlight %}

{% endtabs %}

![Label template support for data markers in Xamarin.Forms Chart](datamarker_images/datamarker_img10.png)

## Event

### DataMarkerLabelCreated

The [`DataMarkerLabelCreated`](https://help.syncfusion.com/cr/cref_files/xamarin/Syncfusion.SfChart.XForms~Syncfusion.SfChart.XForms.ChartSeries~DataMarkerLabelCreated_EV.html) event occurs when the data marker label is created. This argument contains object of the [`ChartDataMarkerLabel`](https://help.syncfusion.com/cr/cref_files/xamarin/Syncfusion.SfChart.XForms~Syncfusion.SfChart.XForms.ChartDataMarkerLabel.html). The following properties are available in [`DataMarkerLabel`](https://help.syncfusion.com/cr/cref_files/xamarin/Syncfusion.SfChart.XForms~Syncfusion.SfChart.XForms.ChartDataMarkerLabelCreatedEventArgs~DataMarkerLabel.html) to customize the appearance of data markers based on condition.

* [`Label`](https://help.syncfusion.com/cr/cref_files/xamarin/Syncfusion.SfChart.XForms~Syncfusion.SfChart.XForms.ChartDataMarkerLabel~Label.html) – Gets or sets the text of data marker.
* [`BackgroundColor`](https://help.syncfusion.com/cr/cref_files/xamarin/Syncfusion.SfChart.XForms~Syncfusion.SfChart.XForms.ChartDataMarkerLabel~BackgroundColor.html) – Gets the background color of data marker label.
* [`Index`](https://help.syncfusion.com/cr/cref_files/xamarin/Syncfusion.SfChart.XForms~Syncfusion.SfChart.XForms.ChartDataMarkerLabel~Index.html) – Gets the data point index of data marker label.
* [`XPosition`](https://help.syncfusion.com/cr/cref_files/xamarin/Syncfusion.SfChart.XForms~Syncfusion.SfChart.XForms.ChartDataMarkerLabel~XPosition.html) – Gets the x-position of data marker label.
* [`YPosition`](https://help.syncfusion.com/cr/cref_files/xamarin/Syncfusion.SfChart.XForms~Syncfusion.SfChart.XForms.ChartDataMarkerLabel~YPosition.html) – Gets the y-position of data marker label.
* [`LabelStyle`](https://help.syncfusion.com/cr/cref_files/xamarin/Syncfusion.SfChart.XForms~Syncfusion.SfChart.XForms.ChartDataMarkerLabel~LabelStyle.html) – Gets or sets the label style to customize the appearance of individual data marker label.
* [`MarkerWidth`](https://help.syncfusion.com/cr/cref_files/xamarin/Syncfusion.SfChart.XForms~Syncfusion.SfChart.XForms.ChartDataMarkerLabel~MarkerWidth.html) – Gets or sets the marker width.
* [`MarkerHeight`](https://help.syncfusion.com/cr/cref_files/xamarin/Syncfusion.SfChart.XForms~Syncfusion.SfChart.XForms.ChartDataMarkerLabel~MarkerHeight.html) – Gets or sets the marker height.
* [`MarkerBorderWidth`](https://help.syncfusion.com/cr/cref_files/xamarin/Syncfusion.SfChart.XForms~Syncfusion.SfChart.XForms.ChartDataMarkerLabel~MarkerBorderWidth.html) – Gets or sets the border width of marker symbol.
* [`MarkerBorderColor`](https://help.syncfusion.com/cr/cref_files/xamarin/Syncfusion.SfChart.XForms~Syncfusion.SfChart.XForms.ChartDataMarkerLabel~MarkerBorderColor.html) – Gets or sets the border color of marker symbol.
* [`MarkerColor`](https://help.syncfusion.com/cr/cref_files/xamarin/Syncfusion.SfChart.XForms~Syncfusion.SfChart.XForms.ChartDataMarkerLabel~MarkerColor.html) – Gets or sets the marker color.
* [`MarkerType`](https://help.syncfusion.com/cr/cref_files/xamarin/Syncfusion.SfChart.XForms~Syncfusion.SfChart.XForms.ChartDataMarkerLabel~MarkerType.html) – Gets or sets the shape type of marker. The available shapes are ellipse, diamond, hexagon, cross, HorizontalLine, VerticalLine, InvertedTriangle, triangle, pentagon, plus, and square.
* [`Data`](https://help.syncfusion.com/cr/cref_files/xamarin/Syncfusion.SfChart.XForms~Syncfusion.SfChart.XForms.ChartDataMarkerLabel~Data.html) - Gets the underlying data of data marker label.