---
layout: post
title: Chart Title
description: How to add and customize the chart title in Essential Xamarin.Forms. 
platform: xamarin
control: Chart
documentation: ug
---

# Chart Title

You can define and customize the title of a chart using the `Title` property of chart. The `Text` property of the `ChartTitle` is used to set the text for title. 

The following properties are used to customize its appearance:

* `TextColor`—Used to change the color of the text.
* `BackgroundColor`—Used to change the background color.
* `BorderColor`—Used to change the border color.
* `BorderWidth`—Used to change the border width.
* `Font`—Used to change the text size, font family, and font weight.
* `Margin`—Used to change the margin of title.

{% tabs %} 

{% highlight xaml %}

<chart:SfChart>

	<chart:SfChart.Title>

		<chart:ChartTitle Text="Efficiency of oil-fired power production" TextColor="Blue"/>

	</chart:SfChart.Title>  

</chart:SfChart>

{% endhighlight %}

{% highlight c# %}

SfChart sfChart = new SfChart();

sfChart.Title.Text = "Efficiency of oil-fired power production";

sfChart.Title.TextColor = Color.Blue;

{% endhighlight %}

{% endtabs %}

![](charttitle_images/charttitle_img1.png)

## Text alignment

You can align the text of the title to the start, center, or end of the title area using the `TextAlignment` property of the `ChartTitle`.

{% tabs %} 

{% highlight xaml %}

<chart:SfChart.Title>

	<chart:ChartTitle Text="Efficiency of oil-fired power production" TextAlignment="Start" TextColor="Blue"/>

</chart:SfChart.Title>  

{% endhighlight %}

{% highlight c# %}

sfChart.Title.Text = "Efficiency of oil-fired power production";

sfChart.Title.TextAlignment = TextAlignment.Start;

sfChart.Title.TextColor = Color.Blue;

{% endhighlight %}

{% endtabs %}

![](charttitle_images/charttitle_img2.png)