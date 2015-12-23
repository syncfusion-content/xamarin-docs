---
layout: post
title: Xamarin.Forms | Chart Title
description: How to add and customize chart title in Essential Xamarin.Forms 
platform: xamarin
control: Chart
documentation: ug
---

# Chart Title

You can define and customise the Chart title using `Title` property of `SfChart`. The `Text` property of `ChartTitle` is used to set the text for the title. 

Following properties are used to customize its appearance.

* `TextColor` – used to change the color of the text.
* `BackgroundColor` – used to change the background color.
* `BorderColor` – used to change the border color.
* `BorderWidth` – used to change the border width.
* `Font` – used to change the text size, font family and font weight.
* `Margin` - used to change the margin for title.

{% highlight xml %}
[XAML]

<chart:SfChart>

<chart:SfChart.Title>

<chart:ChartTitle Text="Efficiency of oil-fired power production" TextColor="Blue"/>

</chart:SfChart.Title>  

</chart:SfChart>

{% endhighlight %}

{% highlight c# %}
[C#]

SfChart sfChart = new SfChart();

sfChart.Title.Text = "Efficiency of oil-fired power production";

sfChart.Title.TextColor = Color.Blue;

{% endhighlight %}

![D:/Chart UG/Xamarin/UG images/Xamarin UG Images/Merged UG Images/ChartTitle/text.png](charttitle_images/charttitle_img1.jpeg)


## Text Alignment

You can align the title text content to the Start, Center or End of the title using the `TextAlignment` property of the `ChartTitle`.

{% highlight xml %}
[XAML]

<chart:SfChart.Title>

<chart:ChartTitle Text="Efficiency of oil-fired power production" TextAlignment="Start" TextColor="Blue"/>

</chart:SfChart.Title>  

{% endhighlight %}

{% highlight c# %}
[C#]

sfChart.Title.Text = "Efficiency of oil-fired power production";

sfChart.Title.TextAlignment = TextAlignment.Start;

sfChart.Title.TextColor = Color.Blue;

{% endhighlight %}

![D:/Chart UG/Xamarin/UG images/Xamarin UG Images/Merged UG Images/ChartTitle/text-alignment.png](charttitle_images/charttitle_img2.jpeg)