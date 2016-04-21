---
layout: post
title: NavigationMode of Syncfusion Rotator control for Xamarin.Forms 
description: Learn how to view the different navigation modes of the Rotator control in Xamarin.Forms
platform: Xamarin.Forms 
control: Rotator
documentation: ug
---

# Navigation Modes

The `NavigationStripMode` property specifies the appearance of navigation bar items. The image datas can be selected either by Thumbnail or by Dots navigation modes.

* `Thumbnail` - The slider items will be loaded in thumbnail view additionally. When a thumbnail item is clicked, the slider will switch to the corresponding image data.

{% highlight C# %}

	rotator.NavigationStripMode = NavigationStripMode.Thumbnail;	

{% endhighlight %}

![](images/thumbnail.png)

* `Dots` - The slider items will be loaded in dots view additionally. When a dots item is clicked, the slider will switch to the corresponding image data.

{% highlight C# %}

	rotator.NavigationStripMode = NavigationStripMode.Dots;	

{% endhighlight %}

![](images/dots.png)