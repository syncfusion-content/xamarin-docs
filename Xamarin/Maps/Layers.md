---
layout: post
title: Layers in Syncfusion Maps control for Xamarin.Forms
description: This section describes about the imagery layer, shape file layer, shape settings, customize the shapes and events in maps
platform: xamarin
control: SfMaps
documentation: ug
---

# Layers in Maps (SfMaps)

The maps control is maintained through [`Layers`](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfMaps.XForms.SfMaps.html#Syncfusion_SfMaps_XForms_SfMaps_LayersProperty); a map can accommodate one or more layers.

The maps control consists the following two layers:

* Imagery layer

* Shape file layer

## Imagery layer

The [`MapsProvider`](https://help.syncfusion.com/xamarin/sfmaps/mapsprovider) section explains about the imagery layer.

## Shape file layer

Using shape file layer, custom shape files can be rendered and the shapes can be customized.

### Shape settings

This section defines how to customize the shapes in a map.

You can customize a shape's fill, stroke, and stroke thickness using the [`ShapeFill`](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfMaps.XForms.ShapeSetting.html#Syncfusion_SfMaps_XForms_ShapeSetting_ShapeFill), [`ShapeStroke`](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfMaps.XForms.ShapeSetting.html#Syncfusion_SfMaps_XForms_ShapeSetting_ShapeStroke),[`ShapeStrokeThickness`](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfMaps.XForms.ShapeSetting.html#Syncfusion_SfMaps_XForms_ShapeSetting_ShapeStrokeThickness) properties.

Refer to the following code sample for customizing shapes.

{% tabs %}

{% highlight xml %}

       <maps:SfMaps>

        <maps:SfMaps.Layers >

        <maps:ShapeFileLayer Uri="usa_state.shp" >

        <maps:ShapeFileLayer.ShapeSettings>

        <maps:ShapeSetting  ShapeFill="LightBlue" ShapeStroke="Black" ShapeStrokeThickness="2" >

        </maps:ShapeSetting>

        </maps:ShapeFileLayer.ShapeSettings>

         </maps:ShapeFileLayer>

        </maps:SfMaps.Layers>

        </maps:SfMaps>

{% endhighlight %}

{% highlight c# %}

        SfMaps maps = new SfMaps();

        ShapeFileLayer layer = new ShapeFileLayer();

        layer.Uri = "usa_state.shp";

        layer.ItemsSource = GetDataSource();

        layer.ShapeIDTableField = "STATE_NAME";

        layer.ShapeIDPath = "State";           
    
        ShapeSetting shapeSetting = new ShapeSetting();            

        shapeSetting.ShapeFill = Color.LightBlue;

        shapeSetting.ShapeStroke = Color.Black;

        shapeSetting.ShapeStrokeThickness = 2;

        layer.ShapeSettings = shapeSetting;

        maps.Layers.Add(layer);

{% endhighlight %}

{% endtabs %}

![Shape customization in Xamarin.Forms Maps](Images/ShapeCustomization_img1.jpeg)

To customize the shapes based on the bound values, use the following properties:

[`ShapeValuePath`](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfMaps.XForms.ShapeSetting.html#Syncfusion_SfMaps_XForms_ShapeSetting_ShapeValuePath): Field value that has to be bound for each shape.

[`ShapeColorValuePath`](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfMaps.XForms.ShapeSetting.html#Syncfusion_SfMaps_XForms_ShapeSetting_ShapeColorValuePath): Field value that has to be bound to determine the color.

{% tabs %}

{% highlight xml %}

       <maps:SfMaps>

        <maps:SfMaps.Layers >

        <maps:ShapeFileLayer Uri="usa_state.shp" 

        ShapeIDPath="State" ShapeIDTableField="STATE_NAME" >

        <maps:ShapeFileLayer.ShapeSettings>

        <maps:ShapeSetting ShapeColorValuePath="Candidate" ShapeValuePath="Candidate">

        <maps:ShapeSetting.ColorMappings>

        <maps:EqualColorMapping Color="#D84444" Value="Romney" LegendLabel="Romney"></maps:EqualColorMapping>

        <maps:EqualColorMapping Color="#316DB5" Value="Obama" LegendLabel="Obama"></maps:EqualColorMapping>

        </maps:ShapeSetting.ColorMappings>

        </maps:ShapeSetting>

        </maps:ShapeFileLayer.ShapeSettings>

        </maps:ShapeFileLayer>

        </maps:SfMaps.Layers>

        </maps:SfMaps>

{% endhighlight %}

{% highlight c# %}

ShapeFileLayer layer = new ShapeFileLayer();

layer.Uri = "usa_state.shp";

layer.ItemsSource = GetDataSource();

layer.ShapeIDTableField = "STATE_NAME";

layer.ShapeIDPath = "State";           

map.Layers.Add(layer);

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

{% endhighlight %}

{% endtabs %}

![Customize shapes based on bounds support in Xamarin.Forms Maps](Images/ShapeCustomization_img2.jpeg)

### Customize selected shapes

To customize the selected shapes alone, use the following properties:

[`SelectedShapeColor`](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfMaps.XForms.ShapeSetting.html#Syncfusion_SfMaps_XForms_ShapeSetting_SelectedShapeColor): Sets the color for selected shapes in a map.

[`SelectedShapeStroke`](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfMaps.XForms.ShapeSetting.html#Syncfusion_SfMaps_XForms_ShapeSetting_SelectedShapeStroke): Sets the border color for selected shapes in a map.

[`SelectedShapeStrokeThickness`](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfMaps.XForms.ShapeSetting.html#Syncfusion_SfMaps_XForms_ShapeSetting_SelectedShapeStrokeThickness): Sets the border thickness for selected shapes in a map.

{% tabs %}

{% highlight xml %}

<maps:ShapeFileLayer.ShapeSettings>

<maps:ShapeSetting  ShapeFill="LightBlue" ShapeStroke="Black" ShapeStrokeThickness="1" >

</maps:ShapeSetting>

</maps:ShapeFileLayer.ShapeSettings>

{% endhighlight %}

{% highlight c# %}

ShapeSetting shapeSetting = new ShapeSetting();

shapeSetting.SelectedShapeColor = Color. Green;

shapeSetting.SelectedShapeStroke = Color.Black;

shapeSetting.SelectedShapeStrokeThickness = 1;

layer.ShapeSettings = shapeSetting;

{% endhighlight %}

{% endtabs %}

![Customize selected shapes in Xamarin.Forms Maps](Images/ShapeCustomization_img3.jpeg)

### Events

The [`ShapeSelected`](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfMaps.XForms.ShapeFileLayer.html) event will be triggered when a map shape is selected. A corresponding model data is passed as an argument. The ShapeSelected event has been deprecated.

The [`ShapeSelectionChanged`](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfMaps.XForms.ShapeFileLayer.html) event will be triggered when changing the the map shapes selection with corresponding argument as model [`Data`](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfMaps.XForms.ShapeSelectedEventArgs.html#Syncfusion_SfMaps_XForms_ShapeSelectedEventArgs_Data).Selection state of the shape will be changed using the  [`IsSelected`](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfMaps.XForms.ShapeSelectedEventArgs.html#Syncfusion_SfMaps_XForms_ShapeSelectedEventArgs_IsSelected) property

{% tabs %}

{% highlight xml %}

<maps:ShapeFileLayer ShapeSelectionChanged ="ShapeLayer_ShapeSelectionChanged" />

{% endhighlight %}

{% highlight c# %}

        private void ShapeLayer_ShapeSelectionChanged(object sender, ShapeSelectedEventArgs e)
        {
            AgricultureData data = e.Data as AgricultureData;
            bool IsSelected = e.IsSelected;
        }
{% endhighlight %}

{% endtabs %}

![Shape Selection Event support in Xamarin.Forms Maps](Images/ShapeCustomization_img4.jpeg)

## Sublayer

The shape layers are the core layers of the maps. Multiple layers can be added to the shape layers as sublayers within the shape layers.

### Adding multiple layers in the map

Multiple layers can be added to the maps using [`Sublayer`](https://help.syncfusion.com/xamarin/sfmaps/sublayer).


## Displaying layer in the view

The [`BaseMapIndex`](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfMaps.XForms.SfMaps.html#Syncfusion_SfMaps_XForms_SfMaps_BaseMapIndexProperty) property allows drill-down from main layer to another layer.

In the ShapeSelected event, the *BaseMapIndex* property has been used to change the layer when Asia shape is selected.

{% tabs %}

{% highlight xml %}
      
      <Grid>
        <Grid.BindingContext>
            <local:DrilldownViewModel/>
        </Grid.BindingContext>
        <maps:SfMaps x:Name="map">
            <maps:SfMaps.Layers>
                <maps:ShapeFileLayer EnableSelection="True" x:Name="layer1" Uri="world-map.shp" ItemsSource="{Binding DataSource}" ShapeIDPath="Country" ShapeIDTableField="admin" ShapeSelectionChanged="ShapeFileLayer_ShapeSelected">
                    <maps:ShapeFileLayer.ShapeSettings>
                        <maps:ShapeSetting  ShapeColorValuePath="Continent">
                            <maps:ShapeSetting.ColorMappings>
                                <maps:EqualColorMapping Color="#C13664" Value="North America" ></maps:EqualColorMapping>
                                <maps:EqualColorMapping Color="#9C3367" Value="South America"></maps:EqualColorMapping>
                                <maps:EqualColorMapping Color="#80306A" Value="Africa"></maps:EqualColorMapping>
                                <maps:EqualColorMapping Color="#622D6C" Value="Europe"></maps:EqualColorMapping>
                                <maps:EqualColorMapping Color="#462A6D" Value="Asia"></maps:EqualColorMapping>
                                <maps:EqualColorMapping Color="#2A2870" Value="Australia"></maps:EqualColorMapping>
                            </maps:ShapeSetting.ColorMappings>
                        </maps:ShapeSetting>
                    </maps:ShapeFileLayer.ShapeSettings>
                </maps:ShapeFileLayer>
                <maps:ShapeFileLayer x:Name="layer2" Uri="asia.shp">
                    <maps:ShapeFileLayer.ShapeSettings>
                        <maps:ShapeSetting ShapeFill="#462A6D"/>
                    </maps:ShapeFileLayer.ShapeSettings>
                </maps:ShapeFileLayer>
            </maps:SfMaps.Layers>
        </maps:SfMaps>
        <Label x:Name="label" Grid.Row="1" HorizontalOptions="Center" VerticalOptions="Center" HorizontalTextAlignment="Center" VerticalTextAlignment="Center" Text="Click on a Asia shape to drill down"/>
    </Grid>

{% endhighlight %}

{% highlight c# %}

        private void ShapeFileLayer_ShapeSelected(object sender, Syncfusion.SfMaps.XForms.ShapeSelectedEventArgs e)
        {
            map.BaseMapIndex = 1;
            label.IsVisible = false;
        }

    public class DrilldownViewModel
    {
        public DrilldownViewModel()
        {
            DataSource = new ObservableCollection<DrilldownModel>();
            DataSource.Add(new DrilldownModel("Afghanistan", "Asia"));
            DataSource.Add(new DrilldownModel("Angola", "Africa"));
            DataSource.Add(new DrilldownModel("Albania", "Europe"));
            DataSource.Add(new DrilldownModel("United Arab Emirates", "Asia"));
            DataSource.Add(new DrilldownModel("Argentina", "South America"));
            DataSource.Add(new DrilldownModel("Armenia", "Asia"));
            DataSource.Add(new DrilldownModel("French Southern and Antarctic Lands", "Seven seas (open ocean)"));
            DataSource.Add(new DrilldownModel("Australia", "Australia"));
            //..
		    //..
            DataSource.Add(new DrilldownModel("Zambia", "Africa"));
            DataSource.Add(new DrilldownModel("Zimbabwe", "Africa"));
        }
        public ObservableCollection<DrilldownModel> DataSource { get; set; }

    }

     public class DrilldownModel
    {
        public DrilldownModel(string country, string con)
        {
            this.Country = country;
            this.Continent = con;
        }
        public string Continent
        {
            get;
            set;
        }
        public string Country
        {
            get;
            set;
        }

    }

{% endhighlight %}

{% endtabs %}

![Drilldown support in Xamarin.Forms Maps](Images/Drilldown1.jpg)  ![](Images/Drilldown_Asia.jpg) 

## See Also

[How to load shape files as stream in maps](https://www.syncfusion.com/kb/10555/how-to-load-shape-files-as-stream-in-maps)

[How to add sub shape file layer for ImageryLayer in Xamarin.Forms SfMaps](https://www.syncfusion.com/kb/10579/how-to-add-sub-shape-file-layer-for-imagerylayer-in-xamarin-forms-sfmaps)

[How to draw a line (route) between two terminals in SfMaps](https://www.syncfusion.com/kb/10619/how-to-draw-a-line-route-between-two-terminals-in-sfmaps)