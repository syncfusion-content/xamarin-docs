---
layout: post
title: Orientation in LinearGauge
description: Learn how to set Orientation in LinearGauge
platform: Xamarin
control: LinearGauge
documentation: ug
---
# Orientation

SfLinearGauge provides support for the vertical orientation. By default SfLinearGauge renders with horizontal orientation. You can the change the orientation by the orientation property. It can be,

* Horizontal
* Vertical

{% tabs %}

{% highlight C# %}

  linearGauge.Orientation = Syncfusion.SfGauge.XForms.Orientation.OrientationVertical;

{% endhighlight %}

{% highlight xaml %}

	<gauge:SfLinearGauge x:Name="linearGauge" Orientation="Vertical" />
	
{% endhighlight %}

{% endtabs %}
