---
layout: post
title: Elements of Syncfusion Maps control for Xamarin.Forms 
description: How to add elements such as shapes, bubbles, markers, legend, labels and etc., in Maps control
platform: xamarin
control: SfMaps
documentation: ug
---

# Map Elements

Map control contains a set of map elements such as shapes, bubbles, markers, legend, labels and data items that can be visualized with the customized appearance showing additional information on the map by using the data bound data.

## Markers

Markers are notes used to leave some message on the map.

There are two ways to set marker for map.

1. Adding marker objects to map
2. Custom Marker

### Adding Marker objects to the map

Without datasource, n number of markers can be added to shape layers with markers property. Each marker object contains the following list of properties.

* `Label` - Text that displays some information about the annotation in text format.
* `Latitude` - Latitude point determine the Y-axis position of marker.
* `Longitude` - Longitude point determine the X-axis position of marker.

{% tabs %}
{% highlight xaml %}
                                                    
        <SfMaps:ShapeFileLayer:MapMarker>
                
                <SfMaps:MapMarker Label = "California" Latitude = "37" Longitude = "-120"/>                
                    
        </SfMaps:ShapeFileLayer:MapMarker>
                               	      

{% endhighlight %}

{% highlight c# %}

    MapMarker marker = new MapMarker ();
    marker.Label = "California";
    marker.Latitude = 37;
    marker.Longitude = -120;
    layer.Markers.Add (marker);

{% endhighlight %}
{% endtabs %}

![](Images/Markers.png)  


## Bubbles

Bubbles in the Maps control represent the underlying data values of the map. Bubbles are scattered throughout the map shapes that contain bound values.

Bubbles are included when data binding and the `BubbleMarkerSettings` is set to the shape layers. 


<table>
<tr>
<th>
Property</th><th>
Type</th><th>
Description</th></tr>
<tr>
<td>
MaxSize</td><td>
String</td><td>
Get or sets the maximum height and width of the bubble.</td></tr>
<tr>
<td>
MinSize</td><td>
String</td><td>
Gets or sets the minimum height and width of the bubble.</td></tr>
<tr>
<td>
ColorValuePath</td><td>
String</td><td>
Get or sets the field value that is to be fetched from data for each bubble used for determining the bubble color.</td></tr>
<tr>
<td>
ValuePath</td><td>
String</td><td>
Gets or sets the field value that is to be fetched from data for each bubble.</td></tr>

<td>
Color</td><td>
String</td><td>
Gets or sets the fill color for bubbles.</td></tr>

</table>

### Add Bubbles to the Map

To add bubbles to a map, the bubble marker setting is added to the shape file layer. Create the Model and ViewModel as illustrated in the Data Binding topic and add the following code. Also set the `MaxSize`, `MinSize`, and `ValuePath` properties as illustrated in the following code sample.

{% tabs %}
{% highlight xaml %}        

        <syncfusion:SfMap.Layers>

                <syncfusion:ShapeFileLayer EnableSelection="false" ShapeIDPath="Country" ShapeIDTableField="NAME">

                        <syncfusion:ShapeFileLayer.BubbleMarkerSetting>
                        
                                <syncfusion:BubbleMarkerSetting ShowBubbles="true" MaxSize="25" MinSize="10" ValuePath="Population" >

                                </syncfusion:BubbleMarkerSetting>

                        </syncfusion:ShapeFileLayer.BubbleMarkerSetting>                  

                </syncfusion:ShapeFileLayer>

        </syncfusion:SfMap.Layers>                                       
 

{% endhighlight %}

{% highlight c# %}

{
        
        //..
        layer.ShapeIdTableField ="NAME";
        layer.ShapeIdPath ="Country";
        layer.DataSource = GetDataSource ();

        BubbleMarkerSetting markerSetting = new BubbleMarkerSetting();
        markerSetting.ShowBubbles = true;
        markerSetting.MinSize =10;
        markerSetting.MaxSize =25;
        markerSetting.ValuePath="Population";
        //..
}


            public List<BubbleData> GetDataSource()
            
            {
            
            List<BubbleData> list = new List<BubbleData>();
            list.Add(new BubbleData("Brazil", "BRA", 204436000, 22));
            list.Add(new BubbleData("Russia", "RUS", 146267288, 134));
            list.Add(new BubbleData("United States", "USA", 321174000, 167));
            list.Add(new BubbleData("India", "IND", 1272470000, 73));
            list.Add(new BubbleData("China", "CHI", 1370320000, 30));
            list.Add(new BubbleData("Indonasia", "INO", 255461700, 72));


            return list;
           }

    public class BubbleData
	{
		public BubbleData (string country, string countrycode,double population,int Index)
		{
			Country = country;
			Code = countrycode;
			Population = population;
			index = Index;
		}

		public string Code {
			get;
			set;
		}
		public string Country {
			get;
			set;
		}

		public double Population {
			get;
			set;
		}

		public int index {
			get;
			set;
		}
	}



{% endhighlight %}
{% endtabs %}

![](Images/Bubbles.png)  

## Legend

A legend is a key used on a map that contains swatches of symbols with descriptions. It provides valuable information for interpreting what the map is displaying and can be represented in various colors, shapes or other identifiers based on the data. It gives a breakdown of what each symbol represents throughout the map.

### Visibility

The Legends can be made visible by setting the `ShowLegend` property of LegendSettings to `true`.

## Positioning of the Legend

Based on the margin values of X and Y-axes, the Map legends can be positioned with the support of `LegendPosition` property in `LegendSetting` class

### Legend Icon Size

The map legend icon size can be modified by using the `IconHeight` and `IconWidth` properties in `LegendSetting`

Refer Equal color mapping code for legend support

{% tabs %}
{% highlight xaml %}
        
        <SfMaps:ShapeFileLayer:LegendSettings >
            <SfMaps:MapLegendSetting ShowLegend ="true" IconHeight ="20" 
            IconWidth ="20" LegendPosition =(100,400)/>
        </SfMaps:ShapeFileLayer:LegendSettings>      

{% endhighlight %}

{% highlight c# %}

         LegendSettings legendSetting = new LegendSettings ();
         legendSetting.ShowLegend = true;
         legendSetting.IconHeight = 20;
         legendSetting.IconWidth = 20;
         legendSetting.LegendPosition = new Point (100, 400);
         layer.LegendSettings = legendSetting;


{% endhighlight %}
{% endtabs %}

![](Images/Legends.png)  