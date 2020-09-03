---
layout: post
title: Animation feature of Syncfusion Xamarin.Forms SfSunburstChart
description: This section describes the animation feature of sunburst chart.
platform: xamarin
control: SfSunburstChart
documentation: ug
---

# Animation

The sunburst chart provides animation on loading and whenever the item source changes. Animation can be enabled by setting the [`EnableAnimation`](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfSunburstChart.XForms.SfSunburstChart.html#Syncfusion_SfSunburstChart_XForms_SfSunburstChart_EnableAnimation) property to true.

The following code shows enabling animation.

{% tabs %} 

{% highlight xaml %}

  <sunburst:SfSunburstChart x:Name="sunburstChart" ItemsSource="{Binding DataSource}" 
                                  ValueMemberPath="EmployeesCount"  EnableAnimation="True">              
               
  </sunburst:SfSunburstChart>

{% endhighlight %}

{% highlight C# %}

  SfSunburstChart sunburstChart = new SfSunburstChart();
  sunburstChart.SetBinding(SfSunburstChart.ItemsSourceProperty, "DataSource");
  sunburstChart.ValueMemberPath = "EmployeesCount";

  sunburstChart.EnableAnimation = true;
                       
  this.Content = sunburstChart;

{% endhighlight %}

{% endtabs %} 

## Duration

Animation duration can be controlled using the [`AnimationDuration`](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfSunburstChart.XForms.SfSunburstChart.html#Syncfusion_SfSunburstChart_XForms_SfSunburstChart_AnimationDuration) property.

{% tabs %} 

{% highlight xaml %}

  <sunburst:SfSunburstChart x:Name="sunburstChart" ItemsSource="{Binding DataSource}" AnimationDuration="2"
                                  ValueMemberPath="EmployeesCount"  EnableAnimation="True">
  </sunburst:SfSunburstChart>

{% endhighlight %}

{% highlight C# %}

  SfSunburstChart sunburstChart = new SfSunburstChart();
  sunburstChart.SetBinding(SfSunburstChart.ItemsSourceProperty, "DataSource");
  sunburstChart.ValueMemberPath = "EmployeesCount";

  sunburstChart.EnableAnimation = true;
  sunburstChart.AnimationDuration = 2;           

  this.Content = sunburstChart;

{% endhighlight %}

{% endtabs %} 

Below snippet is the complete code for generating the following output.

{% tabs %} 

{% highlight xaml %}

  <sunburst:SfSunburstChart x:Name="sunburstChart" ItemsSource="{Binding DataSource}" AnimationDuration="2"
                                  ValueMemberPath="EmployeesCount"  EnableAnimation="True">

         <sunburst:SfSunburstChart.Levels>
            <sunburst:SunburstHierarchicalLevel GroupMemberPath="Country"/>
            <sunburst:SunburstHierarchicalLevel GroupMemberPath="JobDescription"/>
            <sunburst:SunburstHierarchicalLevel GroupMemberPath="JobGroup"/>
            <sunburst:SunburstHierarchicalLevel GroupMemberPath="JobRole"/>
        </sunburst:SfSunburstChart.Levels>

        <sunburst:SfSunburstChart.DataLabel>
            <sunburst:SunburstChartDataLabel x:Name="dataLabel" ShowLabel="True"></sunburst:SunburstChartDataLabel>
        </sunburst:SfSunburstChart.DataLabel>
                
  </sunburst:SfSunburstChart>

{% endhighlight %}

{% highlight C# %}

  SfSunburstChart sunburstChart = new SfSunburstChart();
  sunburstChart.SetBinding(SfSunburstChart.ItemsSourceProperty, "DataSource");
  sunburstChart.ValueMemberPath = "EmployeesCount";

  sunburstChart.EnableAnimation = true;
  sunburstChart.AnimationDuration = 2;

  sunburstChart.Levels.Add(new SunburstHierarchicalLevel() { GroupMemberPath = "Country" });
  sunburstChart.Levels.Add(new SunburstHierarchicalLevel() { GroupMemberPath = "JobDescription" });
  sunburstChart.Levels.Add(new SunburstHierarchicalLevel() { GroupMemberPath = "JobGroup" });
  sunburstChart.Levels.Add(new SunburstHierarchicalLevel() { GroupMemberPath = "JobRole" });

  SunburstChartDataLabel label = new SunburstChartDataLabel();
  label.ShowLabel = true;
  sunburstChart.DataLabel = label;

  this.Content = sunburstChart;

{% endhighlight %}

{% endtabs %} 


The following screenshot depicts animation of the sunburst chart with the specified duration.

![Animation support in Xamarin.Forms Sunburst](Animation_images/Animate.gif)

