---
layout: post
title: Tooltip feature of Essential Xamarin.Forms SfSunburstChart
description: This section describes the tooltip feature of sunburst chart.
platform: xamarin
control: SfSunburstChart
documentation: ug
---

# Tooltip

Tooltip provides additional information about the segments in the sunburst chart. Tooltip is displayed by tapping the segment. By default, tooltip displays the corresponding segment’s category and value. To enable the tooltip, set the `ShowTooltip` property to true.

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

![](Tooltip_images/Tooltip.png)

## Customization

The appearance of the tooltip can be customized using the following properties:

* TextColor: Customizes the text color of the tooltip.
* BackgroundColor: Customizes the background color of the tooltip.
* BorderColor: Customizes the border color of the tooltip.
* BorderWidth: Customizes the border width of the tooltip.
* Duration: Specifies the duration of the tooltip to be displayed.

The following code shows all the above customizations.

{% tabs %} 

{% highlight xaml %}

     <sunburst:SfSunburstChart.TooltipSettings>
                    <sunburst:SunburstTooltipSettings ShowTooltip="True" TextColor="White" BackgroundColor="Green" 
                                                      BorderColor="Black" BorderWidth="1" Duration="2000" ></sunburst:SunburstTooltipSettings>
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

![](Tooltip_images/Customization.png)

## Custom template

The sunburst chart provides options to design your own template for tooltip using the `TooltipTemplate` property.

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

                StackLayout categryLayout = new StackLayout() { Orientation = StackOrientation.Horizontal };
                Label label = new Label() { Text = "Country :" };
                label.TextColor = Color.White;
                Label category = new Label();
                category.TextColor = Color.White;
                category.SetBinding(Label.TextProperty, "Category");
                categryLayout.Children.Add(label);
                categryLayout.Children.Add(category);

                StackLayout valueLayout = new StackLayout() { Orientation = StackOrientation.Horizontal };
                Label label1 = new Label() { Text = "Count :" };
                label1.TextColor = Color.White;
                Label value = new Label();
                value.TextColor = Color.White;
                value.SetBinding(Label.TextProperty, "Value");
                valueLayout.Children.Add(label1);
                valueLayout.Children.Add(value);

                stack.Children.Add(categryLayout);
                stack.Children.Add(valueLayout);
                return stack;
            });

            tooltipSettings.TooltipTemplate = template;
            sunburstChart.TooltipSettings = tooltipSettings;

{% endhighlight %}

{% endtabs %} 

![](Tooltip_images/Template.png)

