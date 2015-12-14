---
layout: post
title: Map Elements | SfMaps |Xamarin | Syncfusion
description: map elements
platform: xamarin
control: SfMaps
documentation: ug
---

#Map Elements

Map control contains a set of map elements such as shapes, bubbles, markers, legend, labels and data items that can be visualized with the customized appearance showing additional information on the map by using the databound datas.

##Markers

Markers are notes used to leave some message on the map.

There are two ways to set marker for map.

1. Adding marker objects to map
2. Custom Marker

###Adding Marker objects to the map

Without datasource, n number of markers can be added to shape layers with markers property. Each marker object contains the following list of properties.

* **label** - Text that displays some information about the annotation in text format.
* **latitude** - Latitude point determine the Y-axis position of marker.
* **longitude** - Longitude point determine the X-axis position of marker.

{% tabs %}
{% highlight Xamarin.Android %}

        MapMarker marker = new MapMarker ();
        marker.Label = "California";
        marker.Latitude = 37;
        marker.Longitude = -120;
        layer.Markers.Add (marker);

{% endhighlight %}

{% highlight Xamarin.iOS %}

        SFMapMarker marker = new SFMapMarker ();
        marker.Latitude = 37;
        marker.Longitude = -120;
        marker.Label = @"California";
        layer.Markers.Add (marker);

{% endhighlight %}
{% endtabs %}

![](images/marker_android.png)  

###Custom Marker

By default, it displays the label data at the specified latitude and longitude. You can also customize the UI of the marker. DrawMarker is a overide method which is used to customize the UI of markers.

{% tabs %}
{% highlight Xamarin.Android %}

        public class CustomMarker : MapMarker
        {
            public CustomMarker (Android.Content.Context con)
            {
                context = con;
            }

            Android.Content.Context context;
            public override void DrawMarker (PointF p0, Canvas p1)
            {
                Bitmap bitmap = BitmapFactory.DecodeResource (context.Resources, Resource.Drawable.pin);
                p1.DrawBitmap(bitmap,(float)p0.X-12,(float)p0.Y-35,new Paint());
            }

        }

        //..

        CustomMarker california = new CustomMarker ();
        california.Latitude = 37;
        california.Longitude = -120;
        layer.Markers.Add(california);

        CustomMarker  newYork=new CustomMarker ();
        newYork.Latitude = 40.7127;
        newYork.Longitude = -74.0059;
        layer.Markers.Add(newYork);

        CustomMarker iowa=new CustomMarker ();
        iowa.Latitude= 42;
        iowa.Longitude= -93;
        layer.Markers.Add(iowa);

        //..
{% endhighlight %}

{% highlight Xamarin.iOS %}

        public class CustomMarker : SFMapMarker
        {
            public override UIView GetView (CGPoint point)
            {
                UIImageView  image= new UIImageView (new CGRect (point.X - 8, point.Y - 25, 15, 23));
                image.Image = new UIImage ("pin.png");
                return image;
            }

        }

        //..

        CustomMarker california = new CustomMarker ();
        california.Latitude = 37;
        california.Longitude = -120;
        layer.Markers.Add(california);

        CustomMarker  newYork=new CustomMarker ();
        newYork.Latitude = 40.7127;
        newYork.Longitude = -74.0059;
        layer.Markers.Add(newYork);
			
        CustomMarker iowa=new CustomMarker ();
        iowa.Latitude= 42;
        iowa.Longitude= -93;
        layer.Markers.Add(iowa);

        //..
			
{% endhighlight %}
{% endtabs %}
![](images/custommarker_android.png)  
## Bubbles

Bubbles in the **Maps** control represent the underlying data values of the map. Bubbles are scattered throughout the map shapes that contain bound values.

Bubbles are included when data binding and the `BubbleMarkerSettings` is set to the shape layers. 

### Properties


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
{% highlight Xamarin.Android %}

        {
            //..
            layer.ShapeIdTableField ="STATE_NAME";
            layer.ShapeIdPath ="State";
            layer.DataSource = GetDataSource ();

            BubbleMarkerSetting markerSetting = new BubbleMarkerSetting();
            markerSetting.ShowBubbles = true;
            markerSetting.MinSize =10;
            markerSetting.MaxSize =25;
            markerSetting.ValuePath="Population";
            //..
        }
        JSONArray GetDataSource()
        {
            JSONArray array = new JSONArray ();
            array.Put(getJsonObject("California",38332521,"CA"));
            array.Put(getJsonObject("New York",19651127,"NY"));
            array.Put(getJsonObject("Iowa",3090416,"IA"));
            return array;
        }

        JSONObject getJsonObject(String state,double population,string name)
        {
            JSONObject obj= new JSONObject();
            obj.Put ("State", state);
            obj.Put ("Population", population);
            obj.Put ("Name", name);
            return obj;
        }


{% endhighlight %}

{% highlight Xamarin.iOS %}

        {
            //..
            layer.DataSource = GetDataSource ();
            SFBubbleMarkerSetting markerSetting = new SFBubbleMarkerSetting();
            markerSetting.ShowBubbles = true;
            markerSetting.MinSize =10;
            markerSetting.MaxSize =25;
            markerSetting.ValuePath=(NSString)"Population";
            //..
        }

        NSMutableArray GetDataSource()
        {
            NSMutableArray array = new NSMutableArray ();
            array.Add (getDictionary ("CA", 38332521, 24));
            array.Add (getDictionary ("NY", 19651127, 16));
            array.Add (getDictionary ("IA", 3090416, 13));

            return array;
        }

        NSDictionary getDictionary(string state,double population,int index)
        {
            
            object[] objects= new object[3];
            object[] keys=new object[3];
            keys.SetValue ("State", 0);
            keys.SetValue ("index", 1);
            keys.SetValue ("Population", 2);
            objects.SetValue ((NSString)state, 0);
            objects.SetValue (index, 1);
            objects.SetValue (population, 2);
            return NSDictionary.FromObjectsAndKeys (objects, keys);
        }


{% endhighlight %}
{% endtabs %}

![](images/bubble_android.png)  
##Legend

A legend is a key used on a map that contains swatches of symbols with descriptions. It provides valuable information for interpreting what the map is displaying and can be represented in various colors, shapes or other identifiers based on the data. It gives a breakdown of what each symbol represents throughout the map.

###Visibility

The Legends can be made visible by setting the `ShowLegend` property of LegendSettings to `true`.

##Positioning of the Legend

Based on the margin values of X and Y-axes, the Map legends can be positioned with the support of `LegendPosition` property in LegendSetting class

###Legend Icon Size

The map legend icon size can be modified by using the `IconHeight` and `IconWidth` properties in `LegendSettings`

Refer Equal color mapping code for legend support

{% tabs %}
{% highlight Xamarin.Android %}

        LegendSetting legendSetting = new LegendSetting ();
        legendSetting.ShowLegend = true;
        legendSetting.IconHeight = 20;
        legendSetting.IconWidth = 20;
        legendSetting.LegendPosition = new Point (100, 400);

        layer.LegendSetting = legendSetting;


{% endhighlight %}

{% highlight Xamarin.iOS %}

        SFMapLegendSettings legendSetting = new SFMapLegendSettings ();
        legendSetting.ShowLegend = true;
        legendSetting.IconSize = new CoreGraphics.CGSize(20,20);
        legendSetting.Position = new CoreGraphics.CGPoint (100, 400);

        layer.LegendSettings = legendSetting;


{% endhighlight %}
{% endtabs %}

![](images/legend_android.png)  