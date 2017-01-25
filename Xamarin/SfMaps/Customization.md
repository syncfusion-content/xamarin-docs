---
layout: post
title: Shape Customization of Syncfusion Maps control for Xamarin.Forms 
description: How to customize the shape and color in maps control
platform: xamarin
control: SfMaps
documentation: ug
---

# Customization

Maps control supports color customization to determine the exact combination of colors for shapes displayed in Maps and tooltip support to display additional information of shape data.

## Shape Settings

The shapeSettings defines the basic customization settings of shapes in the map.

* `ShapeFill` - It is used to set the fill color of the shapes in the map.
* `ShapeStroke` - It is used to set the border color of the shape in the map.
* `ShapeStrokeThickness` - It is used to set the border thickness of the shape in the map.
* `SelectedShapeColor` - It is used to set the selection color for shapes in the map.

{% tabs %}
{% highlight xaml %}

        <SfMaps:ShapeFileLayer:ShapeSetting>
            <SfMaps:ShapeSetting ShapeFill="#9CBF4E" SelectedShapeColor="#BC5353" 
            ShapeStroke="white" ShapeStrokeThickess="1"/>
        </SfMaps:ShapeFileLayer:ShapeSetting>
                      
      
{% endhighlight %}

{% highlight c# %}

         ShapeSetting setting = new ShapeSetting ();
         setting.ShapeFill = Color.ParseColor("#9CBF4E");
         setting.SelectedShapeColor = Color.ParseColor("#BC5353");
         setting.ShapeStroke = Color.White;
         setting.ShapeStrokeThickess = 1;
         layer.ShapeSettings = setting;

{% endhighlight %}
{% endtabs %}

![](Images/Selection.png)  

## Color Mapping

The Color Mapping support enables the customization of shape colors based on the underlying value of shape received from bounded data.

* `ColorValuePath` - It renders the field value that is to be fetched from data for each shape used for determining the shape color.
* `ValuePath` - It renders the field value that is to be fetched from data for each shape. This support also provides a tree map-like impact on the map UI. The various types of Color Mapping supported in maps are listed as follows.

### Equal Color Mapping

The `EqualColorMapping` is used to differentiate the shape’s fill based on its underlying value and color. The properties of equalColorMapping is listed in the following table.

<table>
<tr>
<th>
<br/>Property<br/><br/></th><th>
Type<br/><br/></th><th>
Description<br/><br/></th></tr>
<tr>
<td>
Value<br/><br/></td><td>
String<br/><br/></td><td>
Gets or sets the value.<br/><br/></td></tr>
<tr>
<td>
Color<br/><br/></td><td>
String<br/><br/></td><td>
Gets or sets the color for mapping.<br/><br/></td></tr>
</table>

{% tabs %}
{% highlight xaml %}
        
    <SfMaps:ShapeFileLayer>
        <SfMaps:ShapeFileLayer ShapeIdTableField="STATE_NAME" ShapeIdPath="State"/>
                                      
        <SfMaps:ShapeFileLayer:ShapeSetting>
            <SfMaps:ShapeSetting ShapeColorValuePath="Candidate" >
            <SfMaps:ShapeSetting.ColorMappings>
                    
                <sfMaps:EqualColorMapping Value="Obama" LegendLabel="Obama" Color="#316DB5"/>
                <sfMaps:EqualColorMapping Value="Romney" LegendLabel="Romney" Color="#D84444"/>
                
            </SfMaps:ShapeSetting.ColorMappings>
                    
        </SfMaps:ShapeFileLayer:ShapeSetting>
    </SfMaps:ShapeFileLayer>               	  


{% endhighlight %}

{% highlight c# %}

    {

    //..           
    layer.ShapeIdTableField ="STATE_NAME";
    layer.ShapeIdPath ="State";
    layer.DataSource = GetDataSource (); 
    layer.ShapeSettings.ShapeColorValuePath ="Candidate";
     SetColorMapping(layer.ShapeSettings);
    //..
    }

   void SetColorMapping(ShapeSetting setting)
   {

    List<ColorMapping> colorMappings= new List<ColorMapping>();

    EqualColorMapping colorMapping1= new EqualColorMapping();
    colorMapping1.Value= "Obama";
    colorMapping1.LegendLabel= "Obama";
    colorMapping1.Color =Color.ParseColor("#316DB5");
    colorMappings.Add(colorMapping1);

    EqualColorMapping colorMapping2= new EqualColorMapping();
    colorMapping2.Value= "Romney";
    colorMapping2.LegendLabel= "Romney";
    colorMapping2.Color =Color.ParseColor("#D84444");
    colorMappings.Add(colorMapping2);

    setting.ColorMapping = colorMappings;
  }


{% endhighlight %}
{% endtabs %}

![](Images/customization.png)  


### Color Palette

When `AutoFillColors` property is set to true, shapes are filled with default colors from built-in palettes or custom palette.


{% tabs %}
{% highlight xaml %}
           
                                      
        <SfMaps:ShapeFileLayer:ShapeSetting AutoFillColors="true"/>            
            

{% endhighlight %}

{% highlight c# %}
        
      layer.ShapeSettings.AutoFillColors = true;

{% endhighlight %}
{% endtabs %}

![](Images/palettes.png)  


### Item Templates

Item Templates for Map Markers The maps control provides item template support for marker items, allowing custom templates to be created with any type of view element.

{% highlight xaml %}

    <maps:ShapeFileLayer.MarkerTemplate>
      <DataTemplate >
         <StackLayout  Padding="-12,-12,0,0" IsClippedToBounds="false" HorizontalOptions="StartAndExpand" VerticalOptions="Center" HeightRequest="60" WidthRequest="60"  >
           <Image Source="{Binding ImageName}" Scale="1" Aspect="AspectFit " HorizontalOptions="StartAndExpand" VerticalOptions="Center"  HeightRequest="15" WidthRequest="23"   />    
         </StackLayout>
      </DataTemplate>
    </maps:ShapeFileLayer.MarkerTemplate>
 
{% endhighlight %}

![](Images/MarkerTemplate.png)  

### Geometry Type
  
  Geometry type property specifies the maps control supports any type of shape files that is suppose if shape file  contains  normal or geographic latitude and longitude points it supports both  type of shpae file.
Geometry property has the following two options:
           
 * Points

 * GeographicPoints

The default GeometryType is Geographic Points.it shows the GeographicPoints shapes.

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

### MapPointIcon
    MapPointIcon Property is used for  points GeometryType shape file.it specifies the customized  shapes for points GeometryType shape.
    It can be customized by five shapes.
 
 * Circle
 
 * Rectangle  

 * Square

 * Diamond

 * Star



{% tabs %}

{% highlight xaml %}
        
       <SfMaps:ShapeFileLayer Uri="world1.shp"   MapPointIcon="Circle">
        </SfMaps:ShapeFileLayer>               	  


{% endhighlight %}


 {% highlight c# %}
     
      ShapeFileLayer layer=new ShapeFileLayer();
      layer.MapPointIcon = MapPointIcon.Circle;

{% endhighlight %}

{% endtabs %}

### Map selection
  
  Each shape in the map can be selected and unselected when interacted with shapes. There are two ways to select the map shapes:

  * Single Selection

  * Multi Selection

  The selected map shapes is differentiate by its fill. “SelectedShapeColor” of ShapeSetting is the API that is used to get or set the selected shape color.
All selected shapes available in the “SelectedMapShapes” of ShapeFileLayer.


### Single Selection
     
     Single selection allows only one map shape to be selected at a time. You can select the shape by tapping on the shape.By default single selection is enabled when EnableSelection is set to true. Single selection is enabled by "SelectionMode.Single ” property of ShapeFileLayer. When EnableSelection is set to true, then the map can be selected. When it is set to false, the shapes cannot be selected. When any other shape or the map area is selected, then the shape that is already selected is unselected.

{% tabs %}

{% highlight xaml %}
        
       <SfMaps:ShapeFileLayer EnableSelection="true" SelectionMode="Single">
        </SfMaps:ShapeFileLayer>               	  


{% endhighlight %}


 {% highlight c# %}
     
      ShapeFileLayer layer=new ShapeFileLayer();
      layer.SelectionMode = SelectionMode.Single;
      layer.EnableSelection = true;

{% endhighlight %}

{% endtabs %}

### Multi Selection
     
   Multi selection allows to select multiple mapshapes at a time. You can select the many mapshape by tapping on the shape. To enable this feature, set the selectionMode property as “multiple” along with the enableSelection property is true. When EnableSelection is set to false, the shapes cannot be selected. 

{% tabs %}

{% highlight xaml %}
        
       <SfMaps:ShapeFileLayer EnableSelection="true" SelectionMode="Multiple">
        </SfMaps:ShapeFileLayer>               	  


{% endhighlight %}


 {% highlight c# %}
     
      ShapeFileLayer layer=new ShapeFileLayer();
      layer.SelectionMode = SelectionMode.Multiple;
      layer.EnableSelection = true;

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


      



### GeoJSON Support

 The Maps control supports reading and loading GeoJson files.A GeoJson file contains  attribute information for the spatial features and coordinates in a data set. 
 
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

### MapMarkerIcon
  The markers property has a list of objects that contains the data for Annotation. By default, it displays the bound data at the specified latitude and longitude.   
 MapMarkerIcon can be  customized into four shapes.

 *  Circle

 *  Square

 *  Diamond   

 *  Rectangle

{% tabs %}

{% highlight xaml %}
   
    <SfMaps:ShapeFileLayer Uri="world1.shp"  >
    <SfMaps:ShapeFileLayer.MarkerSettings > 
	<SfMaps:MapMarkerSetting MarkerIcon="Rectangle"/>
    </SfMaps:ShapeFileLayer.MarkerSettings>
    <SfMaps:ShapeFileLayer.Markers >
	<SfMaps:MapMarker  Label = "California" Latitude = "37" Longitude = "-120"/>
    <SfMaps:MapMarker  Label="Brazil" Latitude="-15.7833" Longitude= "-47.8667" />
    <SfMaps:MapMarker Label="India" Latitude="21.0000" Longitude= "78.0000" />
    <SfMaps:MapMarker Label="China" Latitude="35.0000" Longitude= "103.0000" />
    <SfMaps:MapMarker Label="Indonesia" Latitude="-6.1750" Longitude= "106.8283" /> 
    </SfMaps:ShapeFileLayer.Markers>
    </SfMaps:ShapeFileLayer>

{% endhighlight %}


 {% highlight c# %}
     
            ShapeFileLayer layer = new ShapeFileLayer ();
			layer.Uri ="world1.shp";
		    MapMarkerSetting setting = new MapMarkerSetting();
			setting.MarkerIcon = MapMarkerIcon.Diamond;
			layer.MarkerSettings = setting;
			MapMarker usa= new MapMarker();
			usa.Latitude ="38.8833";
			usa.Longitude="-77.0167";
			usa.Label= "United States";
		
			layer.Markers.Add(usa);


			MapMarker brazil= new MapMarker();
			brazil.Latitude="-15.7833";
			brazil.Longitude="-47.8667";
			brazil.Label = "Brazil";
			layer.Markers.Add(brazil);

{% endhighlight %}

{% endtabs %} 
    
   



  



