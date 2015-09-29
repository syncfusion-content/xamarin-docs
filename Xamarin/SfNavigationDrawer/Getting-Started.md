---
layout: post
title: Getting Started | SfNavigationDrawer | Xamarin | Syncfusion
description: getting started
platform: xamarin
control: SfNavigationDrawer 
documentation: ug
---

# Getting Started

## Create your first NavigationDrawer in Xamarin.Android

This section encompasses how to create a NavigationDrawer that navigates to different pages by selecting the desired page from the NavigationDrawer.  



### Add Syncfusion assembly reference

After installing Essential Studio for Xamarin, you can find all the required assemblies in the following installed folders,

{Syncfusion Installed location}\Essential Studio\{version number}\lib




N> Assemblies are available in unzipped package location in Mac.

Add the following assembly references to the Xamarin project,

1.android\Syncfusion.SfNavigationDrawer.Andriod.dll



### Create a NavigationDrawer

To develop an application with the Android NavigationDrawer is simple. The following steps explain you how to create and 
configure its properties.

Create an instance for the NavigationDrawer in the constructor and set that NavigationDrawer as content view of Activity. 



{% highlight C# %}  

SfNavigationDrawer navigationDrawer=new SfNavigationDrawer(this);

SetContentView(navigationDrawer);

{% endhighlight %} 


### Configure the NavigationDrawer

You can set position and animations for NavigationDrawer by using the position and Transition properties in the NavigationDrawer. 

{% highlight C# %}  

navigationDrawer.Position = Position.Left;

navigationDrawer.Transition = Transition.SlideOnTop;

{% endhighlight %} 


The above code example illustrates setting of position and animations for NavigationDrawer by using the position and 
Transition properties in the NavigationDrawer.

![](Create-your-first-NavigationDrawer-in-XamarinAndro_images/img2.png)

## Create your first NavigationDrawer in Xamarin.iOS

This section encompasses how to create a NavigationDrawer that navigates to different pages by selecting the desired page from the NavigationDrawer.  

### Add Syncfusion assembly reference

After installing Essential Studio for Xamarin, you can find all the required assemblies in the following installed folders:

{Syncfusion Installed location}\Essential Studio\{version number}\lib




N> Assemblies are available in unzipped package location in Mac.

Add the following assembly references to the iOS project.

iOS\Syncfusion.SfNavigationDrawer.iOS.dll



### Create a NavigationDrawer

To develop an application with the iOS NavigationDrawer is simple. The following steps explain you how to create and configure its properties.

Create an instance for the SfNavigationDrawer in the constructor and set that SfNavigationDrawer as content view of Activity. 

{% highlight C# %}  

public override void ViewDidLoad ()

{

base.ViewDidLoad ();

SFNavigationDrawer navigationDrawer1;

navigationDrawer1.Frame = new CGRect(0, 0, navigationDrawer1.DrawerWidth, navigationDrawer.DrawerHeight);

} 

{% endhighlight %} 

### Configure the NavigationDrawer

You can set position and animations for NavigationDrawer by using the position and Transition properties in the NavigationDrawer. 

{% highlight C# %}  

navigationDrawer.Position = SFNavigationDrawerPosition.SFNavigationDrawerPositionLeft;

navigationDrawer.Transition = SFNavigationDrawerTransition.SFNavigationDrawerTransitionSlideOnTop; 

{% endhighlight %} 

The above code example illustrates setting of position and animations for NavigationDrawer by using the position and Transition properties in the NavigationDrawer.

![](Create-your-first-NavigationDrawer-in-XamariniOS_images/img2.png)



