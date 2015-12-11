---
layout: post
title: Getting Started | SfMaps | Xamarin | Syncfusion
description: getting started
platform: xamarin
control: SfMaps 
documentation: ug
---

# Getting Started

## Create your first Maps in Xamarin.Android

You can configure an Essential Maps for Xamarin Android in simple steps. In this section, you can learn how to configure a Maps control in a real-time scenario and also provides a walk-through on some of the customization features available in Maps control.


### Reference Essential Studio components in your solution

After installing Essential Studio for Xamarin, you can find all the required assemblies in the installation folders,

{Installed location}\Essential Studio\12.4.0.24\lib


N> Assemblies are available in unzipped package location in Mac

Add the following assembly references to the Android project,

 [android\<.SfMaps.Andriod.dll]

### Add and configure the Maps

Create a Maps instance in Main Activity and set Maps as a ContentView in onCreate() overridden method.

{% highlight c# %}

        protected override void OnCreate (Bundle savedInstanceState)
        {
            base.OnCreate (savedInstanceState);

            SfMaps maps = new SfMaps (this);
            SetContentView (maps);
        }

{% endhighlight %}

### Loading Shapes to Maps

The Maps control supports reading and loading shape files. A shape file is a set of files which are stored in a non-topological geometry and the attribute information for the spatial features and records in a data set. 

A shape file can be a set of files or a single file. Generally, the shape file contains the following files:

•Main file (.shp)

•dBASE file (.dbf)

These files need to be added in Asset folder.

{% highlight c# %}


	
	    protected override void OnCreate (Bundle savedInstanceState)
        {
            base.OnCreate (savedInstanceState);

            SfMaps maps = new SfMaps (this);
            ShapeFileLayer layer = new ShapeFileLayer ();
            layer.Uri = "usa_state.shp";
            maps.Layers.Add (layer);
            SetContentView (maps);
        }

{% endhighlight %}

![](images/maps_android.png)  
	
## Create your first Maps in Xamarin.iOS

You can configure an Essential Maps for Xamarin iOS in simple steps. In this section, you can learn how to configure a Maps control in a real-time scenario and also provides a walk-through on some of the customization features available in Maps control.

### Reference Essential Studio Components in your Solution

After installing Essential Studio for Xamarin, you can find all the required assemblies in the installation folders, typically:

{Syncfusion Installed location}\Essential Studio\{version number}\lib


N> You can find assemblies in unzipped package location in Mac.

You have to add the following assembly references to the Xamarin.iOS project.

[iOS\Syncfusion.SfMaps.iOS.dll]

### Initialize the Maps

Create a Maps object in the UIViewController and add Maps as SubView in ViewDidLoad override method.

You can create a Maps object by using the following code example.

{% highlight c# %}  

        public override void ViewDidLoad ()
        {
            base.ViewDidLoad ();
            SFMap maps = new SFMap ();
            View.AddSubview (maps);

        }


{% endhighlight %}

### Loading Shapes to Maps

The Maps control supports reading and loading shape files. A shape file is a set of files which are stored in a non-topological geometry and the attribute information for the spatial features and records in a data set. 

A shape file can be a set of files or a single file. Generally, the shape file contains the following files:

•Main file (.shp)

•dBASE file (.dbf)

{% highlight c# %}


	
	    public override void ViewDidLoad ()
        {
            base.ViewDidLoad ();
            SFMap maps = new SFMap ();
            SFShapeFileLayer layer = new SFShapeFileLayer ();
            layer.Uri = (NSString)NSBundle.MainBundle.PathForResource ("usa_state", "shp");
            maps.Layers.Add (layer);
            View.AddSubview (maps);

        }
{% endhighlight %}

![](images/maps_iOS.png)  