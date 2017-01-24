---
layout: post
title: Interactive features of Maps control for Xamarin.Forms
description: How to interact with Map elements effectively
platform: xamarin
control: SfMaps
documentation: ug
---

# User Interaction

Options like zooming, panning, and map selection enables the effective interaction on Map elements.

## Map Selection

Each shape in the Map can be selected and deselected during interaction with the shapes. 

The `SelectedShapeColor` property is used to get or set the selected shape color. `SelectionStrokeWidth` property is used to customize the selected shape border.

You can select the shape by tapping the shape. The Selection is enabled by the `EnableSelection` property of shape layer. When `EnableSelection` is set to false, the shapes cannot be selected. 

{% tabs %}
{% highlight xaml %}

        <SfMaps:ShapeFileLayer>
                <SfMaps:ShapeFileLayer EnableSelection="true"/>
                                      
                <SfMaps:ShapeFileLayer:ShapeSetting>
                        <SfMaps:ShapeSetting SelectedShapeColor="#BC5353" >                                
                </SfMaps:ShapeFileLayer:ShapeSetting>
        </SfMaps:ShapeFileLayer>    

{% endhighlight %}

{% highlight c# %}

      layer.EnableSelection = true;
      ShapeSetting setting = new ShapeSetting ();
      setting.SelectedShapeColor = Color.FromHex("#BC5353");
      layer.ShapeSettings = setting;

{% endhighlight %}
{% endtabs %}

![](Images/Selection.png)  

## Zooming

The zooming feature enables you to zoom in and out the Map to show in-depth information. It is controlled by the `level` property of the Map. When the zoom level of the Map control is increased, the Map is zoomed in. When the zoom level is decreased, then the Map is zoomed out.

The following properties are related to the zooming feature of the Maps control:

1. ZoomLevel

2. EnableZoom

3. MinZoom

4. MaxZoom

### Level

The `ZoomLevel` property determines the Map’s scale size when zooming. The default value of `ZoomLevel` is 1. 

N>level cannot be less than 1

### EnableZoom

The `EnableZoom` property enables or disables the zooming feature. 

### MinZoom

The `MinZoom` property is used to set the minimum zoom level of the Map. 

### MaxZoom

The `MaxZoom` property is used to set the maximum zoom level of the Map.

### EnablePanning

The panning feature enables the Map navigation. The `EnablePan` property is used to enable or disable the panning support.

{% tabs %}
{% highlight xaml %}

        <syncfusion:SfMap ZoomLevel="2" MinZoom="1" MaxZoom="10" EnableZoom="True">                

        </syncfusion:SfMap >       

{% endhighlight %}

{% highlight c# %}

    maps.MinZoom = 1;  
    maps.MaxZoom = 10;
    maps.ZoomLevel = 2;
    maps.EnbaleZoom = true;


{% endhighlight %}
{% endtabs %}




