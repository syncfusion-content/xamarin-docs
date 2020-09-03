---
layout: post
title: Setting SfChart as content of SfDateTimeRangeNavigator
description: Content
platform: xamarin
control: SfDateTimeRangeNavigator
documentation: ug
---

# Content

[`SfDateTimeRangeNavigator`](https://help.syncfusion.com/cr/xamarin/Syncfusion.RangeNavigator.XForms.SfDateTimeRangeNavigator.html) allows you to set `SfChart` as its content, explicitly, using [`Content`](https://help.syncfusion.com/cr/xamarin/Syncfusion.RangeNavigator.XForms.SfDateTimeRangeNavigator.html#Syncfusion_RangeNavigator_XForms_SfDateTimeRangeNavigator_Content) property. However, if you provide data source using [`ItemsSource`](https://help.syncfusion.com/cr/xamarin/Syncfusion.RangeNavigator.XForms.SfDateTimeRangeNavigator.html#Syncfusion_RangeNavigator_XForms_SfDateTimeRangeNavigator_ItemsSource) property, the Chart with line series will be created for the provided ItemsSource and will be set as the content of range navigator internally, by default. But, if you configure the range navigator using [`Minimum`](https://help.syncfusion.com/cr/xamarin/Syncfusion.RangeNavigator.XForms.SfDateTimeRangeNavigator.html#Syncfusion_RangeNavigator_XForms_SfDateTimeRangeNavigator_Minimum) and [`Maximum`](https://help.syncfusion.com/cr/xamarin/Syncfusion.RangeNavigator.XForms.SfDateTimeRangeNavigator.html#Syncfusion_RangeNavigator_XForms_SfDateTimeRangeNavigator_Maximum) properties, you have to manually configure the Chart with data source.

N> Though the [`Content`](https://help.syncfusion.com/cr/xamarin/Syncfusion.RangeNavigator.XForms.SfDateTimeRangeNavigator.html#Syncfusion_RangeNavigator_XForms_SfDateTimeRangeNavigator_Content) property’s data type is View and it can accept any View as its value, but currently [`SfDateTimeRangeNavigator`](https://help.syncfusion.com/cr/xamarin/Syncfusion.RangeNavigator.XForms.SfDateTimeRangeNavigator.html) can accept only SfChart as its content.

The following code snippet shows how to configure the range navigator using [`ItemsSource`](https://help.syncfusion.com/cr/xamarin/Syncfusion.RangeNavigator.XForms.SfDateTimeRangeNavigator.html#Syncfusion_RangeNavigator_XForms_SfDateTimeRangeNavigator_ItemsSource) property.

{% tabs %}
{% highlight xaml %}
Namespace:

 xmlns:rangenavigator="clr-namespace:Syncfusion.RangeNavigator.XForms;assembly=Syncfusion.SfChart.XForms"
 
 ...
<rangenavigator:SfDateTimeRangeNavigator ItemsSource="{Binding DateTimeRangeData}" XBindingPath="XValue" YBindingPath="YValue"/>
{% endhighlight %}

{% highlight c# %}
Namespace:

using Syncfusion.RangeNavigator.XForms;
...

SfDateTimeRangeNavigator rangeNavigator = new SfDateTimeRangeNavigator(); 

ViewModel viewModel = new ViewModel(); 

rangeNavigator.ItemsSource = viewModel.DateTimeRangeData;

rangeNavigator.XBindingPath = "XValue"; 

rangeNavigator.YBindingPath = "YValue";
{% endhighlight %}


{% endtabs %}

{% highlight c# %}

[C#]

public class ViewModel

{

	public ObservableCollection<ChartDataPoint> DateTimeRangeData { get; set; }

	public ViewModel()

	{

		DateTimeRangeData = new ObservableCollection<ChartDataPoint>

		{

			new ChartDataPoint(new DateTime(2015, 01, 1), 14),

			new ChartDataPoint(new DateTime(2015, 02, 1), 54),

			new ChartDataPoint(new DateTime(2015, 03, 1), 23),

			new ChartDataPoint(new DateTime(2015, 04, 1), 53),

			new ChartDataPoint(new DateTime(2015, 05, 1), 25),

			new ChartDataPoint(new DateTime(2015, 06, 1), 32),

			new ChartDataPoint(new DateTime(2015, 07, 1), 78),

			new ChartDataPoint(new DateTime(2015, 08, 1), 100),

			new ChartDataPoint(new DateTime(2015, 09, 1), 55),

			new ChartDataPoint(new DateTime(2015, 10, 1), 38),

			new ChartDataPoint(new DateTime(2015, 11, 1), 27),

			new ChartDataPoint(new DateTime(2015, 12, 1), 56),

			new ChartDataPoint(new DateTime(2015, 12, 31), 35),

		};

	}

}

{% endhighlight %}

The following code snippet shows how to configure the range navigator using [`Minimum`](https://help.syncfusion.com/cr/xamarin/Syncfusion.RangeNavigator.XForms.SfDateTimeRangeNavigator.html#Syncfusion_RangeNavigator_XForms_SfDateTimeRangeNavigator_Minimum) and [`Maximum`](https://help.syncfusion.com/cr/xamarin/Syncfusion.RangeNavigator.XForms.SfDateTimeRangeNavigator.html#Syncfusion_RangeNavigator_XForms_SfDateTimeRangeNavigator_Maximum) properties.

{% tabs %}
{% highlight xaml %}
Namespace:

 xmlns:rangenavigator="clr-namespace:Syncfusion.RangeNavigator.XForms;assembly=Syncfusion.SfChart.XForms"
 xmlns:chart="clr-namespace:Syncfusion.SfChart.XForms;assembly=Syncfusion.SfChart.XForms" 

 ...

<rangenavigator:SfDateTimeRangeNavigator ViewRangeStart="5/1/2015" 

	ViewRangeEnd="5/30/2015" Minimum="4/1/2015" Maximum="6/30/2015">

<rangenavigator:SfDateTimeRangeNavigator.Content>

<chart:SfChart>

. . .

</chart:SfChart>

</rangenavigator:SfDateTimeRangeNavigator.Content>
{% endhighlight %}

{% highlight c# %}
Namespace:
using Syncfusion.RangeNavigator.XForms;
using Syncfusion.SfChart.XForms;

...

SfDateTimeRangeNavigator rangeNavigator = new SfDateTimeRangeNavigator();

rangeNavigator.Minimum = new DateTime(2015, 4, 1);

rangeNavigator.Maximum = new DateTime(2015, 6, 30);

rangeNavigator.ViewRangeStart = new DateTime(2015, 5, 1);

rangeNavigator.ViewRangeEnd = new DateTime(2015, 5, 31);

SfChart chart = new SfChart();

...

rangeNavigator.Content = chart;
{% endhighlight %}
{% endtabs %}

![](content_images/content_img1.png)