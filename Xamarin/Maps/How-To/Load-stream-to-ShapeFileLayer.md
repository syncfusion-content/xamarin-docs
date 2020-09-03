---
layout: post
title: Load map shapefiles as a stream in Syncfusion SfMaps
description: This section explains how to load stream to SfMaps instead of the shape file in SfMaps Xamarin.Forms
platform: xamarin
control: SfMaps
documentation: ug
---

## Load map shapefiles as a stream

You can convert shape file into stream and load to maps using the [`ReadAsStream`](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfMaps.XForms.ShapeFileLayer.html#Syncfusion_SfMaps_XForms_ShapeFileLayer_ReadAsStream_System_IO_Stream_) method instead of referring the shape files directly to maps using the Uri property.

### Load shape file as stream

A shape file is non-topological format for storing the geometric location, attribute information of geographic features like points, lines, and polygons. 

The following code snippet demonstrates the stream conversion of a shape file. The shape file added in the project is converted into stream.

{% tabs %}

{% highlight xaml %}
        
        <maps:SfMaps>
            <maps:SfMaps.Layers>
                <maps:ShapeFileLayer x:Name="ShapeLayer"/>
            </maps:SfMaps.Layers>
        </maps:SfMaps>
					
{% endhighlight %}

{% highlight c# %}

// The following code snippet demonstrates the stream conversion of a shape file. The shape file added in the project is converted into stream.

shstream = typeof(MainPage).Assembly.GetManifestResourceStream("Maps.ShapeFiles.usa_state.shp");

// The following code snippet demonstrates how to load the converted stream into shape file layer.
ShapeLayer.ReadAsStream(shstream);
			
{% endhighlight %}

{% endtabs %}

### Load shape file and dbf file as stream

In db file, the additional attributes are stored that can be joined to a shape files features like color mapping, Data Labels etc. 

{% tabs %}

{% highlight xaml %}
        
        <maps:SfMaps>
            <maps:SfMaps.Layers>
                <maps:ShapeFileLayer x:Name="ShapeLayer"
                                 ShapeIDPath="State" ShowMapItems="True"
                                 ShapeIDTableField="STATE_NAME"
                                 ItemsSource="{Binding Data}">
                    <maps:ShapeFileLayer.ShapeSettings>
                        <maps:ShapeSetting ShapeValuePath="State"/>
                    </maps:ShapeFileLayer.ShapeSettings>
                </maps:ShapeFileLayer>
            </maps:SfMaps.Layers>
        </maps:SfMaps>
					
{% endhighlight %}

{% highlight c# %}

// The following code snippet demonstrates the stream conversion of a shape and db file. The shape and db file added in the project is converted into stream.

shstream = typeof(MainPage).Assembly.GetManifestResourceStream("Maps.ShapeFiles.usa_state.shp");
dbstream = typeof(MainPage).Assembly.GetManifestResourceStream("Maps.ShapeFiles.usa_state.dbf");


// The following code snippet demonstrates how to load the converted stream into shape file layer.
ShapeLayer.ReadAsStream(shstream, dbstream);
			
{% endhighlight %}

{% endtabs %}