---
layout: post
title: Populate Data of Syncfusion Maps control for Xamarin.Forms 
description: How to populate the datasource
platform: xamarin
control: SfMaps 
documentation: ug
---

# Populate Data

In this section you can learn how to populate shape data for providing Data input to Map control and usage of DataSource property.

## Data Binding

The Maps control supports data binding with the dataSource property in the shape layers.

The following properties in shape layers is be used for binding datas in Maps control,

* DataSource
* ShapeIdPath
* ShapeIdTableField

### Data Source

The `DataSource` property accepts the collection values as input. For example, you can provide the list of objects as input.

### ShapeIdPath

The `ShapeIdPath` property is used to refer the data ID in DataSource. For example, population MapData contains data ids ‘Name’ and ‘Population’. The ShapeIdPath and the ShapeIdTableField properties are related to each other (refer to ShapeIdTableField for more details).

### ShapeIdTableField

The `ShapeIdTableField` property is similar to the ShapeIdPath that refers to the column name in the data property of shape layers to identify the shape. When the values of the ShapeIdPath property in the dataSource property and the value of ShapeIdTableField in the data property match, then the associated object from the dataSource is bound to the corresponding shape.

Refer the following USA Election data as datasource is used for better understanding.

{% tabs %}
{% highlight xaml %}

    <SfMaps:ShapeFileLayer>
    
        <SfMaps:ShapeFileLayer ShapeIdTableField="STATE_NAME" ShapeIdPath="State"/>
                                                    
    </SfMaps:ShapeFileLayer>           


{% endhighlight %}


{% highlight c# %}

{
    
    //..           
    layer.ShapeIdTableField ="STATE_NAME";
    layer.ShapeIdPath ="State";
    layer.DataSource = GetDataSource ();
    //..
}

JSONArray GetDataSource()
{
			
    JSONArray array = new JSONArray ();
    array.Put(getJsonObject("Alabama","Romney","9" ));
    array.Put(getJsonObject("Alaska","Romney","3" ));
    array.Put(getJsonObject("Arizona","Romney","11" ));
    array.Put(getJsonObject("Arkansas","Romney","6" ));
    array.Put(getJsonObject("California","Obama","55" ));
    array.Put(getJsonObject("Colorado","Obama","9" ));
    array.Put(getJsonObject("Connecticut","Obama","7" ));
    array.Put(getJsonObject("Delaware","Obama","3" ));
    array.Put(getJsonObject("District of Columbia","Obama","3" ));
    array.Put(getJsonObject("Florida","Obama","29" ));
    array.Put(getJsonObject("Georgia","Romney","16" ));
    array.Put(getJsonObject("Hawaii","Obama","4" ));
    array.Put(getJsonObject("Idaho","Romney","4" ));
    array.Put(getJsonObject("Illinois","Obama","20" ));
    array.Put(getJsonObject("Indiana","Romney","11" ));
    array.Put(getJsonObject("Iowa","Obama","6" ));
    array.Put(getJsonObject("Kansas","Romney","6" ));
    array.Put(getJsonObject("Kentucky","Romney","8" ));
    array.Put(getJsonObject("Louisiana","Romney","8" ));
    array.Put(getJsonObject("Maine","Obama","4" ));
    array.Put(getJsonObject("Maryland","Obama","10" ));
    array.Put(getJsonObject("Massachusetts","Obama","11" ));
    array.Put(getJsonObject("Michigan","Obama","16" ));
    array.Put(getJsonObject("Minnesota","Obama","10" ));
    array.Put(getJsonObject("Mississippi","Romney","6" ));
    array.Put(getJsonObject("Missouri","Romney","10" ));
    array.Put(getJsonObject("Montana","Romney","3" ));
    array.Put(getJsonObject("Nebraska","Romney","5" ));
    array.Put(getJsonObject("Nevada","Obama","6" ));
    array.Put(getJsonObject("New Hampshire","Obama","4" ));
    array.Put(getJsonObject("New Jersey","Obama","14" ));
    array.Put(getJsonObject("New Mexico","Obama","5" ));
    array.Put(getJsonObject("New York","Obama","29" ));
    array.Put(getJsonObject("North Carolina","Romney","15" ));
    array.Put(getJsonObject("North Dakota","Romney","3" ));
    array.Put(getJsonObject("Ohio","Obama","18" ));
    array.Put(getJsonObject("Oklahoma","Romney","7" ));
    array.Put(getJsonObject("Oregon","Obama","7" ));
    array.Put(getJsonObject("Pennsylvania","Obama","20" ));
    array.Put(getJsonObject("Rhode Island","Obama","4" ));
    array.Put(getJsonObject("South Carolina","Romney","9" ));
    array.Put(getJsonObject("South Dakota","Romney","3" ));
    array.Put(getJsonObject("Tennessee","Romney","11" ));
    array.Put(getJsonObject("Texas","Romney","38" ));
    array.Put(getJsonObject("Utah","Romney","6" ));
    array.Put(getJsonObject("Vermont","Obama","3" ));
    array.Put(getJsonObject("Virginia","Obama","13" ));
    array.Put(getJsonObject("Washington","Obama","12" ));
    array.Put(getJsonObject("West Virginia","Romney","5" ));
    array.Put(getJsonObject("Wisconsin","Obama","10" ));
    array.Put(getJsonObject("Wyoming","Romney","3" ));

    return array;
}

JSONObject getJsonObject(String state,String candidate,double electors)
{
    JSONObject obj= new JSONObject();
    obj.Put ("State", state);
    obj.Put ("Candidate", candidate);
    obj.Put ("Electors", candidate);
    return obj;
}


{% endhighlight %}


{% endtabs %}