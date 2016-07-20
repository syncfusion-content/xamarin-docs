---
layout: post
title: Opening drawer panel in Syncfusion's NavigationDrawer control for Xamarin.Forms
description: Learn how to open Drawer panel programmatically.
platform: Xamarin
control: NavigationDrawer
documentation: ug
---
## How To Open Drawer panel Programmatically?

In order to open NavigationDrawer's drawer panel, it is needed to use the `IToggleDrawer` interface through DependencyService call, which in turn displays the available method `ToggleDrawer()`.

{% highlight C# %}

	DependencyService.Get<IToggleDrawer>().ToggleDrawer();

{% endhighlight %}


## How To Open the Drawer Content in Full Screen?

It can be done using `DrawerWidth` and `DrawerHeight` properties in SfNavigationDrawer control. Width and Height can be set according to the screen bounds to acquire the sliding panel to desired size.

{% highlight c# %}

    navigationDrawer.DrawerHeight=300;
    navigationDrawer.DrawerWidth=300;

{% endhighlight %}

## How To Perform an action while Drawer is Opening Or Closing?

The `Toggled` event can be hooked to get opening and closing events. This has parameters of NavigationDrawer and a boolean property to display whether it is open or closed.

{% highlight C# %}

navigationDrawer.Toggled += (object sender,Syncfusion.SfNavigationDrawer.XForms.ToggledEventArgs e) => {
		// your codes here
		bool drawerState = e.isOpen;
};
{% endhighlight %}

