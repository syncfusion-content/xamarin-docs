---
layout: post
title: Populate Data of Syncfusion Maps control for Xamarin.Forms 
description: How to populate the datasource
platform: xamarin
control: SfMaps 
documentation: ug
---

# Populate Data

This section explains how to populate shape data for providing data input to the maps control and usage of the `ItemsSource` property.

## Data binding

The maps control supports data binding using the `ItemsSource` property in the shape layers.

The following properties in shape layers are used for binding data in the maps control:

* ItemsSource
* ShapeIDPath
* ShapeIdTableField

### ItemsSource

The [`ItemsSource`](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfMaps.XForms.ShapeFileLayer.html#Syncfusion_SfMaps_XForms_ShapeFileLayer_ItemsSource) property accepts the collection values as input. 

### ShapeIDPath

The [`ShapeIDPath`](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfMaps.XForms.ShapeFileLayer.html#Syncfusion_SfMaps_XForms_ShapeFileLayer_ShapeIDPath) property refers the data ID in `ItemsSource`.

### ShapeIDTableField

The [`ShapeIDTableField`](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfMaps.XForms.ShapeFileLayer.html#Syncfusion_SfMaps_XForms_ShapeFileLayer_ShapeIDTableField) property is similar to the `ShapeIdPath`; it refers to the column name in the data property of shape layers to identify the shape. When the values of the `ShapeIdPath` property in the `ItemsSource` property and the values of `ShapeIdTableField` in the data property match, the associated object from the ItemsSource will be bound to the corresponding shape.

{% tabs %}

{% highlight xaml %}

<maps:SfMaps x:Name="sfmap"    BackgroundColor="White" >

<maps:SfMaps.BindingContext>
<local:ViewModel></local:ViewModel>
</maps:SfMaps.BindingContext>

<maps:SfMaps.Layers >
<maps:ShapeFileLayer Uri="usa_state.shp" ItemsSource="{Binding Data}"
                  ShapeIDPath="State" ShapeIDTableField="STATE_NAME" >
</maps:ShapeFileLayer>
</maps:SfMaps.Layers>
</maps:SfMaps>

{% endhighlight %}

{% highlight c# %}

    ShapeFileLayer layer = new ShapeFileLayer();
            layer.Uri = "usa_state.shp";
            layer.ItemsSource =viewModel.Data;
            layer.ShapeIDTableField = "STATE_NAME";
            layer.ShapeIDPath = "State";
			map.BackgroundColor = Color.White;
            map.Layers.Add(layer);

{% endhighlight %}

{% endtabs %}

The following code sample demonstrates referring the United States election data as items source.

{% highlight c# %}

    public class ViewModel
    {
        public ObservableCollection<ElectionData> Data { get; set; }
        public ViewModel()
        {
            Data = new ObservableCollection<ElectionData>();
            Data.Add(new ElectionData("Alabama", "Romney", 9));
            Data.Add(new ElectionData("Alaska", "Romney", 3));
            Data.Add(new ElectionData("Arizona", "Romney", 11));
            Data.Add(new ElectionData("Arkansas", "Romney", 6));
            Data.Add(new ElectionData("California", "Romney", 55));
            Data.Add(new ElectionData("Colorado", "Obama", 9));
            Data.Add(new ElectionData("Connecticut", "Obama", 7));
            Data.Add(new ElectionData("Delaware", "Obama", 3));
            Data.Add(new ElectionData("District of Columbia", "Obama", 3));
            Data.Add(new ElectionData("Florida", "Obama", 29));
            Data.Add(new ElectionData("Georgia", "Obama", 16));
            Data.Add(new ElectionData("Hawaii", "Romney", 4));
            Data.Add(new ElectionData("Idaho", "Obama", 4));
            Data.Add(new ElectionData("Illinois", "Romney", 20));
            Data.Add(new ElectionData("Indiana", "Obama", 11));
            Data.Add(new ElectionData("Iowa", "Romney", 6));
            Data.Add(new ElectionData("Kansas", "Obama", 6));
            Data.Add(new ElectionData("Kentucky", "Romney", 8));
            Data.Add(new ElectionData("Louisiana", "Romney", 8));
            Data.Add(new ElectionData("Maine", "Romney", 4));
            Data.Add(new ElectionData("Maryland", "Obama", 10));
            Data.Add(new ElectionData("Massachusetts", "Obama", 11));
            Data.Add(new ElectionData("Michigan", "Obama", 16));
            Data.Add(new ElectionData("Minnesota", "Obama", 10));
            Data.Add(new ElectionData("Mississippi", "Obama", 6));
            Data.Add(new ElectionData("Missouri", "Obama", 10));
            Data.Add(new ElectionData("Montana", "Romney", 3));
            Data.Add(new ElectionData("Nebraska", "Romney", 5));
            Data.Add(new ElectionData("Nevada", "Romney", 6));
            Data.Add(new ElectionData("New Hampshire", "Obama", 4));
            Data.Add(new ElectionData("New Jersey", "Obama", 14));
            Data.Add(new ElectionData("New Mexico", "Obama", 5));
            Data.Add(new ElectionData("New York", "Obama", 29));
            Data.Add(new ElectionData("North Carolina", "Romney", 15));
            Data.Add(new ElectionData("North Dakota", "Romney", 3));
            Data.Add(new ElectionData("Ohio", "Obama", 18));
            Data.Add(new ElectionData("Oklahoma", "Romney", 7));
            Data.Add(new ElectionData("Oregon", "Obama", 7));
            Data.Add(new ElectionData("Pennsylvania", "Obama", 20));
            Data.Add(new ElectionData("Rhode Island", "Obama", 4));
            Data.Add(new ElectionData("South Carolina", "Romney", 9));
            Data.Add(new ElectionData("South Dakota", "Romney", 3));
            Data.Add(new ElectionData("Tennessee", "Romney", 11));
            Data.Add(new ElectionData("Texas", "Romney", 38));
            Data.Add(new ElectionData("Utah", "Romney", 6));
            Data.Add(new ElectionData("Vermont", "Obama", 3));
            Data.Add(new ElectionData("Virginia", "Obama", 13));
            Data.Add(new ElectionData("Washington", "Obama", 12));
            Data.Add(new ElectionData("West Virginia", "Romney", 5));
            Data.Add(new ElectionData("Wisconsin", "Obama", 10));
            Data.Add(new ElectionData("Wyoming", "Romney", 3));
        }
    }

    public class ElectionData
    {
        public ElectionData(string state, string candidate, int electors)
        {
            State = state;
            Candidate = candidate;
            Electors = electors;
        }

        public string State
        {
            get;
            set;
        }

        public string Candidate
        {
            get;
            set;
        }

        public int Electors
        {
            get;
            set;
        }
    }


{% endhighlight %}
