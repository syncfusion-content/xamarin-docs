---
layout: post
title: Sublayer in Syncfusion Maps control for Xamarin.Forms
description: This section describes about sublayer.
platform: xamarin
control: SfMaps
documentation: ug
---

# Sublayer

Sublayer in the maps control allows to load multiple shape files in a single container and enables maps to display more information.

## Adding sublayers in ShapeFileLayer

You can add multiple shape files in the [`ShapeFileLayer`](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfMaps.XForms.ShapeFileLayer.html) using the [`Sublayers`](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfMaps.XForms.ShapeFileLayer.html) property.

{% tabs %}

{% highlight xaml %}

     <maps:SfMaps x:Name="sfmap">

        <maps:SfMaps.Layers>

            <maps:ShapeFileLayer Uri="usa_state.shp">

                <maps:ShapeFileLayer.ShapeSettings>

                    <maps:ShapeSetting ShapeStroke="#D0D0D0" ShapeStrokeThickness="2" ShapeFill="#E5E5E5" />

                </maps:ShapeFileLayer.ShapeSettings>

                <maps:ShapeFileLayer.Sublayers>

                    <maps:ShapeFileLayer  Uri="Texas.shp">

                        <maps:ShapeFileLayer.ShapeSettings>

                            <maps:ShapeSetting ShapeFill="#B1D8F5" ShapeStroke="#8DCCF4" ShapeStrokeThickness="1"/>

                        </maps:ShapeFileLayer.ShapeSettings>

                        <maps:ShapeFileLayer.Markers>

                            <maps:MapMarker Label="TX" Latitude="30.267153" Longitude="-97.7430608"/>

                        </maps:ShapeFileLayer.Markers>

                    </maps:ShapeFileLayer>

                    <maps:ShapeFileLayer Uri="California.shp">

                        <maps:ShapeFileLayer.ShapeSettings>

                            <maps:ShapeSetting ShapeFill="#B1D8F5" ShapeStroke="#8DCCF4" ShapeStrokeThickness="1"/>

                        </maps:ShapeFileLayer.ShapeSettings>

                        <maps:ShapeFileLayer.Markers>

                            <maps:MapMarker Label="CA" Latitude="37.3382082" Longitude="-121.8863286"/>

                        </maps:ShapeFileLayer.Markers>

                    </maps:ShapeFileLayer>

                </maps:ShapeFileLayer.Sublayers>

            </maps:ShapeFileLayer>

        </maps:SfMaps.Layers>

    </maps:SfMaps>

{% endhighlight %}

{% highlight c# %}

            SfMaps map = new SfMaps();

            ShapeFileLayer layer = new ShapeFileLayer();

            layer.Uri = "usa_state.shp";

            ShapeSetting shapeSetting = new ShapeSetting();

            shapeSetting.ShapeStroke = Color.FromHex("#D0D0D0");

            shapeSetting.ShapeStrokeThickness = 2;

            shapeSetting.ShapeFill = Color.FromHex("#E5E5E5");

            layer.ShapeSettings = shapeSetting;

            ShapeFileLayer subShapeLayer = new ShapeFileLayer();

            subShapeLayer.Uri = "Texas.shp";

            ShapeSetting shapeSetting1 = new ShapeSetting();

            shapeSetting1.ShapeFill = Color.FromHex("#B1D8F5");

            shapeSetting1.ShapeStrokeThickness = 1;

            shapeSetting1.ShapeStroke = Color.FromHex("#8DCCF4");

            subShapeLayer.ShapeSettings = shapeSetting1;

            MapMarker mapMarker = new MapMarker();

            mapMarker.Label = "TX";

            mapMarker.Latitude = "30.267153";

            mapMarker.Longitude = "-97.7430608";

            subShapeLayer.Markers.Add(mapMarker);

            layer.Sublayers.Add(subShapeLayer);

            ShapeFileLayer subShapeLayer1 = new ShapeFileLayer();

            subShapeLayer1.Uri = "California.shp";

            ShapeSetting shapeSetting2 = new ShapeSetting();

            shapeSetting2.ShapeFill = Color.FromHex("#B1D8F5");

            shapeSetting2.ShapeStrokeThickness = 1;

            shapeSetting2.ShapeStroke = Color.FromHex("#8DCCF4");

            subShapeLayer1.ShapeSettings = shapeSetting2;

            MapMarker mapMarker1 = new MapMarker();

            mapMarker1.Label = "CA";

            mapMarker1.Latitude = "37.3382082";

            mapMarker1.Longitude = "-121.8863286";

            subShapeLayer1.Markers.Add(mapMarker1);

            layer.Sublayers.Add(subShapeLayer1);

            map.Layers.Add(layer);

            this.Content = map;

{% endhighlight %}

{% endtabs %}

![Sublayer support in Xamarin.Forms Maps](Images/Sublayer.png)

## Adding sublayers in ImageryLayer

You can add multiple shape files in the `ImageryLayer` using the `Sublayers` property.

{% tabs %}

{% highlight xaml %}

    <maps:SfMaps x:Name="sfmap">

        <maps:SfMaps.Layers>

            <maps:ImageryLayer>

                <maps:ImageryLayer.Sublayers>
                  
                    <maps:ShapeFileLayer Uri="africa.shp">

                        <maps:ShapeFileLayer.ShapeSettings>

                            <maps:ShapeSetting ShapeFill="#FD8C48" ShapeStrokeThickness="1"/>

                        </maps:ShapeFileLayer.ShapeSettings>

                    </maps:ShapeFileLayer>

                </maps:ImageryLayer.Sublayers>
            
            </maps:ImageryLayer>

        </maps:SfMaps.Layers>
        
    </maps:SfMaps>

{% endhighlight %}

{% highlight c# %}
           
            SfMaps map = new SfMaps();

            ImageryLayer imageryLayer = new ImageryLayer();

            ShapeFileLayer subShapeLayer = new ShapeFileLayer();
            subShapeLayer.Uri = "africa.shp";

            ShapeSetting shapeSetting = new ShapeSetting();
            shapeSetting.ShapeFill = Color.FromHex("#FD8C48");
            shapeSetting.ShapeStrokeThickness = 1;
            subShapeLayer.ShapeSettings = shapeSetting;

            imageryLayer.Sublayers.Add(subShapeLayer);

            map.Layers.Add(imageryLayer);
            Content = map;
			
{% endhighlight %}

{% endtabs %}	

![Sublayer support in Xamarin.Forms Maps](Images/ImageryLayer-SubLayer.jpg)

### Customizing sublayer

Sublayer is a type of shapefile layer. You can add all the elements such as markers, bubbles, color mapping, and legends to sublayer. Please refer to the following links to add the sublayer properties.

* [`Adding markers`](https://help.syncfusion.com/xamarin/sfmaps/getting-started?cs-save-lang=1&cs-lang=xaml#adding-markers)
* [`Color mapping`](https://help.syncfusion.com/xamarin/sfmaps/getting-started?cs-save-lang=1&cs-lang=xaml#color-mapping)
* [`Adding legend`](https://help.syncfusion.com/xamarin/sfmaps/getting-started?cs-save-lang=1&cs-lang=xaml#adding-legends)
* [`Adding bubbles`](https://help.syncfusion.com/xamarin/sfmaps/bubblemarker#adding-bubbles)
* [`Adding data labels`](https://help.syncfusion.com/xamarin/sfmaps/datalabels#adding-data-labels)