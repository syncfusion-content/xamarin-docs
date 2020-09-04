---
layout: post
title:  Legends of Syncfusion Xamarin.Forms SfSunburstChart
description: This section describes the legend and its customization.
platform: xamarin
control: SfSunburstChart
documentation: ug
---

# Legend

Legends are used to represent the first level (i.e root level) of categories in the sunburst chart.

The following code explains how to initialize the legends.

{% tabs %} 

{% highlight xaml %}

  <sunburst:SfSunburstChart.Legend>
      <sunburst:SunburstChartLegend>
      </sunburst:SunburstChartLegend>
  </sunburst:SfSunburstChart.Legend>

{% endhighlight %}

{% highlight C# %}

  SunburstChartLegend legend = new SunburstChartLegend();
  sunburstChart.Legend = legend;

{% endhighlight %}

{% endtabs %} 

## Visibility

The visibility of legends can be controlled using the [`IsVisible`](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfSunburstChart.XForms.SunburstChartLegend.html#Syncfusion_SfSunburstChart_XForms_SunburstChartLegend_IsVisible) property.

The following code shows how to control the visibility of legend.

{% tabs %} 

{% highlight xaml %}

  <sunburst:SfSunburstChart.Legend>
       <sunburst:SunburstChartLegend IsVisible="True" >
       </sunburst:SunburstChartLegend>
  </sunburst:SfSunburstChart.Legend>

{% endhighlight %}

{% highlight C# %}

  SunburstChartLegend legend = new SunburstChartLegend();
  legend.IsVisible = true;
  sunburstChart.Legend = legend;

{% endhighlight %}

{% endtabs %} 

![Legend visibility support in Xamarin.Forms Sunburst](Legend_images/Legend.jpg)

## Position

Legends can be docked at the top, right, left, or bottom position using the [`LegendPosition`](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfSunburstChart.XForms.SunburstChartLegend.html#Syncfusion_SfSunburstChart_XForms_SunburstChartLegend_LegendPosition) property.

The following code shows customizing the legend position.

{% tabs %} 

{% highlight xaml %}

  <sunburst:SfSunburstChart.Legend>
       <sunburst:SunburstChartLegend x:Name="legend" IsVisible="True"  
                      LegendPosition="Left" >
       </sunburst:SunburstChartLegend>
  </sunburst:SfSunburstChart.Legend>

{% endhighlight %}

{% highlight C# %}

  SunburstChartLegend legend = new SunburstChartLegend();
  legend.IsVisible = true;
  legend.LegendPosition = SunburstDockPosition.Left;
  sunburstChart.Legend = legend;

{% endhighlight %}

{% endtabs %} 

![Legend position support in Xamarin.Forms Sunburst](Legend_images/LegendPosition.jpg)

## Legend icon types

Legend icon shapes can be customized using the [`IconType`](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfSunburstChart.XForms.SunburstChartLegend.html#Syncfusion_SfSunburstChart_XForms_SunburstChartLegend_IconType) property. The IconType property provides several predefined shapes. The default legend icon type is circle.

The following predefined shapes are available in the IconType property:

* Circle
* Cross
* Diamond
* Pentagon
* Rectangle
* Triangle.

{% tabs %} 

{% highlight xaml %}

  <sunburst:SfSunburstChart.Legend>
    <sunburst:SunburstChartLegend x:Name="legend" IsVisible="True"  
                         IconType="Diamond" >
    </sunburst:SunburstChartLegend>
  </sunburst:SfSunburstChart.Legend>


{% endhighlight %}

{% highlight C# %}

  SunburstChartLegend legend = new SunburstChartLegend();
  legend.IsVisible = true;
  legend.IconType = SunburstLegendIcon.Diamond;
  sunburstChart.Legend = legend;

{% endhighlight %}

{% endtabs %} 

![Legend icon types support in Xamarin.Forms Sunburst](Legend_images/IconType.jpg)

## Icon size customization

The size of the legend icon can be customized using the [`IconHeight`](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfSunburstChart.XForms.SunburstChartLegend.html#Syncfusion_SfSunburstChart_XForms_SunburstChartLegend_IconHeight) and [`IconWidth`](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfSunburstChart.XForms.SunburstChartLegend.html#Syncfusion_SfSunburstChart_XForms_SunburstChartLegend_IconWidth) properties.

{% tabs %} 

{% highlight xaml %}

  <sunburst:SfSunburstChart.Legend>
     <sunburst:SunburstChartLegend x:Name="legend" IsVisible="True" IconHeight="15" 
                   IconWidth="15" IconType="Diamond">
     </sunburst:SunburstChartLegend>
  </sunburst:SfSunburstChart.Legend>

{% endhighlight %}

{% highlight C# %}

  SunburstChartLegend legend = new SunburstChartLegend();
  legend.IsVisible = true;
  legend.IconType = SunburstLegendIcon.Diamond;
  legend.IconHeight = 15;
  legend.IconWidth = 15;
  sunburstChart.Legend = legend;

{% endhighlight %}

{% endtabs %} 

![Legend icon size customization support in Xamarin.Forms Sunburst](Legend_images/IconSize.jpg)

## Label style

Legend label can be customized using the following properties available in [`LabelStyle`](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfSunburstChart.XForms.SunburstChartLegend.html#Syncfusion_SfSunburstChart_XForms_SunburstChartLegend_LabelStyle):

* [`TextColor`](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfSunburstChart.XForms.SunburstLegendLabelStyle.html#Syncfusion_SfSunburstChart_XForms_SunburstLegendLabelStyle_TextColor): Customizes the text color of the label.
* [`FontSize`](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfSunburstChart.XForms.SunburstLegendLabelStyle.html#Syncfusion_SfSunburstChart_XForms_SunburstLegendLabelStyle_FontSize): Customizes the font size of the label.
* [`FontAttributes`](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfSunburstChart.XForms.SunburstLegendLabelStyle.html#Syncfusion_SfSunburstChart_XForms_SunburstLegendLabelStyle_FontAttributes): Customizes the font attributes such as Bold or Italic.
* [`Margin`](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfSunburstChart.XForms.SunburstLegendLabelStyle.html#Syncfusion_SfSunburstChart_XForms_SunburstLegendLabelStyle_Margin): Sets the specified margin for legend labels.
* [`FontFamily`](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfSunburstChart.XForms.SunburstLegendLabelStyle.html#Syncfusion_SfSunburstChart_XForms_SunburstLegendLabelStyle_FontFamily): Sets the specified font family for labels.


{% tabs %} 

{% highlight xaml %}

  <sunburst:SfSunburstChart.Legend>
     <sunburst:SunburstChartLegend x:Name="legend" IsVisible="True" > 
                                                  
       <sunburst:SunburstChartLegend.LabelStyle>
            <sunburst:SunburstLegendLabelStyle x:Name="legendStyle" 
                         FontAttributes="Italic" FontSize="14" Margin="5"
                         TextColor="Red" ></sunburst:SunburstLegendLabelStyle>
       </sunburst:SunburstChartLegend.LabelStyle>

   </sunburst:SunburstChartLegend>
  </sunburst:SfSunburstChart.Legend>

{% endhighlight %}

{% highlight C# %}

  sunburstChart.Legend = new SunburstChartLegend();
  sunburstChart.Legend.IsVisible = true;

  SunburstLegendLabelStyle labelStyle = new SunburstLegendLabelStyle();
  labelStyle.FontAttributes = FontAttributes.Italic;
  labelStyle.FontSize = 14;
  labelStyle.TextColor = Color.Red;
  labelStyle.Margin = new Thickness(5);

  sunburstChart.Legend.LabelStyle = labelStyle;

{% endhighlight %}

{% endtabs %} 

![Customize label support in Xamarin.Forms Sunburst](Legend_images/LabelStyle.png)


## Item margin

Margin can be set to individual legend items using the [`ItemMargin`](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfSunburstChart.XForms.SunburstChartLegend.html#Syncfusion_SfSunburstChart_XForms_SunburstChartLegend_ItemMargin) property.

{% tabs %} 

{% highlight xaml %}

  <sunburst:SfSunburstChart.Legend>
         <sunburst:SunburstChartLegend x:Name="legend" IsVisible="True" ItemMargin="3" >                    
         </sunburst:SunburstChartLegend>
  </sunburst:SfSunburstChart.Legend>

{% endhighlight %}

{% highlight C# %}

  SunburstChartLegend legend = new SunburstChartLegend();
  legend.IsVisible = true;
  legend.ItemMargin = new Thickness(3, 3, 3, 3);                    
  sunburstChart.Legend = legend;

{% endhighlight %}

{% endtabs %} 

![Legend item margin support in Xamarin.Forms Sunburst](Legend_images/ItemMargin.png)

## Toggle selection

Sunburst segments can also be selected via legends.

{% tabs %} 

{% highlight xaml %}

  <sunburst:SfSunburstChart.Legend>
       <sunburst:SunburstChartLegend x:Name="legend" IsVisible="True"  >                    
       </sunburst:SunburstChartLegend>
  </sunburst:SfSunburstChart.Legend>

  <sunburst:SfSunburstChart.SelectionSettings>
       <sunburst:SelectionSettings   EnableSelection="True" SelectionDisplayMode="HighlightByStrokeColor">
       </sunburst:SelectionSettings>
  </sunburst:SfSunburstChart.SelectionSettings>


{% endhighlight %}

{% highlight C# %}

  SunburstChartLegend legend = new SunburstChartLegend();
  legend.IsVisible = true;                           
  sunburstChart.Legend = legend;

  SelectionSettings selection = new SelectionSettings();
  selection.EnableSelection = true;
  selection.SelectionDisplayMode = SelectionDisplayMode.HighlightByStrokeColor;           
  sunburstChart.SelectionSettings = selection;

{% endhighlight %}

{% endtabs %} 

![Toggle selection support in Xamarin.Forms Sunburst](Legend_images/LegendSelection.png)