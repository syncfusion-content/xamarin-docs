---

layout: post
title: Precision Mode in Syncfusion Rating control for Xamarin.Forms
description: Learn how to change the Precision Mode of rating control
platform: Xamarin
control: Rating
documentation: ug

---

# Various Precision Modes

The Precision mode defines the accuracy level of the SfRating control. It has Standard, Half and Exact options.

## Standard

The rating item will be filled completely based on the rating value.

{% tabs %}

{% highlight C# %}

	rating.Precision=Precision.Standard;

{% endhighlight %} 

{% highlight xaml %}

	<rating:SfRating x:Name="rating" Precision="Standard" />
	
{% endhighlight %}

{% endtabs %}

![](images/standard.jpg)

## Half

The rating item will be filled partially based on the rating value.

{% tabs %}

{% highlight C# %}

	rating.Precision=Precision.Half;

{% endhighlight %} 

{% highlight xaml %}

	<rating:SfRating x:Name="rating" Precision="Half" />
	
{% endhighlight %}

{% endtabs %}

![](images/half.jpg) 

## Exact

The rating item will be filled exactly based on the rating value.

{% tabs %}

{% highlight c# %}

	rating.Precision=Precision.Exact;

{% endhighlight %} 

{% highlight xaml %}

	<rating:SfRating x:Name="rating" Precision="Exact" />
	
{% endhighlight %}

{% endtabs %}

![](images/exact.jpg) 



