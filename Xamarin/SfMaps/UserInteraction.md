---
layout: post
title: User Interaction | SfMaps |Xamarin | Syncfusion
description: user interaction
platform: xamarin
control: SfMaps
documentation: ug
---

#User Interaction

Options like zooming, panning, and map selection enables the effective interaction on Map elements.

## Map Selection

Each shape in the Map can be selected and deselected during interaction with the shapes. 

The `SelectedShapeColor` property is used to get or set the selected shape color. `SelectionStrokeWidth` property is used to customize the selected shape border.

You can select the shape by tapping the shape. The Selection is enabled by the `EnableSelection` property of shape layer. When `EnableSelection` is set to false, the shapes cannot be selected. 

{% tabs %}
{% highlight Xamarin.Android %}

        layer.EnableSelection = true;
        ShapeSetting setting = new ShapeSetting ();
        setting.SelectedShapeColor = Color.ParseColor("#BC5353");
        layer.ShapeSettings = setting;

{% endhighlight %}

{% highlight Xamarin.iOS %}

        layer.EnableSelection = true;
        SFShapeSetting setting = new SFShapeSetting ();
        setting.SelectedShapeColor = UIColor.FromRGB (0xBC, 0x53, 0x53);
        layer.ShapeSettings = setting;

{% endhighlight %}
{% endtabs %}

![](images/selection_android.png)  

## Zooming

The zooming feature enables you to zoom in and out the Map to show in-depth information. It is controlled by the `level` property of the Map. When the zoom level of the Map control is increased, the Map is zoomed in. When the zoom level is decreased, then the Map is zoomed out.

### Properties

The following properties are related to the zooming feature of the **Maps** control:

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

###EnablePanning

The panning feature enables the Map navigation. The `EnablePan` property is used to enable or disable the panning support.

{% tabs %}
{% highlight Xamarin.Android %}

        maps.MinZoom = 1;
        maps.MaxZoom = 10;
        maps.ZoomLevel = 2;
        maps.EnbaleZoom = true;


{% endhighlight %}

{% highlight Xamarin.iOS %}

        maps.MinZoom = 1;
        maps.MaxZoom = 10;
        maps.ZoomLevel = 2;
        maps.EnbaleZoom = true;

{% endhighlight %}
{% endtabs %}