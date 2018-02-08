---
layout: post
title: Getting Started for Essential Xamarin.Forms Chart
description: How to create a chart, add series, legend and multiple Y axis in Chart.
platform: xamarin
control: Chart
documentation: ug
---

# Getting Started

This section explains the steps required to populate a chart with data, title, data labels, and tooltips. This section covers only the minimal features that are needed to get started with chart.

## Adding chart reference

Refer to this [article](https://help.syncfusion.com/xamarin/introduction/download-and-installation) to know how to obtain and reference Essential Studio components in your solution; then refer to this [link](https://help.syncfusion.com/xamarin/introduction/control-dependencies#sfchart) to know about the assemblies required for adding chart to your project.

I> After adding the reference, an additional step is required for iOS and UWP projects. Create an instance of the `SfChartRenderer` in iOS and UWP projects as shown in this [KB article](https://www.syncfusion.com/kb/7144).

I> For UWP alone, an additional step is required if the project is built-in release mode with .NET Native tool chain enabled. Refer this [KB article](https://www.syncfusion.com/kb/7149) for more details.
 
## Initialize chart

Import the [`SfChart`](https://help.syncfusion.com/cr/cref_files/xamarin/sfchart/Syncfusion.SfChart.XForms~Syncfusion.SfChart.XForms.SfChart.html) namespace as shown in the following code in your respective page,

{% tabs %} 

{% highlight xaml %} 

xmlns:chart="clr-namespace:Syncfusion.SfChart.XForms;assembly=Syncfusion.SfChart.XForms" 

{% endhighlight %}

{% highlight C# %} 

using Syncfusion.SfChart.XForms;

{% endhighlight %}

{% endtabs %} 

Then, initialize an empty chart with two axes as shown in the following code,

{% tabs %} 

{% highlight xaml %} 
<chart:SfChart>

    <chart:SfChart.PrimaryAxis>

        <chart:CategoryAxis>
 
        </chart:CategoryAxis>

    </chart:SfChart.PrimaryAxis>

    <chart:SfChart.SecondaryAxis>

        <chart:NumericalAxis>

        </chart:NumericalAxis>

    </chart:SfChart.SecondaryAxis>
		  
</chart:SfChart>
{% endhighlight %}

{% highlight C# %} 
SfChart chart = new SfChart();

 //Initializing Primary Axis
CategoryAxis primaryAxis = new CategoryAxis();

chart.PrimaryAxis = primaryAxis;

//Initializing Secondary Axis
NumericalAxis secondaryAxis  =  new NumericalAxis  ();

chart.SecondaryAxis = secondaryAxis;

this.Content = chart;
{% endhighlight %}

{% endtabs %} 

Run the project, and check if you get following output to make sure that you have configured your project properly to add [`SfChart`](https://help.syncfusion.com/cr/cref_files/xamarin/sfchart/Syncfusion.SfChart.XForms~Syncfusion.SfChart.XForms.SfChart.html).

![](Getting-Started_images/img1.png)

## Initialize view model

The following code illustrates a simple data model that represents a data point in [`SfChart`](https://help.syncfusion.com/cr/cref_files/xamarin/sfchart/Syncfusion.SfChart.XForms~Syncfusion.SfChart.XForms.SfChart.html).

{% highlight c# %}
public class Person   
{   
    public string Name { get; set; }

    public double Height { get; set; }
}
{% endhighlight %} 

Next, create a view model class, and initialize a list of `Person` objects as shown in the following code,

{% highlight c# %}
public class ViewModel  
{
      public List<Person> Data { get; set; }      

      public ViewModel()       
      {
            Data = new List<Person>()
            {
                new Person { Name = "David", Height = 180 },
                new Person { Name = "Michael", Height = 170 },
                new Person { Name = "Steve", Height = 160 },
                new Person { Name = "Joel", Height = 182 }
            }; 
       }
 }
{% endhighlight %} 

Set the `ViewModel` instance as the `BindingContext` of your page to bind the properties of `ViewModel` to [`SfChart`](https://help.syncfusion.com/cr/cref_files/xamarin/sfchart/Syncfusion.SfChart.XForms~Syncfusion.SfChart.XForms.SfChart.html).
 
N> Add the namespace of `ViewModel` class in your XAML page if you need to set `BindingContext` in XAML.

{% tabs %} 

{% highlight xaml %} 
<ContentPage xmlns="http://xamarin.com/schemas/2014/forms"

             xmlns:x="http://schemas.microsoft.com/winfx/2009/xaml"

             x:Class="ChartDemo.MainPage"

             xmlns:chart="clr-namespace:Syncfusion.SfChart.XForms;assembly=Syncfusion.SfChart.XForms"

             xmlns:local="clr-namespace:ChartDemo"> 
   
    <ContentPage.BindingContext>
       
	    <local:ViewModel></local:ViewModel>
   
    </ContentPage.BindingContext>
 
</ContentPage>
{% endhighlight %}

{% highlight C# %} 
this.BindingContext = new ViewModel();
{% endhighlight %}

{% endtabs %} 

## Populate chart with data

To visualize the comparison of heights in the data model, add the [`ColumnSeries`](https://help.syncfusion.com/cr/cref_files/xamarin/sfchart/Syncfusion.SfChart.XForms~Syncfusion.SfChart.XForms.ColumnSeries.html) to the [`SfChart.Series`](https://help.syncfusion.com/cr/cref_files/xamarin/sfchart/Syncfusion.SfChart.XForms~Syncfusion.SfChart.XForms.SfChart~Series.html) property, and then bind the data property of previous `ViewModel` to the [`ColumnSeries.ItemsSource`](https://help.syncfusion.com/cr/cref_files/xamarin/sfchart/Syncfusion.SfChart.XForms~Syncfusion.SfChart.XForms.ChartSeries~ItemsSource.html) property as shown in the following code,

N> You should set [`XBindingPath`](https://help.syncfusion.com/cr/cref_files/xamarin/sfchart/Syncfusion.SfChart.XForms~Syncfusion.SfChart.XForms.ChartSeries~XBindingPath.html) and [`YBindingPath`](https://help.syncfusion.com/cr/cref_files/xamarin/sfchart/Syncfusion.SfChart.XForms~Syncfusion.SfChart.XForms.XyDataSeries~YBindingPath.html) properties to [`SfChart`](https://help.syncfusion.com/cr/cref_files/xamarin/sfchart/Syncfusion.SfChart.XForms~Syncfusion.SfChart.XForms.SfChart.html). By setting these properties, chart can fetch the values from the respective properties in the data model to plot the series.

{% tabs %}   

{% highlight xaml %}
<chart:SfChart>
   
   <chart:SfChart.PrimaryAxis>
    
        <chart:CategoryAxis>

            <chart:CategoryAxis.Title>

                  <chart:ChartAxisTitle Text="Name"> </chart:ChartAxisTitle>

            </chart:CategoryAxis.Title>

         </chart:CategoryAxis>
   
   </chart:SfChart.PrimaryAxis>

   <chart:SfChart.SecondaryAxis>
  
       <chart:NumericalAxis>
            
           <chart:NumericalAxis.Title>
           
                 <chart:ChartAxisTitle Text="Height (in cm)"></chart:ChartAxisTitle>
           
          </chart:NumericalAxis.Title>      
       
      </chart:NumericalAxis>   

     </chart:SfChart.SecondaryAxis>
    
      <chart:SfChart.Series>
              
         <chart:ColumnSeries ItemsSource="{Binding Data}" XBindingPath="Name" YBindingPath="Height">
		 
		 </chart:ColumnSeries>
    
      </chart:SfChart.Series>

 </chart:SfChart> 
{% endhighlight %}

{% highlight C# %}
//Initializing primary axis
CategoryAxis primaryAxis = new CategoryAxis();

primaryAxis.Title.Text = "Name";

chart.PrimaryAxis = primaryAxis;

//Initializing secondary Axis
NumericalAxis secondaryAxis = new NumericalAxis();

secondaryAxis.Title.Text = "Height (in cm)";

chart.SecondaryAxis = secondaryAxis;

//Initializing column series
ColumnSeries series = new ColumnSeries();

series.SetBinding(ChartSeries.ItemsSourceProperty, "Data");

series.XBindingPath = "Name";

series.YBindingPath = "Height";

chart.Series.Add(series);
{% endhighlight %}

{% endtabs %} 

## Add title

You can add title to chart to provide information to the user about the data being plotted in the chart. Title can be set using the [`SfChart.Title`](https://help.syncfusion.com/cr/cref_files/xamarin/sfchart/Syncfusion.SfChart.XForms~Syncfusion.SfChart.XForms.SfChart~Title.html) property as shown in the following code,

{% tabs %} 

{% highlight xaml %}
<chart:SfChart>

	...

   <chart:SfChart.Title>

        <chart:ChartTitle Text="Chart"/>  

   </chart:SfChart.Title>

	...

</chart:SfChart>
{% endhighlight %}

{% highlight C# %} 
chart.Title.Text = "Chart";
{% endhighlight %}

{% endtabs %}  

Refer to this [link](https://help.syncfusion.com/xamarin/sfchart/charttitle) to learn more about the options available in [`SfChart`](https://help.syncfusion.com/cr/cref_files/xamarin/sfchart/Syncfusion.SfChart.XForms~Syncfusion.SfChart.XForms.SfChart.html) to customize chart title.

## Enable data labels

You can add data labels to improve the readability of the chart. This can be achieved using the [`ChartSeries.DataMarkers`](https://help.syncfusion.com/cr/cref_files/xamarin/sfchart/Syncfusion.SfChart.XForms~Syncfusion.SfChart.XForms.ChartSeries~DataMarker.html) property as shown in the following code,

{% tabs %} 

{% highlight xaml %}
<chart:SfChart>

	...

        <chart:ColumnSeries>

	     <chart:ColumnSeries.DataMarker>

		 <chart:ChartDataMarker/>

	     </chart:ColumnSeries.DataMarker>

       </chart:ColumnSeries>

	...

</chart:SfChart>
{% endhighlight %}

{% highlight C# %} 
series.DataMarker = new ChartDataMarker();
{% endhighlight %}

{% endtabs %}  

Refer to this [link](https://help.syncfusion.com/xamarin/sfchart/datamarker) to learn more about the options available in [`SfChart`](https://help.syncfusion.com/cr/cref_files/xamarin/sfchart/Syncfusion.SfChart.XForms~Syncfusion.SfChart.XForms.SfChart.html) to customize data markers.

## Enable legend

You can enable the legend using the [`SfChart.Legend`](https://help.syncfusion.com/cr/cref_files/xamarin/sfchart/Syncfusion.SfChart.XForms~Syncfusion.SfChart.XForms.SfChart~Legend.html) property as shown in the following code,

{% tabs %} 

{% highlight xaml %}
<chart:SfChart>

	...

    <chart:SfChart.Legend>

        <chart:ChartLegend/>

    </chart:SfChart.Legend>

    ...

</chart:SfChart>
{% endhighlight %}

{% highlight C# %} 
chart.Legend = new ChartLegend (); 
{% endhighlight %}

{% endtabs %}  

Additionally, set label for each series using the [`ChartSeries.Label`](https://help.syncfusion.com/cr/cref_files/xamarin/sfchart/Syncfusion.SfChart.XForms~Syncfusion.SfChart.XForms.ChartSeries~Label.html) property that will be displayed in corresponding legend.

{% tabs %} 

{% highlight xaml %}
<chart:SfChart>

	...

      <chart:SfChart.Series>
              
         <chart:ColumnSeries Label="Heights" ItemsSource="{Binding Data}" XBindingPath="Name" YBindingPath="Height">
		 
		 </chart:ColumnSeries>
         
       </chart:SfChart.Series>

	...

</chart:SfChart>
{% endhighlight %}

{% highlight C# %} 
series.Label = "Heights";
{% endhighlight %}

{% endtabs %}  

Refer to this [link](https://help.syncfusion.com/xamarin/sfchart/legend) to learn more about the options available in the [`SfChart`](https://help.syncfusion.com/cr/cref_files/xamarin/sfchart/Syncfusion.SfChart.XForms~Syncfusion.SfChart.XForms.SfChart.html) to customize the legend.

## Enable tooltip

Tooltips are used to show information about the segment, when the segment is tapped. You can enable the tooltip by setting the [`ChartSeries.EnableTooltip`](https://help.syncfusion.com/cr/cref_files/xamarin/sfchart/Syncfusion.SfChart.XForms~Syncfusion.SfChart.XForms.ChartSeries~EnableTooltip.html) property to true.

{% tabs %} 

{% highlight xaml %}
<chart:SfChart>

	...

   <chart:SfChart.Series>
       
        <chart:ColumnSeries ItemsSource="{Binding Data}" XBindingPath="Name" YBindingPath="Height" EnableTooltip ="True">
		
		</chart:ColumnSeries>
   
   </chart:SfChart.Series>

	...

 </chart:SfChart> 
{% endhighlight %}

{% highlight C# %} 
series.EnableTooltip = true;
{% endhighlight %}

{% endtabs %}

Refer to this [link](https://help.syncfusion.com/xamarin/sfchart/tooltip) to learn more about the options available in the [`SfChart`](https://help.syncfusion.com/cr/cref_files/xamarin/sfchart/Syncfusion.SfChart.XForms~Syncfusion.SfChart.XForms.SfChart.html) to customize the tooltip.

![](Getting-Started_images/img2.png)

You can see the complete getting started sample from this [link](http://files2.syncfusion.com/Xamarin.Forms/Samples/Chart_GettingStarted.zip).

