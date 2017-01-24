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

The following properties in shape layers is be used for binding data in Maps control,

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

        List<ElectionData> GetDataSource()
        {
            List<ElectionData> list = new List<ElectionData>();
            list.Add(new ElectionData("Alabama","Romney",9 ));
            list.Add(new ElectionData("Alaska","Romney", 3));
            list.Add(new ElectionData("Arizona", "Romney", 11));
            list.Add(new ElectionData("Arkansas", "Romney", 6));
            list.Add(new ElectionData("California", "Romney", 55));
            list.Add(new ElectionData("Colorado", "Obama", 9));
            list.Add(new ElectionData("Connecticut", "Obama", 7));
            list.Add(new ElectionData("Delaware","Obama", 3));
            list.Add(new ElectionData("District of Columbia", "Obama", 3));
            list.Add(new ElectionData("Florida", "Obama", 29));
            list.Add(new ElectionData("Georgia", "Obama", 16));
            list.Add(new ElectionData("Hawaii", "Romney", 4));
            list.Add(new ElectionData("Idaho", "Obama", 4));
            list.Add(new ElectionData("Illinois","Romney", 20));
            list.Add(new ElectionData("Indiana", "Obama", 11));
            list.Add(new ElectionData("Iowa", "Romney", 6));
            list.Add(new ElectionData("Kansas", "Obama", 6));
            list.Add(new ElectionData("Kentucky", "Romney", 8));
            list.Add(new ElectionData("Louisiana", "Romney", 8));
            list.Add(new ElectionData("Maine", "Romney", 4));
            list.Add(new ElectionData("Maryland", "Obama", 10));
            list.Add(new ElectionData("Massachusetts","Obama", 11));
            list.Add(new ElectionData("Michigan","Obama", 16));
            list.Add(new ElectionData("Minnesota", "Obama", 10));
            list.Add(new ElectionData("Mississippi", "Obama", 6));
            list.Add(new ElectionData("Missouri", "Obama", 10));
            list.Add(new ElectionData("Montana", "Romney", 3));
            list.Add(new ElectionData("Nebraska", "Romney", 5));
            list.Add(new ElectionData("Nevada", "Romney", 6));
            list.Add(new ElectionData("New Hampshire", "Obama", 4));
            list.Add(new ElectionData("New Jersey", "Obama", 14));
            list.Add(new ElectionData("New Mexico", "Obama", 5));
            list.Add(new ElectionData("New York", "Obama", 29));
            list.Add(new ElectionData("North Carolina", "Romney", 15));
            list.Add(new ElectionData("North Dakota", "Romney", 3));
            list.Add(new ElectionData("Ohio", "Obama", 18));
            list.Add(new ElectionData("Oklahoma", "Romney", 7));
            list.Add(new ElectionData("Oregon", "Obama", 7));
            list.Add(new ElectionData("Pennsylvania", "Obama", 20));
            list.Add(new ElectionData("Rhode Island", "Obama", 4));
            list.Add(new ElectionData("South Carolina", "Romney", 9));
            list.Add(new ElectionData("South Dakota", "Romney", 3));
            list.Add(new ElectionData("Tennessee", "Romney", 11));
            list.Add(new ElectionData("Texas", "Romney", 38));
            list.Add(new ElectionData("Utah", "Romney",6));
            list.Add(new ElectionData("Vermont", "Obama", 3));
            list.Add(new ElectionData("Virginia", "Obama", 13));
            list.Add(new ElectionData("Washington", "Obama", 12));
            list.Add(new ElectionData("West Virginia", "Romney", 5));
            list.Add(new ElectionData("Wisconsin","Obama", 10));
            list.Add(new ElectionData("Wyoming", "Romney", 3));
            return list;
         }


      public class ElectionData
	  {
		public ElectionData(string state,string candidate ,int electors)
		{
		    State = state;
			Candidate = candidate;
			Electors = electors;
		}

		public string State {
			get;
			set;
		}

		public string Candidate {
			get;
			set;
		}

		public int Electors {
			get;
			set;
		}
	}



{% endhighlight %}


{% endtabs %}