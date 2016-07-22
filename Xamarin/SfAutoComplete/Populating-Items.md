---
layout : post
title : Data Binding  in Syncfusion AutoComplete control for Xamarin.Forms
description : Learn how to perform DataBinding in AutoComplete
platform : Xamarin
control : AutoComplete
documentation : ug
---

# Populating Items

SfAutoComplete control, supports binding to different data sources such as IList Data Source, Observable Collection Data Source. 

## Through Binding

This section explains about setting data Source and applying custom template to the data.

### Create a Model with Data

DataSource is a collection of SfAutoComplete items which is capable of holding any objects and displays the items based on the provided `DisplayMemberPath` value.

To populate items using data source, create a model class with the properties that to be bound.

{% highlight C# %}

	public class AutoCompleteModel
		{
			public AutoCompleteModel(string label, string imagestr)
			{
				Label = label;
				Image = imagestr;

			}
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

Create and populate the collection in a view model class. Here, countrylist and its flag are populated. 

{% highlight C# %}

	public class AutoCompleteViewModel
		{
			public AutoCompleteViewModel()
			{
				ItemsCollection.Add(new AutoCompleteModel("Austria", "image1.png"));
				ItemsCollection.Add(new AutoCompleteModel("Canada",  "image2.png"));
				ItemsCollection.Add(new AutoCompleteModel("Cambodia", "image3.png"));
				ItemsCollection.Add(new AutoCompleteModel("Denmark", "image4.png"));
				ItemsCollection.Add(new AutoCompleteModel("Equador", "image5.png"));
			}

			private List<AutoCompleteModel> itemsCollection = new List<AutoCompleteModel>();

			public List<AutoCompleteModel> ItemsCollection
			{
				get { return itemsCollection; }
				set { itemsCollection = value; }
			}
		}

{% endhighlight %}

![](images/autocompleteitemsource.png)

### Binding the Data with Custom Template


* Now the created collection will be bound to the data source property and `DisplayMemberPath` has to be set for displaying selected item.

{% highlight xaml %}

	
<ContentPage.Content>
			<autocomplete:SfAutoComplete x:Name="autocomplete" DisplayMemberPath="Label" DataSource="{Binding ItemsCollection}" HeightRequest="60" WidthRequest="400" />
	</ContentPage.Content>
	
{% endhighlight %}

* Setting the binding context for the items collection

{% highlight c# %}

autocomplete.BindingContext = new AutoCompleteViewModel();
	 
{% endhighlight %}

* The above code will display the object class as string. In order to display the provided data, a data template has to be created and need to bind the Model properties. This template has to be set to `ItemTemplate` property.

{% highlight xaml %}

	<ContentPage.Resources>
    	<ResourceDictionary>
     	 	<DataTemplate x:Key="itemTemplate">
       	 		<StackLayout Orientation="Horizontal">
        			<Image Source="{Binding Image}" HeightRequest="50" WidthRequest="50" Aspect="AspectFit"/>
            		<Label Text="{Binding Label}" TextColor="Black"/>            
         		</StackLayout>
      		</DataTemplate>
    	</ResourceDictionary>
 	 </ContentPage.Resources>
	
<ContentPage.Content>
			<autocomplete:SfAutoComplete x:Name="autocomplete" DisplayMemberPath="Label" ItemTemplate="{StaticResource itemTemplate}" DataSource="{Binding ItemsCollection}" HeightRequest="60" WidthRequest="400" />
	</ContentPage.Content>
	
{% endhighlight %}

N> `DisplayMemberPath` property searches for the desired value to be displayed in textbox.

![](images/autocompleteitemsource.png)

## Items AutoCompleteSource

The `AutoCompleteSource` property is used to populate the list of string to the suggestions dropdown.

	
{% highlight c# %}
	SfAutoComplete countryAutoComplete = new SfAutoComplete ();
	List<String> countryList = new List<String>(); 
	countryList.Add ("Iceland");
	countryList.Add ("India");
	countryList.Add ("Indonesia");
	countryList.Add ("Iran");
	countryAutoComplete.AutoCompleteSource=countryList;
	 
{% endhighlight %}

	
![](images/autocompletesource.png)