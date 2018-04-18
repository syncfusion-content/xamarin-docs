---
layout : post
title : Data Binding in Syncfusion Rotator control in Xamarin.Forms.
description : Learn how to set the DataSource in Rotator for Xamarin.Forms.
platform : Xamarin
control : Rotator 
documentation : ug
---

# Populating Data

SfRotator control supports binding to different data sources such as IList Data Source, Observable Collection Data Source.

## Through Binding

This section explains about setting Item Source and applying custom template to the data.

### Create a Model with Data

SfRotator items can be populated with a collection of image data. You can assign a collection to it. Collections include arrays, Lists and DataTables. For example you may wants to create a Rotator model with Image as follows.

{% tabs %}

{% highlight C# %}
	
public RotatorModel(string imageString)
{
    Image = imageString;       
}
private String _image;
public String Image
{
    get { return _image; }
    set { _image = value; }
}       

{% endhighlight %}

{% endtabs %}

Create and populate SfRotator collection as follows

{% tabs %}

{% highlight C# %}

public RotatorViewModel()
{
    ImageCollection.Add(new RotatorModel("movie1.png"));
    ImageCollection.Add(new RotatorModel("movie2.png"));
    ImageCollection.Add(new RotatorModel("movie3.png"));
    ImageCollection.Add(new RotatorModel("movie4.png"));
    ImageCollection.Add(new RotatorModel("movie5.png"));
}
private List<RotatorModel> imageCollection = new List<RotatorModel>();

public List<RotatorModel> ImageCollection
{
    get { return imageCollection; }
    set { imageCollection = value; }
}

{% endhighlight %}

{% endtabs %}

Assigning collection to ItemSource

{% tabs %}

{% highlight C# %}

 rotator.BindingContext = new RotatorViewModel();

{% endhighlight %}

{% endtabs %}

### Binding the Data with Custom Template

SfRotator provides support to add a custom view as RotatorItems by designing a view inside its ItemTemplate. This template will be applied for all its items and its data will be binded.

{% tabs %}

{% highlight xaml %}

<syncfusion:SfRotator x:Name="rotator"  Grid.Row="0" NavigationDelay="2000" ItemsSource="{Binding ImageCollection}" SelectedIndex="2" NavigationDirection="Horizontal" NavigationStripMode="Dots" BackgroundColor="#ececec" NavigationStripPosition="Bottom">
  <syncfusion:SfRotator.ItemTemplate>
    <DataTemplate>
      <Image  Source="{Binding Image}"/>
    </DataTemplate>
  </syncfusion:SfRotator.ItemTemplate>
</syncfusion:SfRotator>
	  
{% endhighlight %}

{% endtabs %}

## Through Rotator Item

The ItemTemplate provides common template with different data, whereas if different views for every items is needed, it can also be provided using `ItemContent` property  in SfRotatorItem class.

{% tabs %}

{% highlight C# %}

SfRotator rotator = new SfRotator();
SfRotatorItem item = new SfRotatorItem();
List<SfRotatorItem> rotatorItem = new List<SfRotatorItem>();
Label label = new Label();
label.Text = "Item no 1";
label.BackgroundColor = Color.Gray;
label.FontSize = 50;
label.VerticalTextAlignment = TextAlignment.Center;
item.ItemContent = label;
rotatorItem.Add((item));
rotator.ItemsSource = rotatorItem;


SfRotatorItem item = new SfRotatorItem();
List<SfRotatorItem> rotatorItem1 = new List<SfRotatorItem>();
Image image = new Image();
image.Source = ImageSource.FromFile("movies.png");
image.Aspect = Aspect.AspectFit;
image.VerticalOptions = LayoutOptions.Center;
image.HeightRequest = 400;
image.WidthRequest = 400;
item.ItemContent = image;
rotatorItem1.Add(item);
rotator.ItemsSource = rotatorItem1;         
 

this.Content=rotator;		
	  
{% endhighlight %}

{% endtabs %}

And also rotator provides a support to display only the Image data with `Image` property in SfRotatorItem class.

{% tabs %}

{% highlight C# %}

public partial class RotatorControlPage : ContentPage
{
	public RotatorControlPage()
	{
		InitializeComponent();

		SfRotator rotator = new SfRotator();

		List<SfRotatorItem> collectionOfItems = new List<SfRotatorItem>();
		collectionOfItems.Add(new SfRotatorItem() { Image = "movie1.png" });
		collectionOfItems.Add(new SfRotatorItem() { Image = "movie2.png" });
		collectionOfItems.Add(new SfRotatorItem() { Image = "movie3.png" });
		collectionOfItems.Add(new SfRotatorItem() { Image = "movie4.png" });
		collectionOfItems.Add(new SfRotatorItem() { Image = "movie5.png" });

		rotator.ItemsSource = collectionOfItems;
		this.Content = rotator;

	}
}


{% endhighlight %}

{% endtabs %}

Similarly every item can be created and customized in case of different Rotator item view is needed.
