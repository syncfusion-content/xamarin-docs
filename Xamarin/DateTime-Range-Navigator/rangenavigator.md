---
layout: post
title: Getting Started in Xamarin DateTime Range Navigator | Syncfusion
description: Learn here all about Getting Started support in Syncfusion® Xamarin DateTime Range Navigator (SfDateTimeRangeNavigator) control and more.
platform: xamarin
control: SfDateTimeRangeNavigator
documentation: ug
---

# Getting Started in Xamarin DateTime Range Navigator

This section walks you through the steps required to add [`SfDateTimeRangeNavigator`](https://help.syncfusion.com/cr/xamarin/Syncfusion.RangeNavigator.XForms.SfDateTimeRangeNavigator.html) and populate it with data, and also explains how to respond to range selection performed in the control. 

## Assembly deployment

After installing [Essential Studio® for Xamarin](https://www.syncfusion.com/downloads/xamarin), you can find all the required assemblies in the installation folders, {Syncfusion Essential Studio Installed location} \Essential Studio\\{Version #}\Xamarin\lib.

E.g.: C:\Program Files (x86) \Syncfusion\Essential Studio\19.1.0.54\Xamarin\lib

N> Assemblies can be found in unzipped package location(Documents/Syncfusion/{Version #}/Xamarin/lib) in Mac.

## Adding SfDateTimeRangeNavigator reference

You can add SfDateTimeRangeNavigator reference in one of the following methods:

**Method 1: Adding SfDateTimeRangeNavigator reference from nuget.org**

Syncfusion® Xamarin components are available in [nuget.org](https://www.nuget.org/). To add SfDateTimeRangeNavigator to your project, open the NuGet package manager in Visual Studio, search for [Syncfusion.Xamarin.SfChart](https://www.nuget.org/packages/Syncfusion.Xamarin.SfChart/), and then install it.

![Adding Xamarin.Forms date-time range navigator reference](gettingstarted_images/img3.png)

N> Install the same version of the SfChart NuGet in all the projects.

**Method 2: Adding SfDateTimeRangeNavigator reference from toolbox**

Syncfusion® also provides Xamarin Toolbox. Using this toolbox, you can drag the SfDateTimeRangeNavigator control to the XAML page. It will automatically install the required NuGet packages and add the namespace to the page. To install Syncfusion® Xamarin Toolbox, refer to [Toolbox](https://help.syncfusion.com/xamarin/utility#toolbox).

**Method 3: Adding SfDateTimeRangeNavigator assemblies manually from the installed location**

If you prefer to manually reference the assemblies instead referencing from NuGet, add the following assemblies in respective projects.

Location : {Installed location}/{version}/Xamarin/lib

<table>
<tr>
<td>
PCL
</td>
<td>
Syncfusion.SfChart.XForms.dll<br/>
Syncfusion.Core.XForms.dll<br/>
Syncfusion.Licensing.dll<br/>
</td>
</tr>
<tr>
<td>
Android
</td>
<td>
Syncfusion.SfChart.XForms.Android.dll<br/>
Syncfusion.SfChart.XForms.dll<br/>
Syncfusion.Core.XForms.dll<br/>
Syncfusion.Core.XForms.Android.dll<br/>
Syncfusion.Licensing.dll<br/>
</td>
</tr>
<tr>
<td>
iOS
</td>
<td>
Syncfusion.SfChart.XForms.iOS.dll<br/>
Syncfusion.SfChart.XForms.dll<br/>
Syncfusion.Core.XForms.dll<br/>
Syncfusion.Core.XForms.iOS.dll<br/>
Syncfusion.Licensing.dll<br/>
</td>
</tr>
<tr>
<td>
UWP
</td>
<td>
Syncfusion.SfChart.UWP.dll<br/>
Syncfusion.SfChart.XForms.UWP.dll<br/>
Syncfusion.SfChart.XForms.dll<br/>
Syncfusion.Core.XForms.dll<br/>
Syncfusion.Core.XForms.UWP.dll<br/>
Syncfusion.Licensing.dll<br/>
</td>
</tr>
</table>

N> To know more about obtaining our components, refer to these links for [Mac](https://help.syncfusion.com/xamarin/installation/mac-installer/how-to-download) and [Windows](https://help.syncfusion.com/xamarin/installation/offline-installer/how-to-download).

I> Starting with v16.2.0.x, if you reference Syncfusion® assemblies from the trial setup or from the NuGet feed, you also have to include a license key in your projects. Please refer to [Syncfusion® license key](https://help.syncfusion.com/common/essential-studio/licensing/overview) to know about registering Syncfusion® license key in your Xamarin application to use our components.

## Launching the application on each platform with range navigator 

To use the range navigator inside an application, each platform application requires some additional configurations. The configurations vary from platform to platform and is discussed in the following sections:

N> If you are adding the references from toolbox, below steps are not needed.

### iOS

To launch the range navigator in iOS, call the SfRangeNavigatorRenderer.Init() method in the FinishedLaunching overridden method of the AppDelegate class after the Xamarin.Forms framework initialization and before the LoadApplication method is called as demonstrated in the following code sample:

{% highlight C# %} 

public override bool FinishedLaunching(UIApplication app, NSDictionary options) 
{ 
    … 
    global::Xamarin.Forms.Forms.Init();

    Syncfusion.RangeNavigator.XForms.iOS.SfRangeNavigatorRenderer.Init();     

    LoadApplication(new App()); 
    …
}

{% endhighlight %}

### Universal Windows Platform (UWP)

To launch the range navigator in UWP, call the SfRangeNavigatorRenderer.Init() method in the constructor of MainPage before the LoadApplication method is called as demonstrated in the following code sample.

{% highlight C# %} 

public MainPage() 
{ 
    … 

  Syncfusion.RangeNavigator.XForms.UWP.SfRangeNavigatorRenderer.Init(); 

  LoadApplication (new App ()); 
  … 
}

{% endhighlight %}

In addition to the above configurations, you need to initialize the control assemblies in App.xaml.cs in UWP project as shown in the below code snippets. This is required to deploy application with range navigator in `Release` mode in UWP platform.

{% highlight C# %} 

// In App.xaml.cs 
protected override void OnLaunched(LaunchActivatedEventArgs e)
{ 
   … 
   if (rootFrame == null) 
   { 
      List<Assembly> assembliesToInclude = new List<Assembly>();

      assembliesToInclude.Add(typeof(Syncfusion.RangeNavigator.XForms.UWP. SfRangeNavigatorRenderer).GetTypeInfo().Assembly);

      Xamarin.Forms.Forms.Init(e, assembliesToInclude); 
   } 
… 
}


{% endhighlight %}

### Android

The Android platform does not require any additional configuration to render the range navigator.

## Adding and configuring SfDateTimeRangeNavigator 

First, let us initialize the control with major and minor date time scales by specifying the minimum and maximum date to be visualized in the control using [`Minimum`](https://help.syncfusion.com/cr/xamarin/Syncfusion.RangeNavigator.XForms.SfDateTimeRangeNavigator.html#Syncfusion_RangeNavigator_XForms_SfDateTimeRangeNavigator_Minimum) and [`Maximum`](https://help.syncfusion.com/cr/xamarin/Syncfusion.RangeNavigator.XForms.SfDateTimeRangeNavigator.html#Syncfusion_RangeNavigator_XForms_SfDateTimeRangeNavigator_Maximum) properties.

Following code example illustrates this,

{% tabs %}

{% highlight xaml %}
 <rangenavigator:SfDateTimeRangeNavigator  Minimum="2015,01,01" Maximum="2016,01,01"/>
{% endhighlight %}

{% highlight c# %}
[C#]

SfDateTimeRangeNavigator rangeNavigator = new SfDateTimeRangeNavigator()
{
	Minimum = new DateTime(2015, 01, 01),
	Maximum = new DateTime(2016, 01, 01)
};

{% endhighlight %}

{% endtabs %}

![Getting started for DateTime range navigator in Xamarin.Forms](gettingstarted_images/gettingstarted_img1.jpeg)

N> If you don’t specify [`Minimum`](https://help.syncfusion.com/cr/xamarin/Syncfusion.RangeNavigator.XForms.SfDateTimeRangeNavigator.html#Syncfusion_RangeNavigator_XForms_SfDateTimeRangeNavigator_Minimum) and [`Maximum`](https://help.syncfusion.com/cr/xamarin/Syncfusion.RangeNavigator.XForms.SfDateTimeRangeNavigator.html#Syncfusion_RangeNavigator_XForms_SfDateTimeRangeNavigator_Maximum) properties, minimum and maximum dates will be chosen automatically based on the provided data using [`ItemsSource`](https://help.syncfusion.com/cr/xamarin/Syncfusion.RangeNavigator.XForms.SfDateTimeRangeNavigator.html#Syncfusion_RangeNavigator_XForms_SfDateTimeRangeNavigator_ItemsSource) property, which is explained in the next step in this section.

Next, create a data model representing the list of sample data.

{% highlight c# %}

public class DataModel
{
	public ObservableCollection<Model> DateTimeData {get; set;}
	
	public DataModel()
	{ 		
		DateTimeData = new ObservableCollection<Model>()
		{ 
			
			new Model (new DateTime(2015, 01, 01), 14), 
			new Model (new DateTime(2015, 02, 01), 54), 
			new Model (new DateTime(2015, 03, 01), 23), 
			new Model (new DateTime(2015, 04, 01), 53), 
			new Model (new DateTime(2015, 05, 01), 25), 
			new Model (new DateTime(2015, 06, 01), 32), 
			new Model (new DateTime(2015, 07, 01), 78), 
			new Model (new DateTime(2015, 08, 01), 100), 
			new Model (new DateTime(2015, 09, 01), 55), 
			new Model (new DateTime(2015, 10, 01), 38), 
			new Model (new DateTime(2015, 11, 01), 27), 
			new Model (new DateTime(2015, 12, 01), 56), 
			new Model (new DateTime(2016, 01, 01), 33) 
			
		}; 
	} 
} 

public class Model 
{ 
	public DateTime Date { get; set; } 
	
	public double Value { get; set; } 
	
	public Model(DateTime dateTime, double value) 
	{ 
		Date = dateTime;
		Value = value; 
	} 
} 

{% endhighlight %}

Then, let us populate the chart, which is displayed inside the [`SfDateTimeRangeNavigator`](https://help.syncfusion.com/cr/xamarin/Syncfusion.RangeNavigator.XForms.SfDateTimeRangeNavigator.html), by setting the above data using [`ItemsSource`](https://help.syncfusion.com/cr/xamarin/Syncfusion.RangeNavigator.XForms.SfDateTimeRangeNavigator.html#Syncfusion_RangeNavigator_XForms_SfDateTimeRangeNavigator_ItemsSource) property. And then specify the property names which contain the x and y values in the model using [`XBindingPath`](https://help.syncfusion.com/cr/xamarin/Syncfusion.RangeNavigator.XForms.SfDateTimeRangeNavigator.html#Syncfusion_RangeNavigator_XForms_SfDateTimeRangeNavigator_XBindingPath) and [`YBindingPath`](https://help.syncfusion.com/cr/xamarin/Syncfusion.RangeNavigator.XForms.SfDateTimeRangeNavigator.html#Syncfusion_RangeNavigator_XForms_SfDateTimeRangeNavigator_YBindingPath) properties.

N> By default, data is visualized using line series. You can change the chart type or add more series by accessing the SfChart instance using [`SfDateTimeRangeNavigator.Content`](https://help.syncfusion.com/cr/xamarin/Syncfusion.RangeNavigator.XForms.SfDateTimeRangeNavigator.html#Syncfusion_RangeNavigator_XForms_SfDateTimeRangeNavigator_Content) property. 

{% tabs %}

{% highlight xaml %}
 <rangenavigator:SfDateTimeRangeNavigator ItemsSource="{Binding DateTimeData}" XBindingPath="Date" YBindingPath="Value"/>
{% endhighlight %}

{% highlight c# %}
[C#]

SfDateTimeRangeNavigator rangeNavigator = new SfDateTimeRangeNavigator() 
{ 
	rangeNavigator.ItemsSource = new DataModel().DateTimeData, 
	rangeNavigator.XBindingPath = "Date", 
	rangeNavigator.YBindingPath = "Value" 
};  

{% endhighlight %}

{% endtabs %}

![Adding chart as a content of Xamarin.Forms DateTime range navigator](gettingstarted_images/gettingstarted_img2.jpeg)

## Handle range selection

In real time, other controls like chart, grid etc., are updated in response to the range selection performed in SfDateTimeRangeNavigator. You can handle the selection using [`RangeChanged`](https://help.syncfusion.com/cr/xamarin/Syncfusion.RangeNavigator.XForms.SfDateTimeRangeNavigator.html#Syncfusion_RangeNavigator_XForms_SfDateTimeRangeNavigator_RangeChanged) event and update other controls based on the selected date time or perform some other tasks using the selected data.

N> You can get the selected start and end date using [`ViewRangeStart`](https://help.syncfusion.com/cr/xamarin/Syncfusion.RangeNavigator.XForms.SfDateTimeRangeNavigator.html#Syncfusion_RangeNavigator_XForms_SfDateTimeRangeNavigator_ViewRangeStart) and [`ViewRangeEnd`](https://help.syncfusion.com/cr/xamarin/Syncfusion.RangeNavigator.XForms.SfDateTimeRangeNavigator.html#Syncfusion_RangeNavigator_XForms_SfDateTimeRangeNavigator_ViewRangeEnd) properties or get the collection of selected data using [`SelectedData`](https://help.syncfusion.com/cr/xamarin/Syncfusion.RangeNavigator.XForms.SfDateTimeRangeNavigator.html#Syncfusion_RangeNavigator_XForms_SfDateTimeRangeNavigator_SelectedData) property.

Following code example illustrates how to handle range selection and update chart's date time axis range,

{% tabs %}
{% highlight xaml %}
<ContentPage xmlns="http://xamarin.com/schemas/2014/forms"
             xmlns:x="http://schemas.microsoft.com/winfx/2009/xaml" 
			 xmlns:local="clr-namespace:GettingStartedSample.ViewModel" 
			 xmlns:rangenavigator="clr-namespace:Syncfusion.RangeNavigator.XForms;assembly=Syncfusion.SfChart.XForms" 
			 xmlns:chart="clr-namespace:Syncfusion.SfChart.XForms;assembly=Syncfusion.SfChart.XForms"
             x:Class="GettingStartedSample.MainPage">
             
  <StackLayout >
  	<chart:SfChart x:Name="chart" HorizontalOptions="FillAndExpand" 
                 VerticalOptions="FillAndExpand">

    	<chart:SfChart.BindingContext>
      	<local:ViewModel />
    	</chart:SfChart.BindingContext>

    	<chart:SfChart.PrimaryAxis>
      	<chart:DateTimeAxis x:Name="dateTimeAxis" Minimum="5/1/2015" Maximum="8/1/2015">
        	<chart:DateTimeAxis.LabelStyle>
          	<chart:ChartAxisLabelStyle LabelFormat="MMM/dd"/>
        	</chart:DateTimeAxis.LabelStyle>
      	</chart:DateTimeAxis>
    	</chart:SfChart.PrimaryAxis>

    	<chart:SfChart.SecondaryAxis>
      	<chart:NumericalAxis/>
    	</chart:SfChart.SecondaryAxis>

    	<chart:SfChart.Series>
      	<chart:SplineAreaSeries x:Name="series" ItemsSource="{Binding DateTimeRangeData}"
        	XBindingPath="XValue" YBindingPath="YValue"/>
    	</chart:SfChart.Series>
  	</chart:SfChart>

  	<rangenavigator:SfDateTimeRangeNavigator x:Name="RangeNavigator" RangeChanged="rangeNavigator_RangeChanged" 
  	HorizontalOptions="FillAndExpand" ViewRangeStart="5/1/2015" ViewRangeEnd ="8/1/2015" ItemsSource="{Binding DateTimeRangeData}"
    XBindingPath="XValue" YBindingPath="YValue" HeightRequest = "200">
    	<rangenavigator:SfDateTimeRangeNavigator.BindingContext>
            <local:ViewModel />
    	</rangenavigator:SfDateTimeRangeNavigator.BindingContext>
  	</rangenavigator:SfDateTimeRangeNavigator>
  	
	</StackLayout>
</ContentPage>

{% endhighlight %}

{% highlight c# %}
using Syncfusion.RangeNavigator.XForms;
using Syncfusion.SfChart.XForms;

namespace GettingStartedSample
{
  public partial class MainPage : ContentPage
  {
    public MainPage()
    {
        InitializeComponent();

		StackLayout stackLayout = new StackLayout();

		viewModel = new ViewModel();
		SfChart chart = new SfChart();
		chart.HorizontalOptions = LayoutOptions.FillAndExpand;
		chart.VerticalOptions = LayoutOptions.FillAndExpand;

		DateTimeAxis dateTimeAxis = new DateTimeAxis();
		dateTimeAxis.Minimum = new DateTime(2015, 5, 1);
		dateTimeAxis.Maximum = new DateTime(2015, 8, 1);
		dateTimeAxis.LabelStyle = new ChartAxisLabelStyle { LabelFormat = "MMM/dd" };
		chart.PrimaryAxis = dateTimeAxis;

		NumericalAxis secondaryAxis = new NumericalAxis();
		chart.SecondaryAxis = secondaryAxis;

		SplineAreaSeries series = new SplineAreaSeries();
		series.ItemsSource = viewModel.DateTimeRangeData;
		series.XBindingPath = "XValue";
		series.YBindingPath = "YValue";

		chart.Series.Add(series);

		SfDateTimeRangeNavigator rangeNavigator = new SfDateTimeRangeNavigator();
		rangeNavigator.ItemsSource = viewModel.DateTimeRangeData;
		rangeNavigator.XBindingPath = "XValue";
		rangeNavigator.YBindingPath = "YValue";
		rangeNavigator.ViewRangeStart = new DateTime(2015, 5, 1);
		rangeNavigator.ViewRangeEnd = new DateTime(2015, 8, 1);
		rangeNavigator.RangeChanged += rangeNavigator_RangeChanged;
		rangeNavigator.HeightRequest = 200;
 		rangeNavigator.Content = chart;

		stackLayout.Children.Add(chart);
		stackLayout.Children.Add(rangeNavigator);
		this.Content = stackLayout;
	}
		
	private void rangeNavigator_RangeChanged(object sender, Syncfusion.RangeNavigator.XForms.RangeChangedEventArgs e)
	{
  		dateTimeAxis.Minimum = e.ViewRangeStartDate;
  		dateTimeAxis.Maximum = e.ViewRangeEndDate;  
	}
  }
}

{% endhighlight %}

{% endtabs %}

You can find the complete getting started sample from this [link.](https://github.com/SyncfusionExamples/Getting_started_of_SfDateTimeRangeNavigator_in_Xamarin.Forms)

![Range selection in Xamarin.Forms DateTime range navigator](gettingstarted_images/gettingstarted_img3.jpeg)
