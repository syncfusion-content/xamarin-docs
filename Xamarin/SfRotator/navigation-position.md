---

layout: post
title: NavigationStripPosition in Syncfusion Rotator Control for Xamarin.Forms 
description: Learn how to set the position of the navigation bar items in Rotator control
platform: xamarin 
control: Rotator
documentation: ug

---

# NavigationStripPosition

The `NavigationStripPosition` position specifies the placement position of the navigation bar items such as thumbnail or dots relative to the slider area. 

There are four available positions,

* `Bottom` - Sets the position of the navigation bar items to the bottom.

{% tabs %}

{% highlight C# %}

	rotator.NavigationStripPosition = NavigationStripPosition.Bottom;

{% endhighlight %}

{% highlight xaml %}

	<rotator:SfRotator x:Name="rotator" NavigationStripPosition="Bottom" />
	
{% endhighlight %}

{% endtabs %}

* `Left` - Sets the position of the navigation bar items to the left.

{% tabs %}

{% highlight C# %}

	rotator.NavigationStripPosition = NavigationStripPosition.Left;

{% endhighlight %}

{% highlight xaml %}

	<rotator:SfRotator x:Name="rotator" NavigationStripPosition="Left" />
	
{% endhighlight %}

{% endtabs %}

* `Top` - Sets the position of the navigation bar items to the top.

{% tabs %}

{% highlight C# %}

	rotator.NavigationStripPosition = NavigationStripPosition.Top;

{% endhighlight %}

{% highlight xaml %}

	<rotator:SfRotator x:Name="rotator" NavigationStripPosition="Top" />
	
{% endhighlight %}

{% endtabs %}

* `Right` - Sets the position of the navigation bar items to the right.

{% tabs %}

{% highlight C# %}

	rotator.NavigationStripPosition = NavigationStripPosition.Right;

{% endhighlight %}


{% highlight xaml %}

	<rotator:SfRotator x:Name="rotator" NavigationStripPosition="Right" />
	
{% endhighlight %}

{% endtabs %}

![](images/tabstrip.png)