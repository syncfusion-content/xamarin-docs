---
layout: post
title: Customization |  SfMaps |Xamarin | Syncfusion
description: customization
platform: xamarin
control: SfMaps
documentation: ug
---

# Customization

**Maps** control supports color customization to determine the exact combination of colors for shapes displayed in Maps and tooltip support to display additional information of shape data.

##Shape Settings

The shapeSettings defines the basic customization settings of shapes in the map.

* **ShapeFill** - It is used to set the fill color of the shapes in the map.
* **ShapeStroke** - It is used to set the border color of the shape in the map.
* **ShapeStrokeThickness** - It is used to set the border thickness of the shape in the map.
* **SelectedShapeColor** - It is used to set the selection color for shapes in the map.

{% tabs %}
{% highlight Xamarin.Android %}

        ShapeSetting setting = new ShapeSetting ();
        setting.ShapeFill = Color.ParseColor("#9CBF4E");
        setting.SelectedShapeColor = Color.ParseColor("#BC5353");
        setting.ShapeStroke = Color.White;
        setting.ShapeStrokeThickess = 1;
        layer.ShapeSettings = setting;

{% endhighlight %}

{% highlight Xamarin.iOS %}

        SFShapeSetting setting = new SFShapeSetting ();
        setting.Fill = UIColor.FromRGB (0x9C, 0xBF, 0x4E);
        setting.SelectedShapeColor = UIColor.FromRGB (0xBC, 0x53, 0x53);
        setting.StrokeColor = UIColor.White;
        setting.StrokeThickness = 0.5f;
        layer.ShapeSettings = setting;

{% endhighlight %}
{% endtabs %}

![](images/shapesettings_android.png)  

## Color Mapping

The **Color Mapping** support enables the customization of shape colors based on the underlying value of shape received from bounded data.

* `ColorValuePath` - It renders the field value that is to be fetched from data for each shape used for determining the shape color.
* `ValuePath` - It renders the field value that is to be fetched from data for each shape. This support also provides a tree map-like impact on the map UI. The various types of Color Mapping supported in maps are listed as follows.

###Equal Color Mapping

The EqualColorMapping is used to differentiate the shape’s fill based on its underlying value and color. The properties of equalColorMapping is listed in the following table.

<table>
<tr>
<td>
<br/>**Property**<br/><br/></td><td>
**Type**<br/><br/></td><td>
**Description**<br/><br/></td></tr>
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
{% highlight Xamarin.Android %}

	     {
            //..           
            layer.ShapeIdTableField ="STATE_NAME";
            layer.ShapeIdPath ="State";
            layer.DataSource = GetDataSource ();
            SetColorMapping(layer.ShapeSettings);
            layer.ShapeSettings.ShapeColorValuePath ="Candidate";
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

{% highlight Xamarin.iOS %}

	    {
            //..
            SetColorMapping(layer.ShapeSettings);
            layer.ShapeSettings.ColorValuePath =(NSString)"Candidate";
           //..
        }

       void SetColorMapping(SFShapeSetting setting)
        {
            NSMutableArray colorMappings = new NSMutableArray ();
            SFEqualColorMapping colorMapping1= new SFEqualColorMapping();
            colorMapping1.Value= (NSString)"Obama";
            colorMapping1.LegendLabel= (NSString)"Obama";
            colorMapping1.Color =  UIColor.FromRGB (0x31, 0x6D, 0xB5);
            colorMappings.Add(colorMapping1);

            SFEqualColorMapping colorMapping2= new SFEqualColorMapping();
            colorMapping2.Value=(NSString) "Romney";
            colorMapping2.LegendLabel= (NSString)"Romney";
            colorMapping2.Color = UIColor.FromRGB (0xD8, 0x44, 0x44);
            colorMappings.Add(colorMapping2);

            setting.ColorMappings = colorMappings;
        }


{% endhighlight %}
{% endtabs %}

![](images/colormapping_android.png)  

###Color Palette

__AutoFill__

When autoFill property is set to true, shapes are filled with default colors from built-in palettes or custom palette.


{% tabs %}
{% highlight Xamarin.Android %}
        
        layer.ShapeSettings.AutoFillColors = true;

{% endhighlight %}

{% highlight Xamarin.iOS %}

        layer.ShapeSettings.AutoFillColors = true;

{% endhighlight %}
{% endtabs %}

![](images/palette_android.png)  