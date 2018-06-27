---
layout: post
title: Drill down feature of Essential Xamarin.Forms SfSunburstChart
description: This section describes the drill down feature of sunburst chart.
platform: xamarin
control: SfSunburstChart
documentation: ug
---

# Drill-down

The drill-down provides better visualization of hierarchy. Large set of data can be virtualized into minimal views. Each level of the segments can be drilled down. The sunburst chart provides animation along with the drill-down support. Toolbar will be enabled on drill-down that helps in performing zoom back and reset operations. The drill-down can be enabled or disabled using the [`Enable`](https://help.syncfusion.com/cr/cref_files/xamarin/Syncfusion.SfSunburstChart.XForms~Syncfusion.SfSunburstChart.XForms.DrilldownSettings~Enable.html) property in the drill-down settings.

I>  Double tapping the segment performs the drill-down operation.

The following code shows enabling the [`DrilldownSettings`](https://help.syncfusion.com/cr/cref_files/xamarin/Syncfusion.SfSunburstChart.XForms~Syncfusion.SfSunburstChart.XForms.SfSunburstChart~DrilldownSettings.html).

{% tabs %} 

{% highlight xaml %}

                <sunburst:SfSunburstChart.DrilldownSettings>
                    <sunburst:DrilldownSettings Enable="True"></sunburst:DrilldownSettings>
                </sunburst:SfSunburstChart.DrilldownSettings>   


{% endhighlight %}

{% highlight C# %} 

            DrilldownSettings drilldownSettings = new DrilldownSettings();
            drilldownSettings.Enable = true;
            sunburstChart.DrilldownSettings = drilldownSettings;

{% endhighlight %}

{% endtabs %} 

![](Drilldown_images/Drilldown.gif)

## Positioning Toolbar

Toolbar can be positioned anywhere on the chart by specifying the [`OffsetX`](https://help.syncfusion.com/cr/cref_files/xamarin/Syncfusion.SfSunburstChart.XForms~Syncfusion.SfSunburstChart.XForms.DrilldownSettings~OffsetX.html) and [`OffsetY`](https://help.syncfusion.com/cr/cref_files/xamarin/Syncfusion.SfSunburstChart.XForms~Syncfusion.SfSunburstChart.XForms.DrilldownSettings~OffsetY.html) values. The offset values range from 0 to 1.

{% tabs %} 

{% highlight xaml %}

                <sunburst:SfSunburstChart.DrilldownSettings>
                    <sunburst:DrilldownSettings OffsetX="0.5" OffsetY="0" Enable="True"
                                                ></sunburst:DrilldownSettings>
                </sunburst:SfSunburstChart.DrilldownSettings>  


{% endhighlight %}

{% highlight C# %} 

            DrilldownSettings drilldownSettings = new DrilldownSettings();
            drilldownSettings.Enable = true;
            drilldownSettings.OffsetX = 0.5;
            drilldownSettings.OffsetY = 0;
            sunburstChart.DrilldownSettings = drilldownSettings;

{% endhighlight %}

{% endtabs %} 

![](Drilldown_images/Offset.png)

## Toolbar alignment 

The vertical and the horizontal alignments of the toolbar can be customized using the [`ToolbarVerticalAlignment`](https://help.syncfusion.com/cr/cref_files/xamarin/Syncfusion.SfSunburstChart.XForms~Syncfusion.SfSunburstChart.XForms.DrilldownSettings~ToolbarVerticalAlignment.html) and [`ToolbarHorizontalAlignment`](https://help.syncfusion.com/cr/cref_files/xamarin/Syncfusion.SfSunburstChart.XForms~Syncfusion.SfSunburstChart.XForms.DrilldownSettings~ToolbarHorizontalAlignment.html) properties, respectively.

Both the alignment properties has the following enum types:

* Center: Toolbar takes the specified offset value as the center of the toolbar and get positioned.
* End: Toolbar takes the specified offset value as the start of the toolbar and get positioned.
* Start: Toolbar takes the specified offset value as the end of the toolbar and get positioned.

The following code shows the toolbar alignment.

{% tabs %} 

{% highlight xaml %}

                <sunburst:SfSunburstChart.DrilldownSettings>
                    <sunburst:DrilldownSettings OffsetX="0.5" OffsetY="0.5" Enable="True" ToolbarHorizontalAlignment="Center"
                                                ToolbarVerticalAlignment="Center"
                                                ></sunburst:DrilldownSettings>
                </sunburst:SfSunburstChart.DrilldownSettings>

{% endhighlight %}

{% highlight C# %} 

            DrilldownSettings drilldownSettings = new DrilldownSettings();
            drilldownSettings.Enable = true;
            drilldownSettings.OffsetX = 0.5;
            drilldownSettings.OffsetY = 0.5;
            drilldownSettings.ToolbarHorizontalAlignment = ToolbarAlignment.Center;
            drilldownSettings.ToolbarVerticalAlignment = ToolbarAlignment.Center;
            sunburstChart.DrilldownSettings = drilldownSettings;


{% endhighlight %}

{% endtabs %} 

![](Drilldown_images/ToolbarAlignment.png)

