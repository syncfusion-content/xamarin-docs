---
layout: post
title: Markers
description: This section describes about Map marker.
platform: xamarin
control: SfMaps
documentation: ug
---
# Markers

Markers provide some messages on the map.

Markers are set to map by using the following two ways:

1. Adding marker objects to map.
2. Defining custom marker.

## Adding marker

Any number of markers can be added to the shape file layers using the [`Markers`](https://help.syncfusion.com/cr/cref_files/xamarin/sfmaps/Syncfusion.SfMaps.XForms~Syncfusion.SfMaps.XForms.ShapeFileLayer~Markers.html#) property. Each marker object contains the following list of properties:

[`Label`](https://help.syncfusion.com/cr/cref_files/xamarin/sfmaps/Syncfusion.SfMaps.XForms~Syncfusion.SfMaps.XForms.MapMarker~Label.html#): Text that is used to display information.

[`Latitude`](https://help.syncfusion.com/cr/cref_files/xamarin/sfmaps/Syncfusion.SfMaps.XForms~Syncfusion.SfMaps.XForms.MapMarker~Latitude.html#): Latitude point that specifies the y-axis position of the marker.

[`Longitude`](https://help.syncfusion.com/cr/cref_files/xamarin/sfmaps/Syncfusion.SfMaps.XForms~Syncfusion.SfMaps.XForms.MapMarker~Longitude.html#): Longitude point that specifies the x-axis position of the marker.

{% tabs %}

{% highlight xml %}

<maps:ShapeFileLayer.Markers>

<maps:MapMarker Label = "California" Latitude = "37" Longitude = "-120">                

</maps:MapMarker>

</maps:ShapeFileLayer.Markers>

{% endhighlight %}

{% highlight c# %}

MapMarker marker = new MapMarker();

marker.Label = "California";

marker.Latitude = "37";

marker.Longitude = "-120";            

layer.Markers.Add(marker);

{% endhighlight %}

{% endtabs %}

![Marker Image](Images/Markers_img1.jpeg)


## Marker customization

A map marker can be customized using the [`MarkerSettings`](https://help.syncfusion.com/cr/cref_files/xamarin/sfmaps/Syncfusion.SfMaps.XForms~Syncfusion.SfMaps.XForms.ShapeFileLayer~MarkerSettings.html#) property in shape file layer.

### Icon customization

Shape, size, and color of a marker icon can be customized using the [`MarkerIcon`](https://help.syncfusion.com/cr/cref_files/xamarin/sfmaps/Syncfusion.SfMaps.XForms~Syncfusion.SfMaps.XForms.MapMarkerSetting~MarkerIcon.html#) , [`IconSize`](https://help.syncfusion.com/cr/cref_files/xamarin/sfmaps/Syncfusion.SfMaps.XForms~Syncfusion.SfMaps.XForms.MapMarkerSetting~IconSize.html#), and [`IconColor`](https://help.syncfusion.com/cr/cref_files/xamarin/sfmaps/Syncfusion.SfMaps.XForms~Syncfusion.SfMaps.XForms.MapMarkerSetting~IconColor.html#) properties. 

### Label customization

A marker label’s color and size can be customized using the [`LabelColor`](https://help.syncfusion.com/cr/cref_files/xamarin/sfmaps/Syncfusion.SfMaps.XForms~Syncfusion.SfMaps.XForms.MapMarkerSetting~LabelColor.html#)  and [`LabelSize`](https://help.syncfusion.com/cr/cref_files/xamarin/sfmaps/Syncfusion.SfMaps.XForms~Syncfusion.SfMaps.XForms.MapMarkerSetting~LabelSize.html#) properties.

The following code explains the marker customization.

{% tabs %}

{% highlight xml %}

<maps:ShapeFileLayer.MarkerSettings>

<maps:MapMarkerSetting IconColor="Red" IconSize="25" MarkerIcon="Diamond"

LabelColor="White" LabelSize="20">

</maps:MapMarkerSetting>

</maps:ShapeFileLayer.MarkerSettings>

{% endhighlight %}

{% highlight c# %}

MapMarkerSetting markerSetting = new MapMarkerSetting();

markerSetting.IconColor = Color.Red;

markerSetting.IconSize = 25;

markerSetting.MarkerIcon = MapMarkerIcon.Diamond;

markerSetting.LabelColor = Color.White;

markerSetting.LabelSize = 20;

layer.MarkerSettings = markerSetting;

{% endhighlight %}

{% endtabs %}

![](Images/Markers_img2.jpeg)


## Custom marker

Maps provide support for defining the custom marker using the [`MarkerTemplate`](https://help.syncfusion.com/cr/cref_files/xamarin/sfmaps/Syncfusion.SfMaps.XForms~Syncfusion.SfMaps.XForms.ShapeFileLayer~MarkerTemplate.html#) property.

{% tabs %}

{% highlight xml %}

<maps:SfMaps.Layers >

<maps:ShapeFileLayer Uri="world1.shp"  >

<maps:ShapeFileLayer.ShapeSettings>

<maps:ShapeSetting ShapeFill="Gray" />

</maps:ShapeFileLayer.ShapeSettings>

<maps:ShapeFileLayer.Markers>

<marker:CustomMarker Label="United States" Latitude="38.8833" Longitude= "-77.0167" Population="321,174,000" />

<marker:CustomMarker Label="Brazil" Latitude="-15.7833" Longitude= "-47.8667" Population="204,436,000" />

<marker:CustomMarker Label="India" Latitude="21.0000" Longitude= "78.0000" Population="1,272,470,000"/>

<marker:CustomMarker Label="China" Latitude="35.0000" Longitude= "103.0000" Population="1,370,320,000" />

<marker:CustomMarker Label="Indonesia" Latitude="-6.1750" Longitude= "106.8283" Population="255,461,700" />

</maps:ShapeFileLayer.Markers>

<maps:ShapeFileLayer.MarkerTemplate>

<DataTemplate >

<StackLayout    Padding="-12,-12,0,0" IsClippedToBounds="false" HorizontalOptions="StartAndExpand" VerticalOptions="Center" HeightRequest="60" WidthRequest="60"  >

<Image Source="{Binding ImageName}" Scale="1" Aspect="AspectFit " HorizontalOptions="StartAndExpand" VerticalOptions="Center"  HeightRequest="15" WidthRequest="23"   />

</StackLayout>

</DataTemplate>

</maps:ShapeFileLayer.MarkerTemplate>

</maps:ShapeFileLayer>

</maps:SfMaps.Layers>

{% endhighlight %}

{% highlight c# %}

public class CustomMarker : MapMarker

{

public ImageSource ImageName { get; set; }

public String Population { get; set; }

public CustomMarker()

{

ImageName = ImageSource.FromResource("MapsSample.pin.png");

}

}

{% endhighlight %}

{% endtabs %}

![](Images/Markers_img3.jpeg)