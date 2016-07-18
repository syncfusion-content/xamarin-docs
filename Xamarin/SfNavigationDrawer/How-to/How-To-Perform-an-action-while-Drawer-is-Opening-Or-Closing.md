---
layout: post
title: Performing an action in Drawer in Syncfusion NavigationDrawer control for Xamarin.Forms
description: Learn how to Perform an action while Drawer is Opening Or Closing
platform: Xamarin
control: NavigationDrawer
documentation: ug
---
# How To Perform an action while Drawer is Opening Or Closing

The `Toggled` event can be hooked to get opening and closing events. This has parameters of NavigationDrawer and a boolean property to display whether it is open or closed.

{% highlight C# %}

navigationDrawer.Toggled += (object sender,Syncfusion.SfNavigationDrawer.XForms.ToggledEventArgs e) => {
		// your codes here
		bool drawerState = e.isOpen;
};
{% endhighlight %}
