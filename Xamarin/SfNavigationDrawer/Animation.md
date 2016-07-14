---
layout: post
title: Transition of drawer in Syncfusion NavigationDrawer control for Xamarin.Forms
description: Learn how to set Transition of the DrawerView panel.
platform: Xamarin
control: NavigationDrawer
documentation: ug
---
# Drawer Opening Animation

The `Transition` property specifies the sliding animations for the DrawerView panel. The `Transition` property has the following three options.

* SlideOnTop
* Push
* Reveal

N> The default Transition is SlideOnTop.

## SlideOnTop

Slides the DrawerContent on top of the main content.

{% tabs %}	
	
{% highlight c# %} 

	navigationDrawer.Transition=Transition.SlideOnTop;

{% endhighlight %}

{% highlight xaml %}

	<navigation:SfNavigationDrawer x:Name="navigationDrawer" Transition="SlideOnTop">
	
{% endhighlight %}

{% endtabs %}

![](images/Slide-on-top.png)

## Push

This transition slides the Drawer and main content simultaneously.

{% tabs %}	
	
{% highlight c# %} 

	navigationDrawer.Transition=Transition.Push;

{% endhighlight %}

{% highlight xaml %}

	<navigation:SfNavigationDrawer x:Name="navigationDrawer" Transition="Push">
	
{% endhighlight %}

{% endtabs %}

![](images/Push.png)

## Reveal

This transition keeps the Drawer content in fixed position and the main content will be slide to reveal the drawer content.

{% tabs %}	
	
{% highlight c# %} 

	navigationDrawer.Transition=Transition.Reveal;

{% endhighlight %}

{% highlight xaml %}

	<navigation:SfNavigationDrawer x:Name="navigationDrawer" Transition="Reveal">
	
{% endhighlight %}

{% endtabs %}

![](images/reveal.png)
