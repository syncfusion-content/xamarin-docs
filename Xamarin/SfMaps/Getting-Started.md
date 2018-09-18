---
layout: post
title: Getting Started with Syncfusion Maps control for Xamarin.Forms
description: A quick tour about Syncfusion maps control in Xamarin.Forms platform
platform: xamarin
control: SfMaps 
documentation: ug
---

# Getting Started

This section explains the steps required to configure the maps control and customize its elements.

## Adding SfMaps reference

Syncfusion components for Xamarin.Forms are available in [nuget.org](https://www.nuget.org/). To add maps to your project, open the NuGet package manager in Visual Studio, search for [syncfusion.xamarin.sfmaps](https://www.nuget.org/packages/Syncfusion.Xamarin.SfMaps), and then install it.

![](Images/maps.png)

To learn more about obtaining our components, refer to these links for [Mac](https://help.syncfusion.com/xamarin/introduction/download-and-installation/mac) and [Windows](https://help.syncfusion.com/xamarin/introduction/download-and-installation/windows). If you prefer to manually reference the assemblies instead of using NuGet, refer to this [documentation](https://help.syncfusion.com/xamarin/introduction/control-dependencies#sfmaps) to learn about the dependent assemblies.

I> After adding the reference, an additional step is required for iOS and UWP projects. Create an instance of the `SfMapsRenderer` in iOS and UWP projects as described in this [KB article.](https://www.syncfusion.com/kb/8603).

I> For UWP alone, one more additional step is required if the project is built-in release mode with .NET Native tool chain enabled. You can refer to this [KB article](https://www.syncfusion.com/kb/8604) for more details.

## Adding namespace

Add the following namespace.

{% tabs %}

{% highlight xaml %}

xmlns:maps="clr-namespace:Syncfusion.SfMaps.XForms;assembly=Syncfusion.SfMaps.XForms"

{% endhighlight %}

{% highlight c# %}

using Syncfusion.SfMaps.XForms;

{% endhighlight %}

{% endtabs %}

## Initializing maps

Create an instance for the maps control, and add it as content.

{% tabs %}

{% highlight xaml %}

<maps:SfMaps >
  
</maps:SfMaps>

{% endhighlight %}

{% highlight c# %}

SfMaps map = new SfMaps();
	
this.Content = map;

{% endhighlight %}

{% endtabs %}

## Adding layers

The maps control is maintained through [`layers`](https://help.syncfusion.com/cr/cref_files/xamarin/Syncfusion.SfMaps.XForms~Syncfusion.SfMaps.XForms.SfMaps~Layers.html). It can accommodate one or more shape file layers.

{% tabs %}

{% highlight xaml %}

<maps:SfMaps>

<maps:SfMaps.Layers>

<maps:ShapeFileLayer/>

</maps:SfMaps.Layers>  

</maps:SfMaps>  

{% endhighlight %}

{% highlight c# %}

SfMaps map = new SfMaps();

ShapeFileLayer layer = new ShapeFileLayer();

map.Layers.Add(layer);
	
this.Content = map;

{% endhighlight %}

{% endtabs %}

## Adding shape files

A shape file is a set of files that is stored in a non-topological geometry with the attribute information for the spatial features and records in a data set.

The maps control supports reading and loading the shape files. A shape file can be a set of files or a single file. Generally, a shape file contains the following files:

* Main file (.shp)
* dBase file (.dbf)

### Android

* Add necessary shape files to the Assets folder of ProjectFileName.Droid.
* Right-click the added shape file, and navigate to properties.
* Choose the `AndroidAsset` option under BuildAction of respective shape file.

### iOS

* Add necessary shape files to the Resources folder of ProjectFileName.iOS.
* Right-click the added shape file, and navigate to properties.
* Choose the `BundleResource` option under BuildAction of respective shape file.

### UWP

* Add necessary shapes files in a folder, and name it as `ShapeFiles`. Add this `ShapeFiles` folder into the `Assets` folder of ProjectFileName.UWP.
* Right-click the added shape file, and navigate to properties.
* Choose the `EmbeddedResource` option under BuildAction of respective shape file.

The [`Uri`](https://help.syncfusion.com/cr/cref_files/xamarin/Syncfusion.SfMaps.XForms~Syncfusion.SfMaps.XForms.ShapeFileLayer~Uri.html) property in shape file layer is used to retrieve the location of the shape file that is added.

{% tabs %}

{% highlight xaml %}

    <maps:SfMaps x:Name="sfmap"  BackgroundColor="White" >
                <maps:SfMaps.Layers >
                    <maps:ShapeFileLayer Uri="usa_state.shp"  >                        
                    </maps:ShapeFileLayer>
                </maps:SfMaps.Layers>
    </maps:SfMaps>     

{% endhighlight %}

{% highlight c# %}
	
SfMaps map = new SfMaps();
map.BackgroundColor = Color.White;
ShapeFileLayer layer = new ShapeFileLayer();
layer.Uri = "usa_state.shp";
map.Layers.Add(layer);
this.Content = map;

{% endhighlight %}
 
{% endtabs %}

The following screenshot illustrates the result of adding shape files.

![](Images/GettingStartedimg1.jpeg)

## GeoJSON support

The maps control supports reading and loading the GeoJSON files. The GeoJSON file contains attribute information for the spatial features and coordinates in a dataset.
 
{% tabs %}

{% highlight xaml %}
        
 <maps:ShapeFileLayer Uri="usa_state.json">                        
 </maps:ShapeFileLayer>
					
{% endhighlight %}

{% highlight c# %}
     
 ShapeFileLayer layer = new ShapeFileLayer();
 layer.Uri = "usa_state.json";
			
{% endhighlight %}

{% endtabs %}

## Data binding

Data can be bound to the shape file layer using the [`ItemsSource`](https://help.syncfusion.com/cr/cref_files/xamarin/Syncfusion.SfMaps.XForms~Syncfusion.SfMaps.XForms.ShapeFileLayer~ItemsSource.html), [`ShapeIDPath`](https://help.syncfusion.com/cr/cref_files/xamarin/Syncfusion.SfMaps.XForms~Syncfusion.SfMaps.XForms.ShapeFileLayer~ShapeIDPath.html), and [`ShapeIdTableField`](https://help.syncfusion.com/cr/cref_files/xamarin/Syncfusion.SfMaps.XForms~Syncfusion.SfMaps.XForms.ShapeFileLayer~ShapeIDTableField.html) properties.

The [`Populate data`](https://help.syncfusion.com/xamarin/SfMaps/PopulateData) section gives the detailed explanation of data binding.

{% tabs %}

{% highlight xaml %}

<maps:SfMaps.Layers >
<maps:ShapeFileLayer Uri="usa_state.shp" ItemsSource="{Binding Data}"
                                          ShapeIDPath="State" ShapeIDTableField="STATE_NAME" >
</maps:ShapeFileLayer>
                </maps:SfMaps.Layers>        

{% endhighlight %}

{% highlight c# %}
	
ShapeFileLayer layer = new ShapeFileLayer();
            layer.Uri = "usa_state.shp";
            layer.ItemsSource =viewModel.Data;
            layer.ShapeIDTableField = "STATE_NAME";
            layer.ShapeIDPath = "State";			
            map.Layers.Add(layer);

{% endhighlight %}

{% endtabs %}

## Adding markers

Markers are used to identify the shapes. They can be added to the shape file layers as demonstrated in the following code sample. Markers can be customized using the [`MarkerSettings`](https://help.syncfusion.com/cr/cref_files/xamarin/Syncfusion.SfMaps.XForms~Syncfusion.SfMaps.XForms.ShapeFileLayer~MarkerSettings.html) property in the shape file layer.

The detailed explanation of marker and its customization are provided under [`Markers`](https://help.syncfusion.com/xamarin/SfMaps/Markers) section.

{% tabs %}

{% highlight xaml %}

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

## Color mapping

The color mapping support allows you customize the shape colors based on the underlying value of shape received from the bound data. Both the range color mapping and equal color mapping are supported in maps.

The detailed explanation of color mapping is provided in [`colorMapping`](https://help.syncfusion.com/xamarin/SfMaps/ColorMapping) section.

{% tabs %}

{% highlight xaml %}

<maps:ShapeSetting.ColorMappings>
<maps:EqualColorMapping Color="#D84444" LegendLabel="Romney" Value = "Romney"></maps:EqualColorMapping>
<maps:EqualColorMapping Color="#316DB5" LegendLabel="Obama" Value="Obama"></maps:EqualColorMapping>
</maps:ShapeSetting.ColorMappings>         

{% endhighlight %}

{% highlight c# %}
	
 EqualColorMapping colorMapping = new EqualColorMapping();
            colorMapping.Color = Color.FromHex("#D84444");
            colorMapping.LegendLabel = "Romney";
            colorMapping.Value = "Romney";

            EqualColorMapping colorMapping1 = new EqualColorMapping();
            colorMapping1.Color = Color.FromHex("#316DB5");
            colorMapping1.LegendLabel = "Obama";
            colorMapping1.Value = "Obama";

            ShapeSetting shapeSetting = new ShapeSetting();           
            shapeSetting.ColorMappings.Add(colorMapping);
            shapeSetting.ColorMappings.Add(colorMapping1);

{% endhighlight %}

{% endtabs %}
 
## Adding legends

Legends interpret what the map displays. They can be added to the shape file layer as demonstrated in the following code sample. Legends will be displayed based on the data bound to the layer, and color mapping plays a major role in enabling legends. 

The detailed explanation of legend is provided under [`Legend`](https://help.syncfusion.com/xamarin/SfMaps/Legend) section.

{% tabs %}

{% highlight xaml %}

<maps:ShapeFileLayer.LegendSettings>
   <maps:MapLegendSetting ShowLegend="true" LegendPosition="75,90"/>
</maps:ShapeFileLayer.LegendSettings>

{% endhighlight %}

{% highlight c# %}
	
MapLegendSetting setting = new MapLegendSetting();
setting.ShowLegend = true;
setting.LegendPosition = new Point(75, 90);
layer.LegendSettings = setting;  

{% endhighlight %}

{% endtabs %}

The following code sample gives you the complete code for map with markers and legends.

{% tabs %}

{% highlight xaml %}

<maps:SfMaps x:Name="sfmap"  BackgroundColor="White"  >
                <maps:SfMaps.Layers >
                    <maps:ShapeFileLayer Uri="usa_state.shp" ShapeIDPath="State" 
                                         ShapeIDTableField="STATE_NAME" 
                                       ItemsSource="{Binding Data}"
                                         >
                        <maps:ShapeFileLayer.Markers>
                            <maps:MapMarker Label = "California" Latitude = "37" Longitude = "-120">
                            </maps:MapMarker>
                        </maps:ShapeFileLayer.Markers>
                        
                        <maps:ShapeFileLayer.MarkerSettings>
                            
                            <maps:MapMarkerSetting IconColor="LimeGreen" IconSize="25" 
                                                   LabelColor="White" LabelSize="20">
                            </maps:MapMarkerSetting>

                        </maps:ShapeFileLayer.MarkerSettings>

                        <maps:ShapeFileLayer.ShapeSettings>
                            <maps:ShapeSetting ShapeColorValuePath="Candidate" ShapeValuePath="Candidate"   >
                                <maps:ShapeSetting.ColorMappings>

                                    <maps:EqualColorMapping Color="#D84444" LegendLabel="Romney" Value = "Romney"></maps:EqualColorMapping>
                                    <maps:EqualColorMapping Color="#316DB5" LegendLabel="Obama" Value="Obama"></maps:EqualColorMapping>
                                </maps:ShapeSetting.ColorMappings>
                            </maps:ShapeSetting>
                        </maps:ShapeFileLayer.ShapeSettings>

                        <maps:ShapeFileLayer.LegendSettings>
                            <maps:MapLegendSetting ShowLegend="True"  
                                                   LegendPosition="30,70">
                                <maps:MapLegendSetting.IconSize>
                                    <Size Width="20" Height="20"></Size>
                                </maps:MapLegendSetting.IconSize>
                            </maps:MapLegendSetting>
                        </maps:ShapeFileLayer.LegendSettings>
                        
                    </maps:ShapeFileLayer>
                </maps:SfMaps.Layers>
            </maps:SfMaps>

{% endhighlight %}

{% highlight c# %}

SfMaps map = new SfMaps();

            map.BackgroundColor = Color.White;
            ShapeFileLayer layer = new ShapeFileLayer();
            layer.Uri = "usa_state.shp";
            layer.ItemsSource = viewModel.Data;
            layer.ShapeIDTableField = "STATE_NAME";
            layer.ShapeIDPath = "State";
            map.Layers.Add(layer);

            MapLegendSetting legendSetting = new MapLegendSetting();
            legendSetting.ShowLegend = true;
            legendSetting.LegendPosition = new Point(30, 70);
            legendSetting.IconSize = new Size(20, 20);
            layer.LegendSettings = legendSetting;

            MapMarker marker = new MapMarker();
            marker.Label = "California";
            marker.Latitude = "37";
            marker.Longitude = "-120";
            layer.Markers.Add(marker);

            MapMarkerSetting markerSetting = new MapMarkerSetting();
            markerSetting.IconColor = Color. LimeGreen;
            markerSetting.IconSize = 25;
            markerSetting.LabelColor = Color.White;
            markerSetting.LabelSize = 20;
            layer.MarkerSettings = markerSetting;

            EqualColorMapping colorMapping = new EqualColorMapping();
            colorMapping.Color = Color.FromHex("#D84444");
            colorMapping.LegendLabel = "Romney";
            colorMapping.Value = "Romney";

            EqualColorMapping colorMapping1 = new EqualColorMapping();
            colorMapping1.Color = Color.FromHex("#316DB5");
            colorMapping1.LegendLabel = "Obama";
            colorMapping1.Value = "Obama";

            ShapeSetting shapeSetting = new ShapeSetting();
            shapeSetting.ShapeValuePath = "Candidate";
            shapeSetting.ShapeColorValuePath = "Candidate";
            shapeSetting.ColorMappings.Add(colorMapping);
            shapeSetting.ColorMappings.Add(colorMapping1);
            layer.ShapeSettings = shapeSetting;

            this.Content = map;

{% endhighlight %}

{% endtabs %}

The following screenshot illustrates the result of the above code sample.

![](Images/GettingStartedimg2.PNG) 

You can download the complete [Getting started](http://www.syncfusion.com/downloads/support/directtrac/general/ze/MapsSample-1975206216.zip) sample.


