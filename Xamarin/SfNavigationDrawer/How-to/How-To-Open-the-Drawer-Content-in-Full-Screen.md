---
layout: post
title: Opening Full Screen Drawer Content in Syncfusion NavigationDrawer control for Xamarin.Forms
description: Learn how to open the Drawer Content in Full Screen.
platform: Xamarin
control: NavigationDrawer
documentation: ug
---
# How To Open the Drawer Content in Full Screen

It can be done using `DrawerWidth` and `DrawerHeight` properties in SfNavigationDrawer control. Width and Height can be set according to the screen bounds to acquire the sliding panel to desired size.

{% highlight c# %}

    navigationDrawer.DrawerHeight=300;
    navigationDrawer.DrawerWidth=300;

{% endhighlight %}



