---

layout: post
title: NavigationStripPosition in Syncfusion Rotator Control for Xamarin.Forms 
description: Learn how to set the position of the navigation bar items in Rotator control
platform: xamarin 
control: Rotator
documentation: ug

---

# Customization of Navigation Strip

## Strip Mode

The `NavigationStripMode` property specifies the appearance of navigation bar items. The image data can be selected either by Thumbnail or by Dots navigation modes.

* `Thumbnail` - The slider items will be loaded in thumbnail view additionally. When a thumbnail item is clicked, the slider will switch to the corresponding image data.

{% tabs %}

{% highlight C# %}

	rotator.NavigationStripMode = NavigationStripMode.Thumbnail;	

{% endhighlight %}

{% highlight xaml %}

	<rotator:SfRotator x:Name="rotator" NavigationStripMode="Thumbnail" />
	
{% endhighlight %}

{% endtabs %}

![](images/thumbnail.png)

* `Dots` - The slider items will be loaded in dots view additionally. When a dots item is clicked, the slider will switch to the corresponding image data.

{% tabs %}

{% highlight C# %}

	rotator.NavigationStripMode = NavigationStripMode.Dots;	

{% endhighlight %}

{% highlight xaml %}

	<rotator:SfRotator x:Name="rotator" NavigationStripMode="Dots" />
	
{% endhighlight %}

{% endtabs %}

![](images/dots.png)


## Strip Position

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