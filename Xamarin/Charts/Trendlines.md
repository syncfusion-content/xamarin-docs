---
layout: post
title: Syncfusion.Xamarin.Forms Chart trendline
description: How to configure the chart trendlines and customize the appearance of the trendlines stroke color, width and Legend icon visibility in Essential Xamarin.Forms Chart.
platform: xamarin
control: Chart
documentation: ug
---

# Trendlines in Xamarin Charts (SfChart)

The [`Trendline`]() is a line drawn over the chart to display the overall direction of the results. And it built on the assumption based on current and past beliefs. 

N> We can draw trendlines for all type of cartesian series except bar type.

The following code examples shows how to add Trendlines in chart.

{% tabs %} 

{% highlight xaml %}

<chart:LineSeries  ItemsSource="{Binding linearData}"..>

    <chart:LineSeries.Trendlines>
        <chart:ChartTrendlineCollection>
            <chart:ChartTrendline />
        </chart:ChartTrendlineCollection>
    </chart:LineSeries.Trendlines>	

</chart:LineSeries>

{% endhighlight %}

{% highlight c# %}

LineSeries lineSeries = new LineSeries() { ...};

. . .

lineSeries.Trendlines = new ChartTrendlineCollection();

lineSeries.Trendlines.Add(new ChartTrendline());

{% endhighlight %}

{% endtabs %}

## Types of Trendline

SfChart support following types of [`Trendlines`]().

* [`Linear`]()
* [`Exponential`]()
* [`Logarithmic`]()
* [`Power`]()
* [`Polynomial`]()


### Linear

[`Linear`]() trendline was best-fit straight line for simple linear datasets. A linear trend line usually shows that something is increasing or decreasing at a steady rate. This is the default trendline to be drawn for the SfChart.

The following is the code example of this trend line.

{% tabs %} 

{% highlight xaml %}

<chart:LineSeries  ItemsSource="{Binding linearData}">

    <chart:LineSeries.Trendlines>
        <chart:ChartTrendlineCollection>
            <chart:ChartTrendline Type="Linear" Label="Linear"/>
        </chart:ChartTrendlineCollection>
    </chart:LineSeries.Trendlines>
</chart:LineSeries>

{% endhighlight %}

{% highlight c# %}

LineSeries lineSeries = new LineSeries() { ...};
lineSeries.Trendlines = new ChartTrendlineCollection();

ChartTrendline linearTrendline = new ChartTrendline()
{
    Type = ChartTrendlineType.Linear,
    Label = "Linear"
};

lineSeries.Trendlines.Add(linearTrendline);
Chart.Series.Add(lineSeries);

{% endhighlight %}

{% endtabs %}

### Logarithmic

A [`Logarithmic`]() trendline is the strongest-fit curved line, that is most effective when the data change rate increases or decreases rapidly. Logarithmic trends may use negative and/or positive values as well. 

The following is the code example of this trend line.

{% tabs %} 

{% highlight xaml %}

<chart:LineSeries  ItemsSource="{Binding linearData}">
    <chart:LineSeries.Trendlines>
        <chart:ChartTrendlineCollection>
            <chart:ChartTrendline Type="Logarithmic" Label="Logarithmic"/>
        </chart:ChartTrendlineCollection>
    </chart:LineSeries.Trendlines>
</chart:LineSeries>

{% endhighlight %}

{% highlight c# %}

LineSeries lineSeries = new LineSeries() { ...};
lineSeries.Trendlines = new ChartTrendlineCollection();

ChartTrendline linearTrendline = new ChartTrendline()
{
    Type = ChartTrendlineType.Logarithmic,
    Label = "Logarithmic"
};

lineSeries.Trendlines.Add(new ChartTrendline());
Chart.Series.Add(lineSeries);

{% endhighlight %}

{% endtabs %}

### Exponential

The [`Exponential`]() trendline is the curved line most useful for data values rise or fall at increasingly higher rates.

Note: SfChart will not generate Exponential trendline when your data contains zero or negative values. 

{% tabs %} 

{% highlight xaml %}

<chart:LineSeries  ItemsSource="{Binding linearData}">

    <chart:LineSeries.Trendlines>
        <chart:ChartTrendlineCollection>
            <chart:ChartTrendline Type="Exponential" Label="Exponential"/>
        </chart:ChartTrendlineCollection>
    </chart:LineSeries.Trendlines>
</chart:LineSeries>

{% endhighlight %}

{% highlight c# %}

LineSeries lineSeries = new LineSeries() { ...};
lineSeries.Trendlines = new ChartTrendlineCollection();

ChartTrendline linearTrendline = new ChartTrendline()
{
    Type = ChartTrendlineType.Exponential,
    Label = "Exponential"
};

lineSeries.Trendlines.Add(new ChartTrendline());
Chart.Series.Add(lineSeries);

{% endhighlight %}

{% endtabs %}

### Power

The [`Power`]() trendline is typically used with data sets to compare measurements that grow at a specific rate.

The following is the code example of this trend line.

{% tabs %} 

{% highlight xaml %}

<chart:LineSeries  ItemsSource="{Binding linearData}">

    <chart:LineSeries.Trendlines>
        <chart:ChartTrendlineCollection>
            <chart:ChartTrendline Type="Power" Label="Power"/>
        </chart:ChartTrendlineCollection>
    </chart:LineSeries.Trendlines>
</chart:LineSeries>

{% endhighlight %}

{% highlight c# %}

LineSeries lineSeries = new LineSeries() { ...};
lineSeries.Trendlines = new ChartTrendlineCollection();

ChartTrendline linearTrendline = new ChartTrendline()
{
    Type = ChartTrendlineType.Power,
    Label = "Power"
};

lineSeries.Trendlines.Add(new ChartTrendline());
Chart.Series.Add(lineSeries);

{% endhighlight %}

{% endtabs %}

### Polynomial

The [`polynomial`]() trendline is a curved line that is used when there are more data fluctuations. By default, this trendline calculated with order of 2, it will be override by the property [`PolyomialOrder`]().

The following is the code example of this trend line.

{% tabs %} 

{% highlight xaml %}

<chart:LineSeries  ItemsSource="{Binding linearData}">

     <chart:LineSeries.Trendlines>
         <chart:ChartTrendlineCollection>
             <chart:ChartTrendline Type="Polynomial" PolynomialOrder="3"/>
         </chart:ChartTrendlineCollection>
     </chart:LineSeries.Trendlines>
 </chart:LineSeries>


{% endhighlight %}

{% highlight c# %}

LineSeries lineSeries = new LineSeries() { ...};
lineSeries.Trendlines = new ChartTrendlineCollection();

ChartTrendline linearTrendline = new ChartTrendline()
{
    Type = ChartTrendlineType.Polynomial,
    PolynomialOrder = 3,
};

lineSeries.Trendlines.Add(new ChartTrendline());
Chart.Series.Add(lineSeries);

{% endhighlight %}

{% endtabs %}

## Forecasting

Forecasting is used to display trends about the future and the past beliefs.

The following two types of forecasting are available in SfChart:

* Forward Forecasting
* Backward Forecasting

### Forward Forecasting

For determining the future trends (in forward direction). The 
following code example explains the how to set the value for [`ForwardForecast`]().

{% tabs %} 

{% highlight xaml %}

<chart:LineSeries  ItemsSource="{Binding linearData}">

    <chart:LineSeries.Trendlines>
        <chart:ChartTrendlineCollection>
            <chart:ChartTrendline Type="Linear" ForwardForecast="3"/>
        </chart:ChartTrendlineCollection>
    </chart:LineSeries.Trendlines>
</chart:LineSeries>

{% endhighlight %}

{% highlight c# %}

lineSeries.Trendlines = new ChartTrendlineCollection();

ChartTrendline linearTrendline = new ChartTrendline()
{
    Type = ChartTrendlineType.Linear,
    ForwardForecast = 3,
};

lineSeries.Trendlines.Add(new ChartTrendline());

{% endhighlight %}

{% endtabs %}

### Backward Forecast

For determining the future trends (in backward direction). The following code example explains the how to set the value for [`BackwardForecast`]().

{% tabs %} 

{% highlight xaml %}

<chart:LineSeries  ItemsSource="{Binding linearData}">

    <chart:LineSeries.Trendlines>
        <chart:ChartTrendlineCollection>
            <chart:ChartTrendline Type="Linear" BackwardForecast="3"/>
        </chart:ChartTrendlineCollection>
    </chart:LineSeries.Trendlines>
</chart:LineSeries>

{% endhighlight %}

{% highlight c# %}

lineSeries.Trendlines = new ChartTrendlineCollection();
ChartTrendline linearTrendline = new ChartTrendline()
{
    Type = ChartTrendlineType.Linear,
    BackwardForecast = 3,
};

lineSeries.Trendlines.Add(new ChartTrendline());
Chart.Series.Add(lineSeries);

{% endhighlight %}

{% endtabs %}

# Customization

We can customize the trendline appearance using [`StrokeWidth`](), [`StrokeColor`]() and [`StrokeDashArray`]() properties. 

{% tabs %} 

{% highlight xaml %}

<chart:LineSeries.Trendlines>

    <chart:ChartTrendlineCollection>
        <chart:ChartTrendline StrokeWidth="3" StrokeColor="Red">
            <chart:ChartTrendline.StrokeDashArray>
                <x:Array Type="{x:Type x:Double}">
                    <sys:Double>5</sys:Double>
                    <sys:Double>6</sys:Double>
                </x:Array>
            </chart:ChartTrendline.StrokeDashArray>
        </chart:ChartTrendline>
    </chart:ChartTrendlineCollection>
</chart:LineSeries.Trendlines>

{% endhighlight %}

{% highlight c# %}

lineSeries.Trendlines = new ChartTrendlineCollection();

ChartTrendline linearTrendline = new ChartTrendline()
{
   StrokeColor = Color.Red,
   StrokeWidth = 3,
   StrokeDashArray = new double[] {5,6},
};

lineSeries.Trendlines.Add(new ChartTrendline());

{% endhighlight %}

{% endtabs %}

# Legend Item Visibility

We can able to control the visibility of the trendline legend items using [`IsVisibleOnLegend`]() property of the Trendline.

{% tabs %} 

{% highlight xaml %}

<chart:LineSeries.Trendlines>
    <chart:ChartTrendlineCollection>
        <chart:ChartTrendline IsVisibleOnLegend="True" >
        </chart:ChartTrendline>
    </chart:ChartTrendlineCollection>
</chart:LineSeries.Trendlines>

{% endhighlight %}

{% highlight c# %}

lineSeries.Trendlines = new ChartTrendlineCollection();

ChartTrendline linearTrendline = new ChartTrendline()
{
    IsVisibleOnLegend = true;
};

lineSeries.Trendlines.Add(new ChartTrendline());

{% endhighlight %}

{% endtabs %}
