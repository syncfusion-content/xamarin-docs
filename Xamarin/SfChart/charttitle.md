---
layout: post
title: Chart Title
description: How to add chart title and customize the appearance of the chart title in the Essential Xamarin.Forms.
platform: xamarin
control: Chart
documentation: ug
---

# Title

You can define and customize the Chart title using [`Title`](https://help.syncfusion.com/cr/cref_files/xamarin/Syncfusion.SfChart.XForms~Syncfusion.SfChart.XForms.SfChart~Title.html) property of [`SfChart`](https://help.syncfusion.com/cr/cref_files/xamarin/Syncfusion.SfChart.XForms~Syncfusion.SfChart.XForms.SfChart.html). The [`Text`](https://help.syncfusion.com/cr/cref_files/xamarin/Syncfusion.SfChart.XForms~Syncfusion.SfChart.XForms.ChartTitle~Text.html) property of [`ChartTitle`](https://help.syncfusion.com/cr/cref_files/xamarin/Syncfusion.SfChart.XForms~Syncfusion.SfChart.XForms.ChartTitle.html) is used to set the text for the title. 

Following properties are used to customize its appearance.

* [`TextColor`](https://help.syncfusion.com/cr/cref_files/xamarin/Syncfusion.SfChart.XForms~Syncfusion.SfChart.XForms.ChartTitle~TextColor.html) – used to change the color of the text.
* [`BackgroundColor`](https://help.syncfusion.com/cr/cref_files/xamarin/Syncfusion.SfChart.XForms~Syncfusion.SfChart.XForms.ChartTitle~BackgroundColor.html) – used to change the background color.
* [`BorderColor`](https://help.syncfusion.com/cr/cref_files/xamarin/Syncfusion.SfChart.XForms~Syncfusion.SfChart.XForms.ChartTitle~BorderColor.html) – used to change the border color.
* [`BorderWidth`](https://help.syncfusion.com/cr/cref_files/xamarin/Syncfusion.SfChart.XForms~Syncfusion.SfChart.XForms.ChartTitle~BorderWidth.html) – used to change the border width.
* [`Font`](https://help.syncfusion.com/cr/cref_files/xamarin/Syncfusion.SfChart.XForms~Syncfusion.SfChart.XForms.ChartTitle~Font.html) – used to change the text size, font family, and font weight. (This is deprecated API. Use FontSize, FontFamily, and FontAttributes properties instead of this.)
* [`FontFamily`](https://help.syncfusion.com/cr/cref_files/xamarin/Syncfusion.SfChart.XForms~Syncfusion.SfChart.XForms.ChartTitle~FontFamily.html) - used to change the font family for chart title. 
* [`FontAttributes`](https://help.syncfusion.com/cr/cref_files/xamarin/Syncfusion.SfChart.XForms~Syncfusion.SfChart.XForms.ChartTitle~FontAttributes.html) – used to change the font style for the chart title.
* [`FontSize`](https://help.syncfusion.com/cr/cref_files/xamarin/Syncfusion.SfChart.XForms~Syncfusion.SfChart.XForms.ChartTitle~FontSize.html) - used to change the font size for the chart title.
* [`Margin`](https://help.syncfusion.com/cr/cref_files/xamarin/Syncfusion.SfChart.XForms~Syncfusion.SfChart.XForms.ChartTitle~Margin.html) - used to change the margin for title.

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

## Text Alignment

You can align the title text content to the Start, Center or End of the title using the [`TextAlignment`](https://help.syncfusion.com/cr/cref_files/xamarin/Syncfusion.SfChart.XForms~Syncfusion.SfChart.XForms.ChartTitle~TextAlignment.html) property of the [`ChartTitle`](https://help.syncfusion.com/cr/cref_files/xamarin/Syncfusion.SfChart.XForms~Syncfusion.SfChart.XForms.ChartTitle.html).

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