---
layout: post
title: Customizing the appearance of Essential Xamarin.Forms chart
description: Learn how to customize the appearance of chart using palettes.
platform: Xamarin
control: Chart
documentation: ug
---

# Color Palette

## Apply palette for chart

The [`ColorModel`](http://help.syncfusion.com/cr/cref_files/xamarin/sfchart/Syncfusion.SfChart.XForms~Syncfusion.SfChart.XForms.ChartColorModel.html) property of [`SfChart`](http://help.syncfusion.com/cr/cref_files/xamarin/sfchart/Syncfusion.SfChart.XForms~Syncfusion.SfChart.XForms.SfChart.html) is used to define the colors for each series. This property contains the following color palettes:

**Predefined palettes**

Currently, chart supports only the [`Metro`](https://help.syncfusion.com/cr/cref_files/xamarin/sfchart/Syncfusion.SfChart.XForms~Syncfusion.SfChart.XForms.ChartColorPalette.html) palette, and this is also the default palette for chart. The following screenshot illustrates the default appearance of multiple series.

![](appearance_images/appearance_img1.png)

**Custom palette**

Chart uses the colors from the [`CustomBrushes`](http://help.syncfusion.com/cr/cref_files/xamarin/sfchart/Syncfusion.SfChart.XForms~Syncfusion.SfChart.XForms.ChartColorModel~CustomBrushes.html) property if the [`ColorModel.Palette`](http://help.syncfusion.com/cr/cref_files/xamarin/sfchart/Syncfusion.SfChart.XForms~Syncfusion.SfChart.XForms.ChartColorModel~Palette.html) is set to [`Custom`](http://help.syncfusion.com/cr/cref_files/xamarin/sfchart/Syncfusion.SfChart.XForms~Syncfusion.SfChart.XForms.ChartColorPalette.html).

The following code illustrates how to set the custom colors.

{% tabs %} 

{% highlight xaml %}

<ContentPage.Resources>
    <ResourceDictionary>
        <chart:ChartColorCollection x:Key="Colors">
            <Color>Red</Color>
            <Color>Gray</Color>
            <Color>Blue</Color>
            <Color>Maroon</Color>
            <Color>Pink</Color>
        </chart:ChartColorCollection>
    </ResourceDictionary>
</ContentPage.Resources>

<chart:SfChart>
    <chart:SfChart.ColorModel>
        <chart:ChartColorModel Palette="Custom" CustomBrushes="{StaticResource Colors}"/>
    </chart:SfChart.ColorModel>

    ...
</chart:SfChart>

{% endhighlight %}

{% highlight c# %}

SfChart chart = new SfChart()
{
     ColorModel = new ChartColorModel()
     {
         Palette = ChartColorPalette.Custom,
         CustomBrushes = new ChartColorCollection()
         {
             Color.Red,
             Color.Gray,
             Color.Blue,
             Color.Maroon,
             Color.Pink,
         }
     },
	 ...
}; 

{% endhighlight %}

{% endtabs %}

![](appearance_images/appearance_img2.png)

**None palette**

[`None`](https://help.syncfusion.com/cr/cref_files/xamarin/sfchart/Syncfusion.SfChart.XForms~Syncfusion.SfChart.XForms.ChartColorPalette.html) palette will not apply any color to the series. So in order to define the color for any series, use the [`Color`](https://help.syncfusion.com/cr/cref_files/xamarin/sfchart/Syncfusion.SfChart.XForms~Syncfusion.SfChart.XForms.ChartSeries~Color.html) or [`ColorModel`](http://help.syncfusion.com/cr/cref_files/xamarin/sfchart/Syncfusion.SfChart.XForms~Syncfusion.SfChart.XForms.ChartColorModel.html) property of [`ChartSeries`](https://help.syncfusion.com/cr/cref_files/xamarin/sfchart/Syncfusion.SfChart.XForms~Syncfusion.SfChart.XForms.ChartSeries.html). The [`ColorModel`](http://help.syncfusion.com/cr/cref_files/xamarin/sfchart/Syncfusion.SfChart.XForms~Syncfusion.SfChart.XForms.ChartColorModel.html) property of series will be explained later in this document.

## Apply palette for series

The [`ColorModel`](http://help.syncfusion.com/cr/cref_files/xamarin/sfchart/Syncfusion.SfChart.XForms~Syncfusion.SfChart.XForms.ChartColorModel.html) property of [`ChartSeries`](http://help.syncfusion.com/cr/cref_files/xamarin/sfchart/Syncfusion.SfChart.XForms~Syncfusion.SfChart.XForms.ChartSeries.html) is used to define the colors for each data point. The following palettes are used to define the colors:

**Predefined palettes**

Currently, chart supports only [`Metro`](https://help.syncfusion.com/cr/cref_files/xamarin/sfchart/Syncfusion.SfChart.XForms~Syncfusion.SfChart.XForms.ChartColorPalette.html) palette.

{% tabs %} 

{% highlight xaml %}

<chart:SfChart>
...

	<chart:ColumnSeries ItemsSource ="{Binding Data}" XBindingPath="Country" YBindingPath="Value">

		<chart:ColumnSeries.ColorModel>

			<chart:ChartColorModel Palette="Metro"/>

		</chart:ColumnSeries.ColorModel>

	</chart:ColumnSeries>

</chart:SfChart>

{% endhighlight %}

{% highlight c# %}

SfChart chart = new SfChart();
...

ColumnSeries columnSeries = new ColumnSeries() { 

	ItemsSource = Data, 
	XBindingPath = "Country", 
	YBindingPath = "Value" 
	
};

columnSeries.ColorModel.Palette = ChartColorPalette.Metro;

chart.Series.Add(columnSeries);

{% endhighlight %}

{% endtabs %}

![](appearance_images/appearance_img3.png)

**Custom palette**

Series will use the colors from the [`CustomBrushes`](https://help.syncfusion.com/cr/cref_files/xamarin/sfchart/Syncfusion.SfChart.XForms~Syncfusion.SfChart.XForms.ChartColorModel~CustomBrushes.html) property if the [`ColorModel.Palette`](https://help.syncfusion.com/cr/cref_files/xamarin/sfchart/Syncfusion.SfChart.XForms~Syncfusion.SfChart.XForms.ChartColorModel~Palette.html) property of series is set to [`Custom`](https://help.syncfusion.com/cr/cref_files/xamarin/sfchart/Syncfusion.SfChart.XForms~Syncfusion.SfChart.XForms.ChartColorPalette.html).

The following code illustrates how to set the custom colors.

{% tabs %} 

{% highlight xaml %}

<ContentPage.Resources>
    <ResourceDictionary>
        <chart:ChartColorCollection x:Key="Colors">
             <Color>Red</Color>
             <Color>Gray</Color>
             <Color>Blue</Color>
             <Color>Maroon</Color>
             <Color>Pink</Color>
        </chart:ChartColorCollection>
    </ResourceDictionary>
</ContentPage.Resources>

<chart:SfChart>
    ...
    <chart:SfChart.Series>
        <chart:ColumnSeries ItemsSource="{Binding Data}" XBindingPath="Name" YBindingPath="Height">
            <chart:ColumnSeries.ColorModel>
                <chart:ChartColorModel Palette="Custom" CustomBrushes="{StaticResource Colors}"/>
            </chart:ColumnSeries.ColorModel>
        </chart:ColumnSeries>
    </chart:SfChart.Series>
</chart:SfChart>

{% endhighlight %}

{% highlight c# %}

SfChart chart = new SfChart()
{
    ...
    Series =
    {
       new ColumnSeries()
       {
             ItemsSource = viewModel.Data,
             XBindingPath = "Name",
             YBindingPath = "Height",
             ColorModel = new ChartColorModel()
             {
                 Palette = ChartColorPalette.Custom,
                 CustomBrushes = new ChartColorCollection()
                 {
                    Color.Red,
                    Color.Gray,
                    Color.Blue,
                    Color.Maroon,
                    Color.Pink,
                 }
             }
        }
    }
};

{% endhighlight %}

{% endtabs %}

![](appearance_images/appearance_img4.png)

**None palette**

[`None`](https://help.syncfusion.com/cr/cref_files/xamarin/sfchart/Syncfusion.SfChart.XForms~Syncfusion.SfChart.XForms.ChartColorPalette.html) palette will not apply any color to the data points. So in order to define the color for the data points, use the [`Color`](http://help.syncfusion.com/cr/cref_files/xamarin/sfchart/Syncfusion.SfChart.XForms~Syncfusion.SfChart.XForms.ChartSeries~ColorProperty.html) property of [`ChartSeries`](http://help.syncfusion.com/cr/cref_files/xamarin/sfchart/Syncfusion.SfChart.XForms~Syncfusion.SfChart.XForms.ChartSeries.html).
