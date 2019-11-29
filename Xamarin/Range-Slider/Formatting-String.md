---
layout: post
title: Format string in Syncfusion RangeSlider control for Xamarin.Forms
description: Learn how to provide the formatting string support for the Value in xamarin.Forms RangeSlider control.
platform: Xamarin
control: RangeSlider
documentation: ug
---

# Formatting String

The Value label of the SfRangeSlider can be configured to display different formats like currency format, percent format etc. We can also customize the Value label with string formatting. We can customize using `LabelFormat` property which determines the format specifier by which the display Value has to be formatted.

## Formatting types

We have different formatting types such as currency format, exponential format, number format, percentage format etc. We can also add the text with Value using `LabelFormat` 

{% tabs %}

{% highlight xaml %}

<StackLayout Margin="3">

<range:SfRangeSlider x:Name="rangeSlider1" LabelFormat="Money: {0:c}" HeightRequest="90" WidthRequest="200" Minimum="0" Maximum="12" RangeStart="0" RangeEnd="12" TickFrequency="2"/>
          
</StackLayout>
 {% endhighlight %}

{% highlight c# %}

StackLayout stack = new StackLayout();
SfRangeSlider rangeSlider2 = new SfRangeSlider();
rangeSlider2 .RangeEnd=12; 
rangeSlider2 .RangeStart=0;
rangeSlider2 .TickFrequency = 2;
rangeSlider2 .HeightRequest="90";
rangeSlider2 .WidthRequest=200;
rangeSlider2 .LabelFormat = "{0:N2}” 
rangeSlider2 .ShowRange=true; 
rangeSlider2 .TrackHeight="4";
rangeSlider2 .Minimum=0; 
rangeSlider2 .Maximum=12; 
this.stack.Children.Add(rangeSlider2);
this.Content = stack;

{% endhighlight %}
{% endtabs %}

![Label Format image](images/FormatString.png)


## Culture Localization

We have provided the support for changing the Culture when using Currency notation for the formatting type. For this we have to enable Currency format and set the desired culture to be shown.

{% tabs %}

{% highlight xaml %}

 <range:SfRangeSlider x:Name="sfRangeSlider2" LabelFormat="c:{0:c2}" HeightRequest="90" WidthRequest="200" Minimum="0" Maximum="12" RangeStart="0" RangeEnd="12" TickFrequency="2"/>

 {% endhighlight %}

{% highlight c# %}

SfRangeSlider rangeSlider=new SfRangeSlider();
rangeSlider.RangeEnd=12; 
rangeSlider.RangeStart=0;
rangeSlider.TickFrequency = 2;
rangeSlider.HeightRequest="90";
rangeSlider.WidthRequest=200;
rangeSlider.LabelFormat = "c:{0:C2}"
rangeSlider.Culture = new System.Globalization.CultureInfo("fr-FR");
rangeSlider.ShowRange=true; 
rangeSlider.TrackHeight="4";
rangeSlider.Minimum=0; 
rangeSlider.Maximum=12; 
this.Content = rangeSlider;

{% endhighlight %}
{% endtabs %}

![Culture localization image](images/culture.png)




