---
layout : post
title : Populating data in Syncfusion Rotator control in Xamarin.Forms.
description : Learn how to set the DataSource in Rotator for Xamarin.Forms.
platform : Xamarin
control : Rotator 
documentation : ug
---

# Populating Data

## Setting ItemSource

SfRotator items can be populated with a collection of image data. Collection includes Arrays, Lists and DataTables. For example you may wants to create a SfRotator model with Image as follows.


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

Create and populate Rotator collection as follows

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

Assigning collection to ItemSource

{% highlight C# %}

 		sfRotator.BindingContext = new RotatorViewModel();

{% endhighlight %}

## Setting ItemTemplate

ItemTemplate property of SfRotator control is used to customize the contents of Rotator items.

{% highlight xaml %}

	<rotate:SfRotator x:Name="sfRotator"  Grid.Row="0" NavigationDelay="2000" ItemsSource="{Binding ImageCollection}" SelectedIndex="2" NavigationDirection="Horizontal" NavigationStripMode="Dots" BackgroundColor="#ececec" NavigationStripPosition="Bottom">
        <rotate:SfRotator.ItemTemplate>
          <DataTemplate>
            <Image  Source="{Binding Image}">
              <Image.Aspect>
                <OnPlatform x:TypeArguments="Aspect">
      			        <OnPlatform.Android>
        			          AspectFill
      			        </OnPlatform.Android>
    		        </OnPlatform>
              </Image.Aspect>
            </Image>
          </DataTemplate>
        </rotate:SfRotator.ItemTemplate>
      </rotate:SfRotator>
	  
{% endhighlight %}
