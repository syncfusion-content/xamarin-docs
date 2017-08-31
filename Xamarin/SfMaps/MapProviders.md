---
layout: post
title: Map Providers of Maps control for Xamarin.Forms
description: How to add geometry type shapefiles  effectively
platform: xamarin
control: SfMaps
documentation: ug
---

# Map Providers

Maps control supports any type of shapefiles like geographic,normal type given by the MapProviders .It can be enabled by using GeometryType property.


## Geometry Type
  
  Geometry type property specifies the maps control supports any type of shape files that is suppose if shape file  contains  normal or geographic latitude and longitude points it supports both  type of shape file.
Geometry property has the following two options:
           
 * Points

 * GeographicPoints

The default GeometryType is Geographic Points.It shows the GeographicPoints shapes.

{% tabs %}

{% highlight xaml %}
        
       <SfMaps:ShapeFileLayer Uri="world1.shp" GeometryType="GeographicPoints">
       </SfMaps:ShapeFileLayer>               	  


{% endhighlight %}


 {% highlight c# %}
     
      ShapeFileLayer layer=new ShapeFileLayer();
      layer.GeometryType = GeometryType.GeographicPoints;
 
{% endhighlight %}

{% endtabs %}

The following code example shows how to set GeometryType as Points.Points GeometryType property shows Points type shapes.

{% tabs %}

{% highlight xaml %}
        
    <SfMaps:ShapeFileLayer Uri="world1.shp" GeometryType="Points">
    </SfMaps:ShapeFileLayer>               	  


{% endhighlight %}


 {% highlight c# %}
      
      ShapeFileLayer layer=new ShapeFileLayer();
      layer.GeometryType = GeometryType.Points;
 
{% endhighlight %}

{% endtabs %}
