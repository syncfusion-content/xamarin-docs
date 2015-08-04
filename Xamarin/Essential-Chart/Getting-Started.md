---
layout: post
title: Getting-Started
description: getting started
platform: ios
control: Control Name undefined
documentation: ug
---

### Getting Started

This section provides a quick overview for working with Essential Chart for Xamarin.Forms. You can walk through the entire process of creating a real world chart.

The goal of this tutorial is to visualize the weather data for Washington, DC during the period 1961-1990. The raw sample data is given below.

<table>
<tr>
<td>
Month</td><td>
High</td><td>
Low</td><td>
Precipitation</td></tr>
<tr>
<td>
January</td><td>
42</td><td>
27</td><td>
3.03</td></tr>
<tr>
<td>
February</td><td>
44</td><td>
28</td><td>
2.48</td></tr>
<tr>
<td>
March</td><td>
53</td><td>
35</td><td>
3.23</td></tr>
<tr>
<td>
April</td><td>
64</td><td>
44</td><td>
3.15</td></tr>
<tr>
<td>
May</td><td>
75</td><td>
54</td><td>
4.13</td></tr>
<tr>
<td>
June</td><td>
83</td><td>
63</td><td>
3.23</td></tr>
<tr>
<td>
July</td><td>
87</td><td>
68</td><td>
4.13</td></tr>
<tr>
<td>
August</td><td>
84</td><td>
66</td><td>
4.88</td></tr>
<tr>
<td>
September</td><td>
78</td><td>
59</td><td>
3.82</td></tr>
<tr>
<td>
October</td><td>
67</td><td>
48</td><td>
3.07</td></tr>
<tr>
<td>
November</td><td>
55</td><td>
38</td><td>
2.83</td></tr>
<tr>
<td>
December</td><td>
45</td><td>
29</td><td>
2.8</td></tr>
</table>

This is how the final output will look like on iOS, Android and Windows Phone devices. You can also download the entire source code of this demo from [here.](http://files2.syncfusion.com/Installs/v12.2.0.40/Samples/Xamarin/Chart_GettingStarted.zip)

![](Getting-Started_images/Getting-Started_img1.png)
{:.image }


Referencing Essential Studio components in your solution

If you had acquired Essential Studio components through the Xamarin component store interface from within your IDE, then after adding the components to your Xamarin.iOS, Xamarin.Android and Windows Phone projects through the Component manager, you will still need to manually reference the PCL (Portable Class Library) assemblies in the Xamarin.Forms PCL project in your solution. You can do this by manually adding the relevant PCL assembly references to your PCL project contained in the following path inside of your solution folder.  

_Components/syncfusionessentialstudio-version/lib/pcl/_

Alternatively if you had downloaded Essential Studio from Syncfusion.com or through the Xamarin store web interface then all assembly references need to be added manually.

After installing Essential Studio for Xamarin, all the required assemblies can be found in the installation folders, typically

{Syncfusion Installed location}\Essential Studio\12.2.0.40\lib

_Eg: C:\Program Files (x86)\Syncfusion\Essential Studio\12.2.0.40\lib_

or after downloading through the Xamarin store web interface, all the required assemblies can be found in the below folder

{download location}\syncfusionessentialstudio-version\lib

You can then add the assembly references to the respective projects as shown below

PCL project

pcl\Syncfusion.SfChart.XForm.dll 

Android project

 	android\Syncfusion.SfChart.Andriod.dll

android\Syncfusion.SfChart.xForms.Andriod.dll

iOS project

ios\Syncfusion.SfChart.iOS.dll 

ios\Syncfusion.SfChart.xForms.iOS.dll

ios\Syncfusion.SfChart.XForm.dll

Windows Phone project

wp8\Syncfusion.SfChart.WP8.dll

wp8\Syncfusion.SfChart.xForms.WinPhone.dll

> ![C:/Users/ApoorvahR/Desktop/Note.png](Getting-Started_images/Getting-Started_img2.png)
{:.image }
_Note: Essential Chart for Xamarin is compatible with Xamarin. Forms v.1.2.3.6257._

Currently an additional step is required for Windows Phone and iOS projects. We need to create an instance of the chart custom renderer as shown below. 

Create an instance of SfChartRenderer in MainPage constructor in of the Windows Phone project as shown 

  	 public MainPage()

       	 {

           		 new SfChartRenderer();

        		    ...    

     	}

Create an instance of SfChartRenderer in FinishedLaunching overridden method of AppDelegate class in iOS Project as shown below

public override bool FinishedLaunching(UIApplication app, NSDictionary options)

        	{

         		  ...

         		  new SfChartRenderer ();

        		   ...

       	 }	

Adding and configuring the chart

The chart control can be configured entirely in C# code or using XAML markup.

1. Create an instance of SfChart.
2. Add the primary and secondary axis for the chart as shown below.





[C#]

SfChart chart = new SfChart ();

_//Initializing Primary Axis_
CategoryAxis primaryAxis = new CategoryAxis ();
primaryAxis.Title = new ChartAxisTitle (){ Text = "Month" };

chart.PrimaryAxis = primaryAxis;

_//Initializing Secondary Axis_
NumericalAxis secondaryAxis = new NumericalAxis ();
secondaryAxis.Title = new ChartAxisTitle (){ Text = "Temperature" };

chart.SecondaryAxis = secondaryAxis;

this.Content = chart;



[XAML]

  &lt;chart:SfChart&gt;



    &lt;chart:SfChart.PrimaryAxis&gt;

      &lt;chart:CategoryAxis&gt;

        &lt;chart:CategoryAxis.Title&gt;

          &lt;chart:ChartAxisTitle Text="Month"/&gt;

        &lt;/chart:CategoryAxis.Title&gt;

      &lt;/chart:CategoryAxis&gt;

    &lt;/chart:SfChart.PrimaryAxis&gt;



    &lt;chart:SfChart.SecondaryAxis&gt;

      &lt;chart:NumericalAxis&gt;

        &lt;chart:NumericalAxis&gt;

          &lt;chart:ChartAxisTitle Text="Month"/&gt;

        &lt;/chart:NumericalAxis&gt;

      &lt;/chart:NumericalAxis&gt;

    &lt;/chart:SfChart.SecondaryAxis&gt;



  &lt;/chart:SfChart&gt;



3. A title for the chart is set using the Title property as shown below,



[C#] 

chart.Title = new ChartTitle (){ Text = "Weather Analysis" };



[XAML]

  &lt;chart:SfChart&gt;



    &lt;chart:SfChart.Title&gt;

     &lt;chart:ChartTitle Text="Weather Analysis"/&gt;  

    &lt;/chart:SfChart.Title&gt;

    …

  &lt;/chart:SfChart&gt;

Add Chart series

In this sample, we will be visualize the temperature over the months using a Column Series. Before creating the series, let’s create a data model representing the climate details data. 

In SfChart, the series itemsource should be a collection of _ChartDataPoint_ objects. Add the following class for generating the datapoints.



    public class DataModel
    {
        public ObservableCollection<ChartDataPoint>  HighTemperature;

        public DataModel ()
        {
            HighTemperature = new ObservableCollection<ChartDataPoint> ();

            HighTemperature.Add (new ChartDataPoint ("Jan", 42));
            HighTemperature.Add (new ChartDataPoint ("Feb", 44));
            HighTemperature.Add (new ChartDataPoint ("Mar", 53));
            HighTemperature.Add (new ChartDataPoint ("Apr", 64));
            HighTemperature.Add (new ChartDataPoint ("May", 75));
            HighTemperature.Add (new ChartDataPoint ("Jun", 83));
            HighTemperature.Add (new ChartDataPoint ("Jul", 87));
            HighTemperature.Add (new ChartDataPoint ("Aug", 84));
            HighTemperature.Add (new ChartDataPoint ("Sep", 78));
            HighTemperature.Add (new ChartDataPoint ("Oct", 67));
            HighTemperature.Add (new ChartDataPoint ("Nov", 55));
            HighTemperature.Add (new ChartDataPoint ("Dec", 45));

        }

   }



Now, you can add the series into the chart and set its ItemsSource as shown below



[C#]  

_//Adding the series to the chart_
  chart.Series.Add (new ColumnSeries () {
                ItemsSource = dataModel.HighTemperature
            }); 



[XAML] 

  &lt;chart:SfChart&gt;

   …

    &lt;chart:SfChart.Series&gt;

      <chart:ColumnSeries 

           ItemsSource = "{Binding HighTemperature}"/>

    &lt;/chart:SfChart.Series&gt;



  &lt;/chart:SfChart&gt;

Adding Legends

Legends can be enabled in SfChart by initializing the Legend property with ChartLegend instance as follows.



[C#] 

_//Adding Legend_ 
 chart.Legend = new ChartLegend (); 



[XAML] 

&lt;chart:SfChart&gt;



    &lt;chart:SfChart.Legend&gt;

      &lt;chart:ChartLegend/&gt;

    &lt;/chart:SfChart.Legend&gt;

    …

 &lt;/chart:SfChart&gt;



Circular legend icons will be displayed for each series by default. Next, we need to provide the labels for the series using the Label property, this information is displayed along the legend icon.

The next step is to add the HighTemperature column series as shown below



[C#]

_//Adding the column series to the chart_
chart.Series.Add (new ColumnSeries () {
        ItemsSource = dataModel.HighTemperature,
        Label = "Series 1"
});



[XAML]

&lt;chart:SfChart&gt;

    …

    &lt;chart:SfChart.Series&gt;

      &lt;chart:ColumnSeries Label = "Series 1" ItemsSource = "{Binding HighTemperature}"/&gt;

    &lt;/chart:SfChart.Series&gt;



  &lt;/chart:SfChart&gt;

Add multiple series to the chart

So far we have visualized just the high temperature data over time. Now let’s visualize other data such as low temperature and precipitation.

Let’s add two SplineSeries for displaying high and low temperatures and a ColumnSeries for displaying the precipitation as shown below



[C#]           

     DataModel dataModel = new DataModel ();

_//Adding ColumnSeries to the chart for displaying Precipitation_
     chart.Series.Add (new ColumnSeries () {
     ItemsSource = dataModel.Precipitation,
     Label = "Precipitation"
     });

_//Adding the SplineSeries to the chart for displaying  high temperature_
     chart.Series.Add (new SplineSeries () {
     ItemsSource = dataModel.HighTemperature,
     Label = "High"
     });

_//Adding the SplineSeries to the chart for displaying  low temperature_
     chart.Series.Add (new SplineSeries () {
     ItemsSource = dataModel.LowTemperature,
     Label = "Low"
     });



[XAML]   

  &lt;chart:SfChart&gt;



…



    &lt;chart:SfChart.Series&gt;



      &lt;chart:ColumnSeries   Label = "Low" ItemsSource = "{Binding Precipitation}"/&gt;



      &lt;chart:SplineSeries  Label = "High" ItemsSource = "{Binding HighTemperature}"/&gt;



      &lt;chart:SplineSeries  Label = "Low" ItemsSource = "{Binding LowTemperature}"/&gt;



    &lt;/chart:SfChart.Series&gt;



  &lt;/chart:SfChart&gt;


Currently all the data is plotted against a single scale but the precipitation data needs to be plotted against a different scale.

Add multiple Y-axis

Let’s add a secondary axis(y axis) to the chart as shown below

[C#] 

_//Adding ColumnSeries to the chart for displaying  Precipitation_
            chart.Series.Add (new ColumnSeries () {
                ItemsSource = dataModel.Precipitation,
                Label = "Precipitation",
                YAxis = new NumericalAxis(){ OpposedPosition = true }

             );



[XAML]

  &lt;chart:SfChart&gt;

…

      &lt;chart:ColumnSeries   Label = "Low" ItemsSource = "{Binding Precipitation}"&gt;

        &lt;chart:ColumnSeries.YAxis&gt;

          &lt;chart:NumericalAxis OpposedPosition ="true"/&gt;

        &lt;/chart:ColumnSeries.YAxis&gt;

      &lt;/chart:ColumnSeries&gt;

…

  &lt;/chart:SfChart&gt;


The OpposedPosition has been set to true to place the secondary axis on the opposite side.

Here is the complete code sample for creating the Chart.

[C#]    

    public class WeatherChartDemo : ContentPage
    {

        public WeatherChartDemo ()
        {

_//Initializing chart_
            SfChart chart = new SfChart ();
            chart.Title = new ChartTitle (){ Text = "Weather Analysis" };

_//Initializing Primary Axis_
            CategoryAxis primaryAxis = new CategoryAxis ();
            primaryAxis.Title = new ChartAxisTitle (){ Text = "Month" };

            chart.PrimaryAxis = primaryAxis;

_//Initializing Secondary Axis_
            NumericalAxis secondaryAxis = new NumericalAxis ();
            secondaryAxis.Title = new ChartAxisTitle (){ Text = "Temperature" };

            chart.SecondaryAxis = secondaryAxis;


            DataModel dataModel = new DataModel ();

_//Adding ColumnSeries to the chart for displaying  Precipitation_
            chart.Series.Add (new ColumnSeries () {
                ItemsSource = dataModel.Precipitation,
                Label = "Precipitation",
                YAxis = new NumericalAxis(){ OpposedPosition = true, 

                                ShowMajorGridLines =  false }
            });

_//Adding the SplineSeries to the chart for displaying high temperature_
            chart.Series.Add (new SplineSeries () {
                ItemsSource = dataModel.HighTemperature,
                Label = "High"
            });

_//Adding the SplineSeries to the chart for displaying low temperature_
            chart.Series.Add (new SplineSeries () {
                ItemsSource = dataModel.LowTemperature,
                Label = "Low"
            });

_//Adding Chart Legend for the Chart_
            chart.Legend = new ChartLegend ();

            this.Content = chart;
        }

    }

    public class DataModel
    {
        public ObservableCollection<ChartDataPoint>  HighTemperature  { get; set; }

        public ObservableCollection<ChartDataPoint>  LowTemperature { get; set; }

        public ObservableCollection<ChartDataPoint>  Precipitation { get; set; }

        public DataModel ()
        {
            HighTemperature = new ObservableCollection<ChartDataPoint> ();

            HighTemperature.Add (new ChartDataPoint ("Jan", 42));
            HighTemperature.Add (new ChartDataPoint ("Feb", 44));
            HighTemperature.Add (new ChartDataPoint ("Mar", 53));
            HighTemperature.Add (new ChartDataPoint ("Apr", 64));
            HighTemperature.Add (new ChartDataPoint ("May", 75));
            HighTemperature.Add (new ChartDataPoint ("Jun", 83));
            HighTemperature.Add (new ChartDataPoint ("Jul", 87));
            HighTemperature.Add (new ChartDataPoint ("Aug", 84));
            HighTemperature.Add (new ChartDataPoint ("Sep", 78));
            HighTemperature.Add (new ChartDataPoint ("Oct", 67));
            HighTemperature.Add (new ChartDataPoint ("Nov", 55));
            HighTemperature.Add (new ChartDataPoint ("Dec", 45));

            LowTemperature = new ObservableCollection<ChartDataPoint> ();

            LowTemperature.Add (new ChartDataPoint ("Jan", 27));
            LowTemperature.Add (new ChartDataPoint ("Feb", 28));
            LowTemperature.Add (new ChartDataPoint ("Mar", 35));
            LowTemperature.Add (new ChartDataPoint ("Apr", 44));
            LowTemperature.Add (new ChartDataPoint ("May", 54));
            LowTemperature.Add (new ChartDataPoint ("Jun", 63));
            LowTemperature.Add (new ChartDataPoint ("Jul", 68));
            LowTemperature.Add (new ChartDataPoint ("Aug", 66));
            LowTemperature.Add (new ChartDataPoint ("Sep", 59));
            LowTemperature.Add (new ChartDataPoint ("Oct", 48));
            LowTemperature.Add (new ChartDataPoint ("Nov", 38));
            LowTemperature.Add (new ChartDataPoint ("Dec", 29));

            Precipitation = new ObservableCollection<ChartDataPoint> ();

            Precipitation.Add (new ChartDataPoint ("Jan", 3.03));
            Precipitation.Add (new ChartDataPoint ("Feb", 2.48));
            Precipitation.Add (new ChartDataPoint ("Mar", 3.23));
            Precipitation.Add (new ChartDataPoint ("Apr", 3.15));
            Precipitation.Add (new ChartDataPoint ("May", 4.13));
            Precipitation.Add (new ChartDataPoint ("Jun", 3.23));
            Precipitation.Add (new ChartDataPoint ("Jul", 4.13));
            Precipitation.Add (new ChartDataPoint ("Aug", 4.88));
            Precipitation.Add (new ChartDataPoint ("Sep", 3.82));
            Precipitation.Add (new ChartDataPoint ("Oct", 3.07));
            Precipitation.Add (new ChartDataPoint ("Nov", 2.83));
            Precipitation.Add (new ChartDataPoint ("Dec", 2.8));
        }
    }



[XAML]

&lt;chart:SfChart&gt;



    &lt;chart:SfChart.Legend&gt;

      &lt;chart:ChartLegend/&gt;

    &lt;/chart:SfChart.Legend&gt;



    &lt;chart:SfChart.Title&gt;

      &lt;chart:ChartTitle Text="Weather Analysis"/&gt;

    &lt;/chart:SfChart.Title&gt;



    &lt;chart:SfChart.PrimaryAxis&gt;

      &lt;chart:CategoryAxis&gt;

        &lt;chart:CategoryAxis.Title&gt;

          &lt;chart:ChartAxisTitle Text="Month"/&gt;

        &lt;/chart:CategoryAxis.Title&gt;

      &lt;/chart:CategoryAxis&gt;

    &lt;/chart:SfChart.PrimaryAxis&gt;



    &lt;chart:SfChart.SecondaryAxis&gt;

      &lt;chart:NumericalAxis&gt;

        &lt;chart:NumericalAxis.Title&gt;

          &lt;chart:ChartAxisTitle Text="Month"/&gt;

        &lt;/chart:NumericalAxis.Title&gt;

      &lt;/chart:NumericalAxis&gt;

    &lt;/chart:SfChart.SecondaryAxis&gt;



    &lt;chart:SfChart.Series&gt;



      &lt;chart:ColumnSeries   Label = "Low" ItemsSource = "{Binding Precipitation}"&gt;

        &lt;chart:ColumnSeries.YAxis&gt;

          &lt;chart:NumericalAxis OpposedPosition="true" ShowMajorGridLines="false"/&gt;

        &lt;/chart:ColumnSeries.YAxis&gt;

      &lt;/chart:ColumnSeries&gt;



      &lt;chart:SplineSeries  Label = "High" ItemsSource = "{Binding HighTemperature}"/&gt;



      &lt;chart:SplineSeries  Label = "Low" ItemsSource = "{Binding LowTemperature}"/&gt;



    &lt;/chart:SfChart.Series&gt;



  &lt;/chart:SfChart&gt;

![](Getting-Started_images/Getting-Started_img3.png)
{:.image }


