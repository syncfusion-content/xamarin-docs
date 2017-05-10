---
layout : post
title : Watermark support of Syncfusion SfAutoComplete control for Xamarin.Forms
description : Learn about Watermark support in autocomplete control
platform : xamarin
control : SfAutoComplete
documentation : ug
---

# Watermark

Watermark provides a short note about the type of input to enter in the editor control. Watermarks are visible only if the text is empty. Also it will reappear if the text is cleared.
The following example, explains the usability of watermark which hints user to start with the character “U”.

{% tabs %}

{% highlight xaml %}

    <autocomplete:SfAutoComplete HeightRequest="40" WidthRequest="180" Watermark="Enter 'U' to filter suggestions" x:Name="autoComplete" />

{% endhighlight %}

{% highlight c# %}

    autoComplete.Watermark = "Enter 'U' to filter suggestions"; 

{% endhighlight %}

{% endtabs %}

![](images/watermark.png)

# Changing Watermark Text Color

Text color of watermark can be customized using WatermarkColor property.

{% highlight xaml %}

    <autocomplete:SfAutoComplete HeightRequest="40" WidthRequest="180" Watermark="Enter some text" WatermarkColor="#1976d2" x:Name="autoComplete" />

{% endhighlight %}

![](images/watermark-color.png)