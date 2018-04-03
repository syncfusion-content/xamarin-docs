---
layout: post
title: Format string in Syncfusion RangeSlider control for Xamarin.Forms
description: Learn how to provide the formatting string support for the Value in RangeSlider control.
platform: Xamarin
control: RangeSlider
documentation: ug
---

# Formatting string

The Value label of the SfRangeSlider can be configured to display different formats like currency format, percent format etc. We can also customize the Value label with string formatting. We can customize using `FormatString` property which determines the format specifier by which the display Value has to be formatted.

## Formatting types

We have different formatting types such as currency format, exponential format, number format, percentage format etc. We can also add the text with Value using FormatString 

{% tabs %}

{% highlight xaml %}

  <StackLayout Margin="3">
  
   <range:SfRangeSlider x:Name="rangeSlider1" FormatString="Value: {0:c}" HeightRequest="90" WidthRequest="200" Minimum="0" Maximum="12" RangeStart="0" RangeEnd="12" TickFrequency="2"/>
            
   <range:SfRangeSlider x:Name="rangeslider2" FormatString="Value: {0:n}" Minimum="0" TickFrequency="2" Maximum="10"/>
              
   </StackLayout>
 {% endhighlight %}

{% highlight c# %}

    StackLayout stack = new StackLayout();
    SfRangeSlider rangeSlider1=new SfRangeSlider();
	rangeSlider1.RangeEnd=12; 
	rangeSlider1.RangeStart=0;
	rangeSlider1.TickFrequency = 2;
	rangeSlider1.HeightRequest="90";
	rangeSlider1.WidthRequest=200;
	rangeSlider1.FormatString = "Value: {0:c}"
	rangeSlider1.ShowRange=true; 
	rangeSlider1.TrackHeight="4";
	rangeSlider1.Minimum=0; 
	rangeSlider1.Maximum=12; 
	SfRangeSlider rangeSlider2=new SfRangeSlider();
	rangeSlider2.TickFrequency = 2;
	rangeSlider2.FormatString = "Value: {0:c}"
	rangeSlider2.Minimum=0; 
	rangeSlider2.Maximum=10; 
	this.stack.Children.Add(rangeSlider1);
	this.stack.Children.Add(rangeSlider2);
	this.Content = stack;

{% endhighlight %}
{% endtabs %}

![](images/FormatString.png)


## Culture Localization

We have provided the support for changing the Culture when using Currency notation for the formatting type. For this we have to enable Currency format and set the desired culture to be shown.

{% tabs %}

{% highlight xaml %}

 <range:SfRangeSlider x:Name="sfRangeSlider2" FormatString="Value: {0:c}" HeightRequest="90" WidthRequest="200" Minimum="0" Maximum="12" RangeStart="0" RangeEnd="12" TickFrequency="2"/>

 {% endhighlight %}

{% highlight c# %}

    SfRangeSlider rangeSlider=new SfRangeSlider();
	rangeSlider.RangeEnd=12; 
	rangeSlider.RangeStart=0;
	rangeSlider.TickFrequency = 2;
	rangeSlider.HeightRequest="90";
	rangeSlider.WidthRequest=200;
	rangeSlider.FormatString = "Value: {0:c}"
	rangeSlider.Culture = new System.Globalization.CultureInfo("fr-FR");
	rangeSlider.ShowRange=true; 
	rangeSlider.TrackHeight="4";
	rangeSlider.Minimum=0; 
	rangeSlider.Maximum=12; 
	this.Content = rangeSlider;

{% endhighlight %}
{% endtabs %}

![](images/culture.png)




