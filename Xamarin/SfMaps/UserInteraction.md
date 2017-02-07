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

## Map selection
  
  Each shape in the map can be selected and unselected when interacted with shapes. There are two ways to select the map shapes.

  * Single Selection

  * Multi Selection

  The selected map shapes is differentiate by its fill. `SelectedShapeColor` of ShapeSetting is the API that is used to get or set the selected shape color. `SelectionStrokeWidth` property is used to customize the selected shape border.
  

### Single Selection
     
 Single selection allows only one map shape to be selected at a time. You can select the shape by tapping on the shape.By default single selection is enabled when EnableSelection is set to true. Single selection is enabled by "SelectionMode.Single ” property of ShapeFileLayer. When EnableSelection is set to true, then the mapshape can be selected. When it is set to false, the shapes cannot be selected. When any other shape or the map area is selected, then the shape that is already selected is unselected.

{% tabs %}

{% highlight xaml %}
        
       <SfMaps:ShapeFileLayer EnableSelection="true" SelectionMode="Single">
       <SfMaps:ShapeFileLayer:ShapeSetting>
       <SfMaps:ShapeSetting SelectedShapeColor="#BC5353" >                                
       </SfMaps:ShapeFileLayer:ShapeSetting>
       </SfMaps:ShapeFileLayer>               	  


{% endhighlight %}


 {% highlight c# %}
     
      ShapeFileLayer layer = new ShapeFileLayer();
      layer.SelectionMode = SelectionMode.Single;
      layer.EnableSelection = true;
      ShapeSetting setting = new ShapeSetting ();
      setting.SelectedShapeColor = Color.FromHex("#BC5353");
      layer.ShapeSettings = setting;

{% endhighlight %}

{% endtabs %}


![](Images/Selection.png)


### Multi Selection
     
   Multi selection allows to select multiple mapshapes at a time. You can select the many mapshape by tapping on the shape. To enable this feature, set the selectionMode property as “multiple” along with the enableSelection property is true. When EnableSelection is set to false, the shapes cannot be selected. 

{% tabs %}

{% highlight xaml %}
        
       <SfMaps:ShapeFileLayer EnableSelection="true" SelectionMode="Multiple">
       <SfMaps:ShapeFileLayer:ShapeSetting>
       <SfMaps:ShapeSetting SelectedShapeColor="#BC5353" >                                
       </SfMaps:ShapeFileLayer:ShapeSetting>
       </SfMaps:ShapeFileLayer>               	  


{% endhighlight %}


 {% highlight c# %}
     
      ShapeFileLayer layer=new ShapeFileLayer();
      layer.SelectionMode = SelectionMode.Multiple;
      layer.EnableSelection = true;
      ShapeSetting setting = new ShapeSetting ();
      setting.SelectedShapeColor = Color.FromHex("#BC5353");
      layer.ShapeSettings = setting;

{% endhighlight %}

{% endtabs %}

### Selected Items
    
 SelectedItems property allows to select shapes without tapping or touching shapes by calling SelectedItems.Add(Object)  and also remove the SelectedItems by calling  SelectedItems.Remove(object).
    
{% tabs %}

{% highlight c# %}
     
      var model = GetDataSource();
      ShapeFileLayer layer=new ShapeFileLayer();
      layer.ItemsSource=model;
      SelectedItemButton.Clicked += (sender, e) =>
       {
        layer.SelectedItems.Add(model[0]);
       };
      RemoveItemButton.Clicked += (sender, e) =>
       {
        layer.SelectedItems.Remove(model[0]);
       };


 {% endhighlight %}

{% endtabs %}


## Zooming

The zooming feature enables you to zoom in and out the Map to show in-depth information. It is controlled by the `level` property of the Map. When the zoom level of the Map control is increased, the Map is zoomed in. When the zoom level is decreased, then the Map is zoomed out.

The following properties are related to the zooming feature of the Maps control:

1. ZoomLevel

2. EnableZooming

3. MinZoom

4. MaxZoom

### Level

The `ZoomLevel` property determines the Map’s scale size when zooming. The default value of `ZoomLevel` is 1. 

N>level cannot be less than 1

### EnableZoom

The `EnableZooming` property enables or disables the zooming feature. 

### MinZoom

The `MinZoom` property is used to set the minimum zoom level of the Map. 

### MaxZoom

The `MaxZoom` property is used to set the maximum zoom level of the Map.

### EnablePanning

The panning feature enables the Map navigation. The `EnablePanning` property is used to enable or disable the panning support.

{% tabs %}

{% highlight xaml %}

        <syncfusion:SfMap ZoomLevel="2" MinZoom="1" MaxZoom="10" EnablePanning="true" EnableZooming="true">                

        </syncfusion:SfMap >       

{% endhighlight %}

{% highlight c# %}

    maps.MinZoom = 1;  
    maps.MaxZoom = 10;
    maps.ZoomLevel = 2;
    maps.EnableZooming = true;
    maps.EnablePanning=true;

{% endhighlight %}

{% endtabs %}




