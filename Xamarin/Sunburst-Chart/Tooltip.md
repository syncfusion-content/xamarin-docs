---
layout: post
title: Tooltip in Syncfusion SfSunburstChart control for Xamarin.Forms
description: This section describes the tooltip feature of sunburst chart.
platform: xamarin
control: SfSunburstChart
documentation: ug
---

# Tooltip

Tooltip provides additional information about the segments in the sunburst chart. Tooltip is displayed by tapping the segment. By default, tooltip displays the corresponding segment’s category and value. To enable the tooltip, set the [`ShowTooltip`](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfSunburstChart.XForms.SunburstTooltipSettings.html#Syncfusion_SfSunburstChart_XForms_SunburstTooltipSettings_ShowTooltip) property to true.

The following code shows enabling the tooltip.

{% tabs %} 

{% highlight xaml %}

  <sunburst:SfSunburstChart.TooltipSettings>
         <sunburst:SunburstTooltipSettings ShowTooltip="True"></sunburst:SunburstTooltipSettings>
  </sunburst:SfSunburstChart.TooltipSettings>

{% endhighlight %}

{% highlight C# %}

  SunburstTooltipSettings tooltipSettings = new SunburstTooltipSettings();
  tooltipSettings.ShowTooltip = true;
  sunburstChart.TooltipSettings = tooltipSettings;

{% endhighlight %}

{% endtabs %} 

![Tooltip support in Xamarin.Forms Sunburst](Tooltip_images/Tooltip.png)

## Customization

The appearance of the tooltip can be customized using the following properties:

* [`TextColor`](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfSunburstChart.XForms.SunburstTooltipSettings.html#Syncfusion_SfSunburstChart_XForms_SunburstTooltipSettings_TextColor): Customizes the text color of the tooltip.
* [`BackgroundColor`](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfSunburstChart.XForms.SunburstTooltipSettings.html#Syncfusion_SfSunburstChart_XForms_SunburstTooltipSettings_BackgroundColor): Customizes the background color of the tooltip.
* [`BorderColor`](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfSunburstChart.XForms.SunburstTooltipSettings.html#Syncfusion_SfSunburstChart_XForms_SunburstTooltipSettings_BorderColor): Customizes the border color of the tooltip.
* [`BorderWidth`](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfSunburstChart.XForms.SunburstTooltipSettings.html#Syncfusion_SfSunburstChart_XForms_SunburstTooltipSettings_BorderWidth): Customizes the border width of the tooltip.
* [`Duration`](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfSunburstChart.XForms.SunburstTooltipSettings.html#Syncfusion_SfSunburstChart_XForms_SunburstTooltipSettings_Duration): Specifies the duration of the tooltip to be displayed.

The following code shows all the above customizations.

{% tabs %} 

{% highlight xaml %}

  <sunburst:SfSunburstChart.TooltipSettings>
        <sunburst:SunburstTooltipSettings ShowTooltip="True" TextColor="White"
         BackgroundColor="Green"  BorderColor="Black" BorderWidth="1" 
         Duration="2000" ></sunburst:SunburstTooltipSettings>
  </sunburst:SfSunburstChart.TooltipSettings>

{% endhighlight %}

{% highlight C# %}

  SunburstTooltipSettings tooltipSettings = new SunburstTooltipSettings();
  tooltipSettings.ShowTooltip = true;
  tooltipSettings.TextColor = Color.White;
  tooltipSettings.BackgroundColor = Color.Green;
  tooltipSettings.BorderColor = Color.Black;
  tooltipSettings.BorderWidth = 1;
  tooltipSettings.Duration = 2000;
  sunburstChart.TooltipSettings = tooltipSettings;

{% endhighlight %}

{% endtabs %} 

![Customize tooltip support in Xamarin.Forms Sunburst](Tooltip_images/Customization.png)

## Font customization

The font size can be customized using the [`FontSize`](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfSunburstChart.XForms.SunburstTooltipSettings.html#Syncfusion_SfSunburstChart_XForms_SunburstTooltipSettings_FontSize) property of tooltip.

{% tabs %} 

{% highlight xaml %}

<sunburst:SfSunburstChart.TooltipSettings>
            <sunburst:SunburstTooltipSettings ShowTooltip="True" FontSize="20" />
</sunburst:SfSunburstChart.TooltipSettings>

{% endhighlight %}

{% highlight C# %}

SunburstTooltipSettings tooltipSettings = new SunburstTooltipSettings();
tooltipSettings.ShowTooltip = true;
tooltipSettings.FontSize = 20;
sunburstChart.TooltipSettings = tooltipSettings;

{% endhighlight %}

{% endtabs %} 

![Font customization support in Xamarin.Forms Sunburst](Tooltip_images/font.png)

## Custom template

The sunburst chart provides options to design your own template for tooltip using the [`TooltipTemplate`](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfSunburstChart.XForms.SunburstTooltipSettings.html#Syncfusion_SfSunburstChart_XForms_SunburstTooltipSettings_TooltipTemplate) property.

{% tabs %} 

{% highlight xaml %}

  <sunburst:SfSunburstChart.TooltipSettings>
    <sunburst:SunburstTooltipSettings ShowTooltip="True">
         <sunburst:SunburstTooltipSettings.TooltipTemplate>
              <DataTemplate>
                    <StackLayout Orientation="Vertical">
                        <StackLayout Orientation="Horizontal">
                            <Label Text="Country : " TextColor="White"/>
                            <Label Text="{Binding Category}" TextColor="White"/>
                        </StackLayout>
                         <StackLayout Orientation="Horizontal">
                            <Label Text="Count   :"  TextColor="White"/>
                            <Label Text="{Binding Value}" TextColor="White"/>
                         </StackLayout>                               
                    </StackLayout>
              </DataTemplate>
         </sunburst:SunburstTooltipSettings.TooltipTemplate>
    </sunburst:SunburstTooltipSettings>
  </sunburst:SfSunburstChart.TooltipSettings>

{% endhighlight %}

{% highlight C# %}

  SunburstTooltipSettings tooltipSettings = new SunburstTooltipSettings();
  tooltipSettings.ShowTooltip = true;

  DataTemplate template = new DataTemplate(() =>
  {
     StackLayout stack = new StackLayout() { Orientation = StackOrientation.Vertical };

     StackLayout categoryLayout = new StackLayout() { Orientation = StackOrientation.Horizontal };
     Label label = new Label() { Text = "Country :" };
     label.TextColor = Color.White;
     Label category = new Label();
     category.TextColor = Color.White;
     category.SetBinding(Label.TextProperty, "Category");
     categoryLayout.Children.Add(label);
     categoryLayout.Children.Add(category);

     StackLayout valueLayout = new StackLayout() { Orientation = StackOrientation.Horizontal };
     Label label1 = new Label() { Text = "Count :" };
     label1.TextColor = Color.White;
     Label value = new Label();
     value.TextColor = Color.White;
     value.SetBinding(Label.TextProperty, "Value");
     valueLayout.Children.Add(label1);
     valueLayout.Children.Add(value);

     stack.Children.Add(categoryLayout);
     stack.Children.Add(valueLayout);
     return stack;
     });

     tooltipSettings.TooltipTemplate = template;
     sunburstChart.TooltipSettings = tooltipSettings;

{% endhighlight %}

{% endtabs %} 

![Custom template support in Xamarin.Forms Sunburst](Tooltip_images/Template.png)

