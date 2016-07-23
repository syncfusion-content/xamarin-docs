---
layout : post
title : Data Binding in Syncfusion Rotator control in Xamarin.Forms.
description : Learn how to set the DataSource in Rotator for Xamarin.Forms.
platform : Xamarin
control : Rotator 
documentation : ug
---

# Populating Data

SfRotator control, supports binding to different data sources such as IList Data Source, Observable Collection Data Source.

## Through Binding

This section explains about setting Item Source and applying custom template to the data.

### Create a Model with Data

SfRotator items can be populated with a collection of image data. You can assign a collection to it. Collections include arrays, Lists and DataTables. For example you may wants to create a Rotator model with Image as follows.

{% tabs %}

{% highlight C# %}
	
	public RotatorModel(string imagestr)
        {
            Image = imagestr;
           
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

	<rotator:SfRotator x:Name="rotator"  Grid.Row="0" NavigationDelay="2000" ItemsSource="{Binding ImageCollection}" SelectedIndex="2" NavigationDirection="Horizontal" NavigationStripMode="Dots" BackgroundColor="#ececec" NavigationStripPosition="Bottom">
        <rotator:SfRotator.ItemTemplate>
          <DataTemplate>
            <Image  Source="{Binding Image}"/>
          </DataTemplate>
        </rotator:SfRotator.ItemTemplate>
      </rotator:SfRotator>
	  
{% endhighlight %}

{% endtabs %}

## Through Rotator Item

The ItemTemplate provides common template with different data, whereas if different views for every items is needed, it can also be provided using `ItemContent` property in SfRotatorItem class.

{% tabs %}

{% highlight C# %}

	SfRotator rotator = new SfRotator();	
	SfRotatorItem rotatorItem = new SfRotatorItem ();
	Label lbl = new Label ();
	lbl.Text ="  Item No: 1 ";
	lbl.BackgroundColor = Color.Gray;
	lbl.FontSize = 20;
	lbl.VerticalTextAlignment = TextAlignment.Center;
	rotatorItem.ItemContent =lbl;
	rotator.DataSource.Add (rotatorItem);	

	SfRotatorItem rotatorItem1 = new SfRotatorItem ();
	Image img = new Image ();
	img.Source = ImageSource.FromFile("image2.png");
	img.Aspect = Aspect.AspectFit;
	img.VerticalOptions = LayoutOptions.Center;
	img.HeightRequest = 400;
	img.WidthRequest = 400;
	rotatorItem1.ItemContent =img;
	rotator.DataSource.Add (rotatorItem1);		
	  
{% endhighlight %}

{% endtabs %}

Similarly every item can be created and customized in case of different Rotator item view is needed.
