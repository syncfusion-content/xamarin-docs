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

SfRotator items can be populated with a collection of image data. You can assign a collection to it. Collections include arrays, Lists and DataTables.For example you may wants to create a rotator model.

The Rotator model looks like as follows.

{% highlight C# %}
	
	public RotatorModel(string imagestr,string name)
        {
            Image = imagestr;
            Name = name;
        }
        private String _image;

        public String Image
        {
            get { return _image; }
            set { _image = value; }
        }

        private String name;

        public String Name
        {
            get { return name; }
            set { name = value; }
        }

{% endhighlight %}

Create and populate rotator collection as follows

{% highlight C# %}

	public RotatorViewModel()
        {
            ImageCollection.Add(new RotatorModel("movie1.png","Autor: Stephen Haunts"));
            ImageCollection.Add(new RotatorModel("movie2.png", "Autor: Macro Breveglieri"));
            ImageCollection.Add(new RotatorModel("movie3.png", "Autor: Peter Shaw"));
            ImageCollection.Add(new RotatorModel("movie4.png", "Autor: Del Sole"));
            ImageCollection.Add(new RotatorModel("movie5.png", "Autor: Marko Valjeik"));
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

ItemTemplate property of Rotator control is used to customize the contents of rotator items.

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
