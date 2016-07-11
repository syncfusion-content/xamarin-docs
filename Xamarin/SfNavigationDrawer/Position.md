---
layout: post
title: Position of Drawer in Syncfusion NavigationDrawer control for Xamarin.Forms
description: Learn how to set position of the DrawerView panel.
platform: Xamarin
control: NavigationDrawer
documentation: ug
---
# Position

The `Position` property specifies the sliding position of the DrawerView panel. The `Position` property has the following four options.

* Left

* Right

* Top

* Bottom

N> The default option is Left.

## Left

Sets the SfNavigationDrawer sliding position to the left.

{% tabs %}	
	
{% highlight c# %}

	navigationDrawer.Position=Position.Left;

{% endhighlight %}

{% highlight xaml %}

	<navigation:SfNavigationDrawer x:Name="navigationDrawer" Position="Left">
  	
{% endhighlight %}

{% endtabs %}

![](images/Left.png)

## Right

Sets the SfNavigationDrawer sliding position to the right.

{% tabs %}	
	
{% highlight c# %}

	navigationDrawer.Position=Position.Right;

{% endhighlight %}

{% highlight xaml %}

	<navigation:SfNavigationDrawer x:Name="navigationDrawer" Position="Right">
	
{% endhighlight %}

{% endtabs %}

![](images/Right.png)
	
## Top

Sets the SfNavigationDrawer sliding position to the top.

{% tabs %}	
	
{% highlight c# %}
	
   	navigationDrawer.Position=Position.Top;

{% endhighlight %}

{% highlight xaml %}

	<navigation:SfNavigationDrawer x:Name="navigationDrawer" Position="Top">
	
{% endhighlight %}

{% endtabs %}

![](images/Top.png)

## Bottom

Sets the SfNavigationDrawer sliding position to the bottom.

{% tabs %}	
	
{% highlight c# %}

	navigationDrawer.Position=Position.Bottom;

{% endhighlight %}

{% highlight xaml %}

	<navigation:SfNavigationDrawer x:Name="navigationDrawer" Position="Bottom">
	
{% endhighlight %}

{% endtabs %}

![](images/bottom.png)






