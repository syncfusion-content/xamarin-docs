---
layout: post
title: Opening drawer panel in Syncfusion's NavigationDrawer control for Xamarin.Forms
description: Learn how to open Drawer panel programmatically.
platform: Xamarin
control: NavigationDrawer
documentation: ug
---
# How To Open Drawer panel Programmatically

In order to open NavigationDrawer's drawer panel, it is needed to use the `IToggleDrawer` interface through DependencyService call, which in turn displays the available method `ToggleDrawer()`.

{% highlight C# %}

	DependencyService.Get<IToggleDrawer>().ToggleDrawer();

{% endhighlight %}


