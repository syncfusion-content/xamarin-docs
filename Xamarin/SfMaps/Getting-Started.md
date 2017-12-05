---
layout: post
title: Getting Started with Syncfusion Maps control for Xamarin.Forms
description: A quick tour about Syncfusion maps control in Xamarin.Forms platform
platform: xamarin
control: SfMaps 
documentation: ug
---

# Getting Started

This section explains you the steps to configure a Maps control in a real-time scenario and also provides a walk-through on some of the customization features available in Maps control.

## Adding SfMaps Reference

Refer this [article](https://help.syncfusion.com/xamarin/introduction/download-and-installation) to know how to obtain and reference Essential Studio components in your solution; then refer [this](https://help.syncfusion.com/xamarin/introduction/control-dependencies#sfmaps) link to know about the assemblies required for adding Maps to your project.

I> After adding the reference, currently, an additional step is required for iOS and UWP projects. We need to create an instance of the `SfMapsRenderer` in iOS and UWP projects as shown in this [KB article.](https://www.syncfusion.com/kb/7144)

I> For UWP alone, one more additional step is required if the project is built in release mode with .NET Native tool chain enabled. You can refer the [KB article](https://www.syncfusion.com/kb/7149) for more details.


## Initializing Maps   

Create a Maps instance in Main Activity and set Maps as a ContentView in onCreate() overridden method.

{% tabs %}

{% highlight xaml %}

    <syncfusion:SfMap>
           
    </syncfusion:SfMap>    

{% endhighlight %}

{% highlight c# %}

    SfMaps maps = new SfMaps ();
    this.ContentView=maps;
    


{% endhighlight %}

{% endtabs %}

## Loading Shapes to Maps

The Maps control supports reading and loading shape files. A shape file is a set of files which are stored in a non-topological geometry and the attribute information for the spatial features and records in a data set. 

A shape file can be a set of files or a single file. Generally, the shape file contains the following files:

* Main file (.shp)

* dBase file (.dbf)

These files need to be added in Asset folder.

{% tabs %}

{% highlight xaml %}

    <syncfusion:SfMap>                     
        <syncfusion:SfMap.Layers>                
            <syncfusion:ShapeFileLayer   Uri="usa_state.shp">                                    
            </syncfusion:ShapeFileLayer>           
        </syncfusion:SfMap.Layers>        
    </syncfusion:SfMap>    	        

{% endhighlight %}

{% highlight c# %}
	


    SfMaps maps = new SfMaps ();
    ShapeFileLayer layer = new ShapeFileLayer ();
    layer.Uri = "usa_state.shp";
    maps.Layers.Add (layer);
    this.ContentView=maps;
    


{% endhighlight %}
 
{% endtabs %}

![](Images/Maps.png)

## Steps for adding shapefiles 

Android    
     
  * Add necessary shape files to the Assets folder of ProjectFileName.Droid.                       	
    
  * Right click on the added shape file and navigate to properties. 
   	
  * Choose `AndroidAsset` option under BuildAction of respective shape file. 

iOS   
  
  * Add necessary shape files to the Assets folder of ProjectFileName.iOS.  
    
  * Right click on the added shape file and navigate to properties. 
    
  * Choose `BundleResource` option under BuildAction of respective shape file.


 UWP
   
  * Add necessary shape files to the Assets folder of ProjectFileName.UWP.
     
  * Right click on the added shape file and navigate to properties. 
 
  * Choose `EmbeddedResource` option under BuildAction of respective shape file.


## GeoJson Support

 The Maps control supports reading and loading GeoJson files. The GeoJson file contains attribute information for the spatial features and coordinates in a data set. 
 
{% tabs %}

{% highlight xaml %}
        
       <SfMaps:ShapeFileLayer Uri="world.json">
       </SfMaps:ShapeFileLayer>               	  


{% endhighlight %}


 {% highlight c# %}
     
      ShapeFileLayer layer=new ShapeFileLayer();
      layer.Uri = "world.json";

{% endhighlight %}

{% endtabs %}

## Adding Marker to the Maps

Markers can be added into the shape layers. The below code snippets enables you to do so.

{% tabs %}

{% highlight xaml %}

    <SfMaps:ShapeFileLayer:MapMarker>
                
        <SfMaps:MapMarker Label = "California" Latitude = "37" Longitude = "-120"/>                
                    
    </SfMaps:ShapeFileLayer:ShapeSetting>	              

{% endhighlight %}

{% highlight c# %}
	

            
    SfMaps maps = new SfMaps ();
    ShapeFileLayer layer = new ShapeFileLayer ();
    MapMarker marker = new MapMarker ();
    marker.Label = "California";
    marker.Latitude = 37;
    marker.Longitude = -120;
    layer.Markers.Add (marker);  
    maps.Layers.Add (layer);            
    this.ContentView=maps;
    


{% endhighlight %}

{% endtabs %}

![](Images/Markers.png) 