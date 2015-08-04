---
layout: post
title: Create-your-first-NavigationDrawer-in-XamarinAndro
description: create your first navigationdrawer in xamarin.android
platform: ios
control: Control Name undefined
documentation: ug
---

#### Create your first NavigationDrawer in Xamarin.Android

This section encompasses how to create a NavigationDrawer that navigates to different pages by selecting the desired page from the NavigationDrawer.  



Add Syncfusion assembly reference

After installing Essential StudioforXamarin, you can find all the required assemblies in the following installed folders,

{Syncfusion Installed location}\Essential Studio\{version number}\lib



![](Create-your-first-NavigationDrawer-in-XamarinAndro_images/Create-your-first-NavigationDrawer-in-XamarinAndro_img1.jpeg)
{:.image }
_Note: Assemblies are available in unzipped package location in Mac._

 Add the following assembly references to the Xamarin project,



android\Syncfusion.SfNavigationDrawer.Andriod.dll





Create a NavigationDrawer

To develop an application with the Android NavigationDrawer is simple. The following steps explain you how to create and configure its properties.

Create an instance for the NavigationDrawer in the constructor and set that NavigationDrawer as content view of Activity. 



[C#]



SfNavigationDrawer navigationDrawer=new SfNavigationDrawer(this);

SetContentView(navigationDrawer);



Configure the NavigationDrawer

You can set position and animations for NavigationDrawer by using the position and Transition properties in the NavigationDrawer. 

[C#]

navigationDrawer.Position = Position.Left;

navigationDrawer.Transition = Transition.SlideOnTop;

The above code example illustrates setting of position and animations for NavigationDrawer by using the position and Transition properties in the NavigationDrawer.

![C:/Users/nijamudeensulaiman/Desktop/slidedrawer (1).png](Create-your-first-NavigationDrawer-in-XamarinAndro_images/Create-your-first-NavigationDrawer-in-XamarinAndro_img2.png)
{:.image }




