---
layout: post
title: Formatting Strings in Xamarin Range Slider Control | Syncfusion
description: Discover how to format strings in the Syncfusion Xamarin Range Slider (SfRangeSlider) control.
platform: Xamarin
control: RangeSlider
documentation: ug
---

# Formatting Strings in Xamarin Range Slider (SfRangeSlider)

The value label of the [`SfRangeSlider`](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfRangeSlider.XForms.SfRangeSlider.html) can be configured to display various formats, such as currency and percentage. You can customize the value label using string formatting with the [`LabelFormat`](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfRangeSlider.XForms.SfRangeSlider.html#Syncfusion_SfRangeSlider_XForms_SfRangeSlider_LabelFormat) property, which specifies the desired format of the displayed value.

## Available Formatting Types

You can choose from different formatting types, including currency, exponential, number, and percentage formats. Additionally, text can be added to the value using the [`LabelFormat`](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfRangeSlider.XForms.SfRangeSlider.html#Syncfusion_SfRangeSlider_XForms_SfRangeSlider_LabelFormat) property.

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

We have provided the support for changing the [`Culture`](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfRangeSlider.XForms.SfRangeSlider.html#Syncfusion_SfRangeSlider_XForms_SfRangeSlider_Culture) when using currency notation for the formatting type. To do this, enable the currency format and set the desired culture.

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




