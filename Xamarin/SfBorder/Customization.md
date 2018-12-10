---
layout: post
title: Various customization in Syncfusion border control for Xamarin.Forms
description: Learn how to customize the border control
platform: Xamarin
control: SfBorder
documentation: ug
---

# Customization

The border control supports customizing the border color, width, corner radius, background color, and more. The border can be customized using the following properties.

## Border color

You can customize the color of the border using the `BorderColor` property.

{% tabs %}
{% highlight xaml %}

<border:SfBorder x:Name="border" BorderColor = "Red"/>

{% endhighlight %}
{% highlight c# %}

SfBorder border = new SfBorder();
border.BorderColor = Color.Red;

{% endhighlight %}
{% endtabs %}

![bordercolor](images/Xamarin_Forms_BorderColor.png)

## Background color

The background color of the border control can be customized using the `BackgroundColor` property.

{% tabs %}
{% highlight xaml %}

<border:SfBorder x:Name="border" BackgroundColor = "Green"/>

{% endhighlight %}
{% highlight c# %}

SfBorder border = new SfBorder();
border.BackgroundColor = Color.Green;

{% endhighlight %}
{% endtabs %}

![backgroundcolor](images/Xamarin_Forms_BackgroundColor.png)

## Border width

You can customize the thickness of the border using the `BorderWidth` property.

{% tabs %}
{% highlight xaml %}

<border:SfBorder x:Name="border" BorderWidth = "12"/>

{% endhighlight %}
{% highlight c# %}

SfBorder border = new SfBorder();
border.BorderWidth = 12;

{% endhighlight %}
{% endtabs %}

![borderwidth](images/Xamarin_Forms_BorderWidth.png)

## Corner radius

You can customize the corner radius of the border on four sides using the `CornerRadius` property with type as `Thickness`.

% tabs %}
{% highlight xaml %}

<border:SfBorder x:Name="border" CornerRadius="0,10,10,0"/>

{% endhighlight %}
{% highlight c# %}

SfBorder border = new SfBorder();
border.CornerRadius =  new Thickness (0,10,10,0);

{% endhighlight %}
{% endtabs %}

![cornerradius](images/Xamarin_Forms_CornerRadius.png)

