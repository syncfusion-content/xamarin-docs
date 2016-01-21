---
layout: post
title: Getting Started with Syncfusion Maps control for Xamarin.Forms
description: A quick tour to initial users on Syncfusion maps control for Xamarin.Forms platform
platform: xamarin
control: SfMaps 
documentation: ug
---

# Getting Started

This section explains you the steps to configure a Maps control in a real-time scenario and also provides a walk-through on some of the customization features available in Maps control.


## Referencing Essential Studio components in your solution

If you had acquired Essential Studio components through the Xamarin component store interface from within your IDE, then after adding the components to your Xamarin.iOS, Xamarin.Android and Windows Phone projects through the Component manager, you will still need to manually reference the PCL (Portable Class Library) assemblies in the Xamarin.Forms PCL project in your solution. You can do this by manually adding the relevant PCL assembly references to your PCL project contained in the following path inside of your solution folder.  

Components/syncfusionessentialstudio-version/lib/pcl/

Alternatively if you had downloaded Essential Studio from Syncfusion.com or through the Xamarin store web interface then all assembly references need to be added manually.

After installing Essential Studio for Xamarin, all the required assemblies can be found in the installation folders, typically

{Syncfusion Installed location}\Essential Studio\12.2.0.40\lib

Eg: C:\Program Files (x86)\Syncfusion\Essential Studio\12.2.0.40\lib

or after downloading through the Xamarin store web interface, all the required assemblies can be found in the below folder

{download location}\syncfusionessentialstudio-version\lib

You can then add the assembly references to the respective projects as shown below

### PCL project

pcl\Syncfusion.SfMaps.XForms.dll 

### Android project

android\Syncfusion.SfMaps.Andriod.dll

android\Syncfusion.SfMaps.XForms.Andriod.dll

### iOS(Classic) project

ios\Syncfusion.SfMaps.iOS.dll 

ios\Syncfusion.SfMaps.XForms.iOS.dll

ios\Syncfusion.SfMaps.XForms.dll

### iOS(Unified) project

ios-unified\Syncfusion.SfMaps.iOS.dll 

ios-unified\Syncfusion.SfMaps.XForms.iOS.dll

ios-unified\Syncfusion.SfMaps.XForms.dll

### Windows Phone project

wp8\Syncfusion.SfMaps.WP8.dll

wp8\Syncfusion.SfMaps.XForms.WinPhone.dll


N> Essential Maps for Xamarin is compatible with Xamarin. Forms v.1.2.3.6257.

Currently an additional step is required for Windows Phone and iOS projects. We need to create an instance of the Maps custom renderer as shown below. 

Create an instance of SfMaps in MainPage constructor in of the Windows Phone project as shown 

{% highlight xaml %}

    <syncfusion:SfMap>                     
  
    </syncfusion:SfMap>    

{% endhighlight %}

{% highlight C# %}

public MainPage()
{
    
    new SfMaps();
    ...
            
}

{% endhighlight %}
 

## Initializing Maps   

Create a Maps instance in Main Activity and set Maps as a ContentView in onCreate() overridden method.

{% highlight xaml %}

    <syncfusion:SfMap>
           
    </syncfusion:SfMap>    

{% endhighlight %}

{% highlight c# %}

protected override void OnCreate (Bundle savedInstanceState)
{
    
    base.OnCreate (savedInstanceState);

    SfMaps maps = new SfMaps (this);
    SetContentView (maps);
    
}

{% endhighlight %}

## Loading Shapes to Maps

The Maps control supports reading and loading shape files. A shape file is a set of files which are stored in a non-topological geometry and the attribute information for the spatial features and records in a data set. 

A shape file can be a set of files or a single file. Generally, the shape file contains the following files:

* Main file (.shp)

* dBASE file (.dbf)

These files need to be added in Asset folder.

{% highlight xaml %}

    <syncfusion:SfMap>                     
        <syncfusion:SfMap.Layers>                
            <syncfusion:ShapeFileLayer   Uri="usa_state.shp">                                    
            </syncfusion:ShapeFileLayer>           
        </syncfusion:SfMap.Layers>        
    </syncfusion:SfMap>    	        

{% endhighlight %}

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

![](Getting-Started_images/maps_xamarin.png)


## Adding Marker to the Maps

Markers can be added into the shape layers. The below code snippets enables you to do so.

{% highlight xaml %}

    <SfMaps:ShapeFileLayer:MapMarker>
                
        <SfMaps:MapMarker Label = "California" Latitude = "37" Longitude = "-120"/>                
                    
    </SfMaps:ShapeFileLayer:ShapeSetting>	              

{% endhighlight %}

{% highlight c# %}
	
protected override void OnCreate (Bundle savedInstanceState)
{
    
    base.OnCreate (savedInstanceState);
            
    SfMaps maps = new SfMaps (this);
    ShapeFileLayer layer = new ShapeFileLayer ();
    SFMapMarker marker = new SFMapMarker ();
    marker.Label = "California";
    marker.Latitude = 37;
    marker.Longitude = -120;
    layer.Markers.Add (marker);  
    maps.Layers.Add (layer);            
    SetContentView (maps);
    
}

{% endhighlight %}

![](Getting-Started_images/markers_xamarin.png) 