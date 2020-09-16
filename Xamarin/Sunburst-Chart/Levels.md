---
layout: post
title:  Levels of Syncfusion Xamarin.Forms SfSunburstChart
description: This section describes the hierarchical levels in SfSunburstChart.
platform: xamarin
control: SfSunburstChart
documentation: ug
---

# Levels

The sunburst chart is used to display hierarchical data. More than one hierarchical data can be added to the [`Levels`](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfSunburstChart.XForms.SfSunburstChart.html#Syncfusion_SfSunburstChart_XForms_SfSunburstChart_Levels) collection of the sunburst chart. Each level of the hierarchy is represented by a circle.

The following code shows how to add hierarchical levels in the Levels collection.

{% tabs %} 

{% highlight xaml %}

  <sunburst:SfSunburstChart.Levels>
     <sunburst:SunburstHierarchicalLevel />
  </sunburst:SfSunburstChart.Levels>


{% endhighlight %}

{% highlight C# %}

  SunburstHierarchicalLevel level = new SunburstHierarchicalLevel();
  sunburstChart.Levels.Add(level);

{% endhighlight %}

{% endtabs %} 

## Group member path

The [`GroupMemberPath`](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfSunburstChart.XForms.SunburstHierarchicalLevel.html#Syncfusion_SfSunburstChart_XForms_SunburstHierarchicalLevel_GroupMemberPath) is a string property that is used to map the group category value in the sunburst [`ItemsSource`](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfSunburstChart.XForms.SfSunburstChart.html#Syncfusion_SfSunburstChart_XForms_SfSunburstChart_ItemsSource).

The following code shows how to map the group member path.

{% tabs %} 

{% highlight xaml %}

  <sunburst:SfSunburstChart.Levels>
      <sunburst:SunburstHierarchicalLevel GroupMemberPath="Level1"/>
      <sunburst:SunburstHierarchicalLevel GroupMemberPath="Level2"/>
      <sunburst:SunburstHierarchicalLevel GroupMemberPath="Level3"/>
  </sunburst:SfSunburstChart.Levels>

{% endhighlight %}

{% highlight C# %}

  SunburstHierarchicalLevel level1 = new SunburstHierarchicalLevel();
  level1.GroupMemberPath = "Level1";

  SunburstHierarchicalLevel level2 = new SunburstHierarchicalLevel();
  level2.GroupMemberPath = "Level2";

  SunburstHierarchicalLevel level3 = new SunburstHierarchicalLevel();
  level3.GroupMemberPath = "Level3";

  sunburstChart.Levels.Add(level1);
  sunburstChart.Levels.Add(level2);
  sunburstChart.Levels.Add(level3);

{% endhighlight %}

{% endtabs %} 

The following code specifies the levels for data model specified in the getting started section.

{% tabs %} 

{% highlight xaml %}

  <sunburst:SfSunburstChart x:Name="sunburstChart" ItemsSource="{Binding DataSource}"  
                ValueMemberPath="EmployeesCount">

     <sunburst:SfSunburstChart.Levels>
         <sunburst:SunburstHierarchicalLevel GroupMemberPath="Country"/>
         <sunburst:SunburstHierarchicalLevel GroupMemberPath="JobDescription"/>
         <sunburst:SunburstHierarchicalLevel GroupMemberPath="JobGroup"/>
         <sunburst:SunburstHierarchicalLevel GroupMemberPath="JobRole"/>
    </sunburst:SfSunburstChart.Levels>

  </sunburst:SfSunburstChart>

{% endhighlight %}

{% highlight C# %}

  SfSunburstChart sunburst = new SfSunburstChart();           
  sunburst.SetBinding(SfSunburstChart.ItemsSourceProperty, "DataSource");
  sunburst.ValueMemberPath = "EmployeesCount";
  sunburst.Levels.Add(new SunburstHierarchicalLevel() { GroupMemberPath = "Country" });
  sunburst.Levels.Add(new SunburstHierarchicalLevel() { GroupMemberPath = "JobDescription" });
  sunburst.Levels.Add(new SunburstHierarchicalLevel() { GroupMemberPath = "JobGroup" });
  sunburst.Levels.Add(new SunburstHierarchicalLevel() { GroupMemberPath = "JobRole" });
  this.Content = sunburstChart;

{% endhighlight %}

{% endtabs %} 

![Levels support in Xamarin.Forms Sunburst](Levels_images/Levels.png)

