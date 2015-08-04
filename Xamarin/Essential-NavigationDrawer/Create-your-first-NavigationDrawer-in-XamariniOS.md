---
layout: post
title: Create-your-first-NavigationDrawer-in-XamariniOS
description: create your first navigationdrawer in xamarin.ios
platform: ios
control: Control Name undefined
documentation: ug
---

#### Create your first NavigationDrawer in Xamarin.iOS

This section encompasses how to create a NavigationDrawer that navigates to different pages by selecting the desired page from the NavigationDrawer.  

Add Syncfusion assembly reference

After installing Essential Studio for Xamarin, you can find all the required assemblies in the following installed folders:

{Syncfusion Installed location}\Essential Studio\{version number}\lib



![](Create-your-first-NavigationDrawer-in-XamariniOS_images/Create-your-first-NavigationDrawer-in-XamariniOS_img1.jpeg)
{:.image }
_Note: Assemblies are available in unzipped package location in Mac._

Add the following assembly references to the iOS project.

 iOS\Syncfusion.SfNavigationDrawer.iOS.dll



Create a NavigationDrawer

To develop an application with the iOS NavigationDrawer is simple. The following steps explain you how to create and configure its properties.

Create an instance for the SfNavigationDrawer in the constructor and set that SfNavigationDrawer as content view of Activity. 

[C#]

public override void ViewDidLoad ()

{

  base.ViewDidLoad ();

SFNavigationDrawer navigationDrawer1;

navigationDrawer1.Frame = new CGRect(0, 0, navigationDrawer1.DrawerWidth, navigationDrawer.DrawerHeight);

}

Configure the NavigationDrawer

You can set position and animations for NavigationDrawer by using the position and Transition properties in the NavigationDrawer. 

[C#]

navigationDrawer.Position = SFNavigationDrawerPosition.SFNavigationDrawerPositionLeft;

navigationDrawer.Transition = SFNavigationDrawerTransition.SFNavigationDrawerTransitionSlideOnTop;

The above code example illustrates setting of position and animations for NavigationDrawer by using the position and Transition properties in the NavigationDrawer.

![C:/Users/nijamudeensulaiman/Desktop/slidedrawer.png](Create-your-first-NavigationDrawer-in-XamariniOS_images/Create-your-first-NavigationDrawer-in-XamariniOS_img2.png)
{:.image }


