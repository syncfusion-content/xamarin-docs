---
layout : post
title : Data Binding  in Syncfusion AutoComplete control for Xamarin.Forms
description : Learn how to perform DataBinding in AutoComplete
platform : Xamarin
control : AutoComplete
documentation : ug
---

# DataBinding

SfAutoComplete control, supports binding to different data sources such as IList Data Source, XML Data Source, Observable Collection Data Source. This section explains 
about setting AutoComplete source, Item Source and applying template to the data.

## Setting AutoComplete Source

The `AutoCompleteSource` property is used to populate the list of data to the suggestions dropdown.
	
{% tabs %}	
	
{% highlight c# %}
	
	List<String> countryList = new List<String>(); 
	countryList.Add ("Iceland");
	countryList.Add ("India");
	countryList.Add ("Indonesia");
	countryList.Add ("Iran");
	countryAutoComplete.AutoCompleteSource=countryList;
	 
{% endhighlight %}

{% highlight xaml %}

  		<autocomplete:SfAutoComplete  x:Name="countryAutoComplete" HeightRequest="40" AutoCompleteSource="{Binding }" />

{% endhighlight %}

{% endtabs %}
	
![](images/autocompletesource.png)

## ItemSource

ItemSource is a collection of SfAutoComplete items which holds the ImageName and TextProperties that to be displayed in suggestions.

The SfAutoComplete model looks as follows.

{% highlight C# %}

	public AutoCompleteModel(string label,string imagestr)
	{        
         Label = label;
	     Image = imagestr;
        
    	 private string _label;

        public string Label
        {
            get { return _label; }
            set { _label = value; }
        }
		 private string _image;

        public string Image
        {
            get { return _image; }
            set { _image = value; }
        }
	}

{% endhighlight %}

Create and populate autocomplete collection as follows

{% highlight C# %}

	autoComplete.DataSource = GetItemSource();
	List<AutoCompleteModel> GetItemSource()
    {
	List<AutoCompleteModel> list = new List<AutoCompleteModel>();

	list.Add(new AutoCompleteModel("Label1","image1.png"));
    list.Add(new AutoCompleteModel("Label2","image2.png"));
	list.Add(new AutoCompleteModel("Label3","image3.png"));
    list.Add(new AutoCompleteModel("Label4","image4.png"));
    list.Add(new AutoCompleteModel("Label5","image5.png"));
	return list;
	}

{% endhighlight %}

![](images/autocompleteitemsource.png)

## Applying Template to Data 

SfAutoComplete contents can be customized by using `ItemTemplate` property. Through the ItemTemplate user can set up data bindings to the user objects.


{% highlight xaml %}

	<ResourceDictionary>
      <DataTemplate x:Key="itemTemplate">
        <StackLayout Orientation="Horizontal">
            <Label Text="{Binding Text}" />
            <Image Source="{Binding Image}"  Aspect="AspectFit"/>
         <StackLayout>
      </DataTemplate>
    </ResourceDictionary>
	
	<autocomplete:SfAutoComplete x:Name="autocomplete" ItemTemplate="{StaticResource itemTemplate}" HeightRequest="600" WidthRequest="400" />

{% endhighlight %}

![](images/autocompleteitemsource.png)

