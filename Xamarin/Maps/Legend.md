---
layout: post
title: Legend in Syncfusion Maps control for Xamarin.Forms
description: This section describes about maps legend.
platform: xamarin
control: SfMaps
documentation: ug
---

# Legend

Legends are keys used on maps; they contain swatches of symbols with descriptions. A legend interprets what the map displays; it can be represented in various colors, shapes, or other identifiers based on the data. It gives a breakdown on what each symbol represents throughout the map.
Legends can be added using the [`LegendSettings`](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfMaps.XForms.ShapeFileLayer.html#Syncfusion_SfMaps_XForms_ShapeFileLayer_LegendSettings) in the shape file layer.

## Visibility

The legends can be made visible by setting the [`ShowLegend`](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfMaps.XForms.MapLegendSetting.html#Syncfusion_SfMaps_XForms_MapLegendSetting_ShowLegend) property in [`MapLegendSetting`](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfMaps.XForms.MapLegendSetting.html#) to true.

{% tabs %}

{% highlight xml %}

    <maps:ShapeFileLayer.LegendSettings>

    <maps:MapLegendSetting ShowLegend="True"></maps:MapLegendSetting>

    </maps:ShapeFileLayer.LegendSettings>

{% endhighlight %}

{% highlight c# %}

    MapLegendSetting legendSetting = new MapLegendSetting();

    legendSetting.ShowLegend = true;

    layer.LegendSettings = legendSetting;

{% endhighlight %}

{% endtabs %}


## Legend type

The [`LegendType`](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfMaps.XForms.MapLegendSetting.html#Syncfusion_SfMaps_XForms_MapLegendSetting_LegendTypeProperty) property is used to display the shapes and bubble legends in maps.

* Layers
* Bubbles


## Legend position

Based on the values of x (in the range of 0 to 100) and y (in the range of 0 to 100), the legends can be positioned using the  [`LegendPosition`](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfMaps.XForms.MapLegendSetting.html#Syncfusion_SfMaps_XForms_MapLegendSetting_LegendPosition)property of the [`MapLegendSetting`](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfMaps.XForms.MapLegendSetting.html#) class. Legends will be positioned in the range of 0 to 100 (screen size ratio). By default, the *LegendPosition* is (50,10).

The legend items will be placed in multiple rows if size of the total legend exceeds the available size. 


{% tabs %}

{% highlight xml %}

        <maps:ShapeFileLayer.LegendSettings>

        <maps:MapLegendSetting LegendType="Bubbles" HorizontalAlignment="Start" LegendPosition="80,60" ShowLegend="True"></maps:MapLegendSetting>

        </maps:ShapeFileLayer.LegendSettings>

{% endhighlight %}

{% highlight c# %}

            MapLegendSetting legendSetting = new MapLegendSetting();

            legendSetting.ShowLegend = true;

            legendSetting.LegendType = LegendType.Bubbles;

            legendSetting.LegendPosition = new Point(80, 60);

            legendSetting.HorizontalAlignment = HorizontalAlignment.Start;

            layer.LegendSettings = legendSetting;

{% endhighlight %}

{% endtabs %}

![Legend positioning in Xamarin.Forms Maps](Images/LegendWrapping.jpg)


## Legend alignment

Legends can be aligned using the [`HorizontalAlignment`](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfMaps.XForms.MapLegendSetting.html#Syncfusion_SfMaps_XForms_MapLegendSetting_HorizontalAlignmentProperty) and [`VerticalAlignment`](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfMaps.XForms.MapLegendSetting.html#Syncfusion_SfMaps_XForms_MapLegendSetting_VerticalAlignmentProperty)Properties. By default, the legends will be aligned to  the center.

{% tabs %}

{% highlight xml %}

        <maps:ShapeFileLayer.LegendSettings>

        <maps:MapLegendSetting LegendType="Bubbles" HorizontalAlignment="Start" LegendPosition="5,20" VerticalAlignment="Center" ShowLegend="True"></maps:MapLegendSetting>

        </maps:ShapeFileLayer.LegendSettings>

{% endhighlight %}

{% highlight c# %}

            MapLegendSetting legendSetting = new MapLegendSetting();

            legendSetting.ShowLegend = true;

            legendSetting.LegendType = LegendType.Bubbles;

            legendSetting.LegendPosition = new Point(5, 20);

            legendSetting.HorizontalAlignment = HorizontalAlignment.Start;

            legendSetting.VerticalAlignment = VerticalAlignment.Center;

            layer.LegendSettings = legendSetting;

{% endhighlight %}

{% endtabs %}

![Legend alignment support in Xamarin.Forms Maps](Images/LegendAlignment.jpg)

## Icon customization

The icon size of a legend can be customized using the [`IconSize`](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfMaps.XForms.MapLegendSetting.html#Syncfusion_SfMaps_XForms_MapLegendSetting_IconSize) property.

{% tabs %}

{% highlight xml %}

    <maps:ShapeFileLayer.LegendSettings>

    <maps:MapLegendSetting ShowLegend="True" LegendPosition="75,90">

    <maps:MapLegendSetting.IconSize>

    <Size Width="20" Height="20"/>

    </maps:MapLegendSetting.IconSize>

    </maps:MapLegendSetting>

    </maps:ShapeFileLayer.LegendSettings>

{% endhighlight %}

{% highlight c# %}

    MapLegendSetting legendSetting = new MapLegendSetting();

    legendSetting.ShowLegend = true;

    legendSetting.LegendPosition = new Point(75, 90);

    legendSetting.IconSize = new Size(20, 20);

    layer.LegendSettings = legendSetting;

{% endhighlight %}

{% endtabs %}

The icon shape can be customized using the [`LegendIcon`](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfMaps.XForms.LegendIcon.html) property. By default, this property is set to circle for bubbles and rectangle for shapes.

{% tabs %}

{% highlight xml %}

    <maps:ShapeFileLayer.LegendSettings>

    <maps:MapLegendSetting ShowLegend="True" LegendType="Bubbles" LegendIcon="Diamond">

    </maps:MapLegendSetting>

    </maps:ShapeFileLayer.LegendSettings>

{% endhighlight %}

{% highlight c# %}

    MapLegendSetting legendSetting = new MapLegendSetting();

    legendSetting.ShowLegend = true;

    legendSetting.LegendType = LegendType.Bubbles;

    legendSetting.LegendIcon = LegendIcon.Diamond;

    layer.LegendSettings = legendSetting;

{% endhighlight %}

{% endtabs %}

![Legend icon customization in Xamarin.Forms Maps](Images/LegendIconCustomization.jpg)

## Item margin

The [`ItemMargin`](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfMaps.XForms.MapLegendSetting.html#Syncfusion_SfMaps_XForms_MapLegendSetting_ItemMarginProperty) property is used to set spacing between the legend items.

{% tabs %}

{% highlight xml %}

        <maps:ShapeFileLayer.LegendSettings>

       <maps:MapLegendSetting LegendType="Bubbles" ShowLegend="True" ItemMargin="30" />

        </maps:ShapeFileLayer.LegendSettings>

{% endhighlight %}

{% highlight c# %}

            MapLegendSetting legendSetting = new MapLegendSetting();

            legendSetting.ShowLegend = true;

            legendSetting.LegendType = LegendType.Bubbles;

            legendSetting.ItemMargin = 30;
            
            layer.LegendSettings = legendSetting;

{% endhighlight %}

{% endtabs %}

![Legend item margin support in Xamarin.Forms Maps](Images/LegendItemMargin.jpg)

## Legend label

The [`LegendLabel`](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfMaps.XForms.ColorMapping.html#Syncfusion_SfMaps_XForms_ColorMapping_LegendLabel) provides information about the maps. It is specified under color mapping. If *LegendLabel* is not specified, ColorMapping values will be applied as legend label.

The following properties are used to customize the label of the legends:

 * [`TextColor`](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfMaps.XForms.MapLegendSetting.html#Syncfusion_SfMaps_XForms_MapLegendSetting_TextColorProperty) : Changes the color of the legend text.

 * [`FontAttributes`](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfMaps.XForms.MapLegendSetting.html#Syncfusion_SfMaps_XForms_MapLegendSetting_FontAttributesProperty) : Changes the font weight of the legend label.

 * [`FontFamily`](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfMaps.XForms.MapLegendSetting.html#Syncfusion_SfMaps_XForms_MapLegendSetting_FontFamilyProperty) : Changes the font family of the legend label.

 * [`FontSize`](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfMaps.XForms.MapLegendSetting.html#Syncfusion_SfMaps_XForms_MapLegendSetting_FontSizeProperty) : Changes the text size of the legend label.
{% tabs %}

{% highlight xml %}

        <maps:ShapeFileLayer.LegendSettings>

       <maps:MapLegendSetting LegendType="Bubbles" ShowLegend="True" FontFamily="algerian.ttf" TextColor="Maroon" />

        </maps:ShapeFileLayer.LegendSettings>

{% endhighlight %}

{% highlight c# %}

            MapLegendSetting legendSetting = new MapLegendSetting();

            legendSetting.ShowLegend = true;

            legendSetting.LegendType = LegendType.Bubbles;

            legendSetting.FontFamily ="algerian.ttf";

            legendSetting.TextColor = Color.Maroon;
            
            layer.LegendSettings = legendSetting;

{% endhighlight %}

{% endtabs %}

![Legend font customization in Xamarin.Forms Maps](Images/LegendFontCustomization.jpg)


The following code sample demonstrates how to add a legend to maps and customize it.


### Legend for bubbles


{% tabs %}

{% highlight xml %}

     <Grid>
        <Grid.BindingContext>
            <local:ViewModel />
        </Grid.BindingContext>
        <maps:SfMaps>
            <maps:SfMaps.Layers>
                <maps:ShapeFileLayer x:Name="layer" Uri="usa_state.shp" ShapeIDPath="Name" ShapeIDTableField="STATE_NAME" 
                                        ShowMapItems="True"  ItemsSource="{Binding DataSource}">
                    <maps:ShapeFileLayer.BubbleMarkerSettings>
                        <maps:BubbleMarkerSetting  ValuePath="index" ColorValuePath="index" >
                            <maps:BubbleMarkerSetting.ColorMappings>
                                <maps:RangeColorMapping Color="#2E769F" From="0" To="15" LegendLabel="0 - 15 " />
                                <maps:RangeColorMapping Color="#D84444" To="30" From="15" LegendLabel="15- 30" />
                                <maps:RangeColorMapping Color="#816F28" To="45" From="30" LegendLabel="30 - 45" />
                                <maps:RangeColorMapping Color="#7F38A0" To="60" From="45" LegendLabel="45 - 60" />
                            </maps:BubbleMarkerSetting.ColorMappings>
                        </maps:BubbleMarkerSetting>
                    </maps:ShapeFileLayer.BubbleMarkerSettings>
                    <maps:ShapeFileLayer.ShapeSettings>
                        <maps:ShapeSetting  ShapeFill="LightBlue"/>
                    </maps:ShapeFileLayer.ShapeSettings>
                    <maps:ShapeFileLayer.LegendSettings>
                        <maps:MapLegendSetting LegendType="Bubbles" ItemMargin="30" LegendIcon="Diamond" LegendPosition="5,20" HorizontalAlignment="Start" VerticalAlignment="Bottom" FontFamily="algerian.ttf" FontSize="14" TextColor="Maroon" ShowLegend="True"></maps:MapLegendSetting>
                    </maps:ShapeFileLayer.LegendSettings>
                </maps:ShapeFileLayer>
            </maps:SfMaps.Layers>
        </maps:SfMaps>
    </Grid>

{% endhighlight %}

{% highlight c# %}

            ViewModel viewModel = new ViewModel();

            SfMaps map = new SfMaps();

            map.BackgroundColor = Color.White;

            ShapeFileLayer layer = new ShapeFileLayer();

            layer.Uri = "usa_state.shp";

            layer.ItemsSource = viewModel.DataSource;

            layer.ShapeIDTableField = "STATE_NAME";

            layer.ShapeIDPath = "Name";

            layer.ShowMapItems = true;               

            BubbleMarkerSetting bubbleSetting = new BubbleMarkerSetting();

            bubbleSetting.ValuePath = "index";

            bubbleSetting.ColorValuePath = "index";


            RangeColorMapping colorMapping1 = new RangeColorMapping() { Color = Color.FromHex("#2E769F"), From = 0, To = 15 };
            RangeColorMapping colorMapping2 = new RangeColorMapping() { Color = Color.FromHex("#D84444"), From = 15, To = 30 };
            RangeColorMapping colorMapping3 = new RangeColorMapping() { Color = Color.FromHex("#816F28"), From = 30, To = 45 };
            RangeColorMapping colorMapping4 = new RangeColorMapping() { Color = Color.FromHex("#7F38A0"), From = 45, To = 50 };

            bubbleSetting.ColorMappings.Add(colorMapping1);
            bubbleSetting.ColorMappings.Add(colorMapping2);
            bubbleSetting.ColorMappings.Add(colorMapping3);
            bubbleSetting.ColorMappings.Add(colorMapping4);

            layer.BubbleMarkerSettings = bubbleSetting;

            MapLegendSetting legendSetting = new MapLegendSetting();

            legendSetting.ShowLegend = true;

            legendSetting.LegendPosition = new Point(5, 20);

            legendSetting.LegendType = LegendType.Bubbles;

            legendSetting.FontFamily ="algerian.ttf";

            legendSetting.TextColor = Color.Maroon;

            legendSetting.ItemMargin = 30;

            legendSetting.LegendIcon = LegendIcon.Diamond;

            legendSetting.HorizontalAlignment = HorizontalAlignment.Start;

            layer.LegendSettings = legendSetting;


            ShapeSetting shapeSetting = new ShapeSetting();

            shapeSetting.ShapeFill = Color.LightBlue;

            layer.ShapeSettings = shapeSetting;

            map.Layers.Add(layer);

            this.Content = map;


    public class AgricultureData
    {
        public AgricultureData(string name, string type, int count)
        {
            Name = name;
            Type = type;
            index = count;
        }

        public string Name
        {
            get;
            set;
        }

        public string Type
        {
            get;
            set;
        }

        public int index
        {
            get;
            set;
        }
    }

    public class ViewModel
    {
        public ViewModel()
        {
            DataSource = new ObservableCollection<AgricultureData>();
          
            DataSource.Add(new AgricultureData("Alaska", "Vegetables", 0));
            DataSource.Add(new AgricultureData("Arizona", "Rice", 36));          
            DataSource.Add(new AgricultureData("California", "Wheat", 24));
            DataSource.Add(new AgricultureData("Colorado", "Rice", 31));
            DataSource.Add(new AgricultureData("North Dakota", "Grains", 4));
            DataSource.Add(new AgricultureData("Connecticut", "Wheat", 18));          
            DataSource.Add(new AgricultureData("District of Columbia", "Grains", 27));
            DataSource.Add(new AgricultureData("Florida", "Wheat", 48));
            DataSource.Add(new AgricultureData("New Mexico", "Vegetables", 41));        
            DataSource.Add(new AgricultureData("Idaho", "Rice", 8));
          
        }
        public ObservableCollection<AgricultureData> DataSource { get; set; }

    }

{% endhighlight %}

{% endtabs %}

![Legend for bubbles support in Xamarin.Forms Maps](Images/LegendForBubble.jpg)


### Legend for shapes


{% tabs %}

{% highlight xml %}

        <Grid>
                <Grid.BindingContext>
                    <local:ViewModel/>
                </Grid.BindingContext>
                <maps:SfMaps x:Name="sfmap"  BackgroundColor="White">
                    <maps:SfMaps.Layers>
                <maps:ShapeFileLayer Uri="usa_state.shp" ItemsSource="{Binding Data}"
                                         ShapeIDPath="State" ShapeIDTableField="STATE_NAME" >
                    <maps:ShapeFileLayer.LegendSettings>
                        <maps:MapLegendSetting ItemMargin="30" LegendIcon="Diamond" LegendPosition="50,20" 
                                 FontFamily="algerian.ttf" FontSize="14" TextColor="Maroon" ShowLegend="True">
                        </maps:MapLegendSetting>
                    </maps:ShapeFileLayer.LegendSettings>
                    <maps:ShapeFileLayer.ShapeSettings>
                        <maps:ShapeSetting ShapeColorValuePath="Candidate" ShapeValuePath="Candidate">
                            <maps:ShapeSetting.ColorMappings>
                                <maps:EqualColorMapping Color="#D84444" Value="Romney"
                                                            LegendLabel="Romney"/>
                                <maps:EqualColorMapping Color="#316DB5" Value="Obama" 
                                                            LegendLabel="Obama"/>
                            </maps:ShapeSetting.ColorMappings>
                        </maps:ShapeSetting>
                    </maps:ShapeFileLayer.ShapeSettings>
                </maps:ShapeFileLayer>
            </maps:SfMaps.Layers>
        </maps:SfMaps>
    </Grid>

{% endhighlight %}

{% highlight c# %}

            ViewModel viewModel = new ViewModel();

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

            legendSetting.LegendPosition = new Point(50, 20);

            legendSetting.LegendType = LegendType.Layers;

            legendSetting.FontFamily ="algerian.ttf";

            legendSetting.TextColor = Color.Maroon;

            legendSetting.ItemMargin = 30;

            legendSetting.LegendIcon = LegendIcon.Diamond;

            layer.LegendSettings = legendSetting;

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

![Legend for shapes in Xamarin.Forms Maps](Images/LegendForShapes.png)

