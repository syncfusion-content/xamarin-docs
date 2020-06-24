---
layout: post
title: Customization of Dots for Syncfusion Essential Xamarin.Forms SfRotator
description: Learn about dots customization support in Syncfusion Xamarin Rotator (SfRotator) control and more details.
platform: xamarin 
control: Rotator 
documentation: ug
---

# Customization in Xamarin Rotator (SfRotator)

The Rotator control supports to customize the dots border color, selected dots color and unselected dots color.

## DotsBorder Color

The [`DotsBorderColor`] property is used to customize the color of dots border in SfRotator.

{% tabs %}
{% highlight xaml %}

<ContentPage xmlns="http://xamarin.com/schemas/2014/forms"
             xmlns:x="http://schemas.microsoft.com/winfx/2009/xaml"
             xmlns:local="clr-namespace:Rotator"
             xmlns:syncfusion="clr-namespace:Syncfusion.SfRotator.XForms;assembly=Syncfusion.SfRotator.XForms"
             x:Class="Rotator.Rotator">
     <ContentPage.BindingContext>
        <local:RotatorViewModel/>
    </ContentPage.BindingContext>
    <ContentPage.Content>
        <syncfusion:SfRotator x:Name="rotator" 
                              ItemsSource="{Binding ImageCollection}" 
                              SelectedIndex="2"
                              BackgroundColor="#ececec"
                              NavigationStripPosition="Bottom"
                              DotsBorderColor="Aqua" >
            <syncfusion:SfRotator.ItemTemplate>
                <DataTemplate>
                    <Image  Source="{Binding Image}"/>
                </DataTemplate>
            </syncfusion:SfRotator.ItemTemplate>
        </syncfusion:SfRotator>
    </ContentPage.Content>
</ContentPage>

{% endhighlight %}
{% highlight c# %}

using Syncfusion.SfRotator.XForms;
using System;
using System.Collections.Generic;
using System.Linq;
using System.Text;
using System.Threading.Tasks;
using Xamarin.Forms;
using Xamarin.Forms.Xaml;

namespace Rotator
{
	[XamlCompilation(XamlCompilationOptions.Compile)]
	public partial class Rotator : ContentPage
	{
		public Rotator()
		{
			InitializeComponent ();
            SfRotator rotator = new SfRotator();
            var ImageCollection = new List<RotatorModel> {
            new RotatorModel ("movie1.png"),
            new RotatorModel ("movie2.png"),
            new RotatorModel ("movie3.png"),
            new RotatorModel ("movie4.png"),
            new RotatorModel ("movie5.png")
            };
            var itemTemplate = new DataTemplate(() =>
            {
                var grid = new Grid();
                var nameLabel = new Image();
                nameLabel.SetBinding(Image.SourceProperty, "Image");
                grid.Children.Add(nameLabel);
                return grid;
            });
            rotator.ItemTemplate = itemTemplate;
            rotator.DotsBorderColor = Color.Aqua;
            rotator.ItemsSource = ImageCollection;
            this.Content = rotator;
        }
	}
    public class RotatorModel
    {
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
    }
}

{% endhighlight %}
{% endtabs %}

![SfRotator with dots border color](images/DotsBorderColor.png)

## Selected Dot Color

The [`SelectedDotColor`] property is used to customize the color of selected dots in SfRotator.

{% tabs %}
{% highlight xaml %}

<ContentPage xmlns="http://xamarin.com/schemas/2014/forms"
             xmlns:x="http://schemas.microsoft.com/winfx/2009/xaml"
             xmlns:local="clr-namespace:Rotator"
             xmlns:syncfusion="clr-namespace:Syncfusion.SfRotator.XForms;assembly=Syncfusion.SfRotator.XForms"
             x:Class="Rotator.Rotator">
     <ContentPage.BindingContext>
        <local:RotatorViewModel/>
    </ContentPage.BindingContext>
    <ContentPage.Content>
        <syncfusion:SfRotator x:Name="rotator" 
                              ItemsSource="{Binding ImageCollection}" 
                              SelectedIndex="2"
                              BackgroundColor="#ececec"
                              NavigationStripPosition="Bottom"
                              DotsBorderColor="Aqua" 
                              SelectedDotColor="Blue">
            <syncfusion:SfRotator.ItemTemplate>
                <DataTemplate>
                    <Image  Source="{Binding Image}"/>
                </DataTemplate>
            </syncfusion:SfRotator.ItemTemplate>
        </syncfusion:SfRotator>
    </ContentPage.Content>
</ContentPage>

{% endhighlight %}
{% highlight c# %}

using Syncfusion.SfRotator.XForms;
using System;
using System.Collections.Generic;
using System.Linq;
using System.Text;
using System.Threading.Tasks;
using Xamarin.Forms;
using Xamarin.Forms.Xaml;

namespace Rotator
{
	[XamlCompilation(XamlCompilationOptions.Compile)]
	public partial class Rotator : ContentPage
	{
		public Rotator()
		{
			InitializeComponent ();
            SfRotator rotator = new SfRotator();
            var ImageCollection = new List<RotatorModel> {
            new RotatorModel ("movie1.png"),
            new RotatorModel ("movie2.png"),
            new RotatorModel ("movie3.png"),
            new RotatorModel ("movie4.png"),
            new RotatorModel ("movie5.png")
            };
            var itemTemplate = new DataTemplate(() =>
            {
                var grid = new Grid();
                var nameLabel = new Image();
                nameLabel.SetBinding(Image.SourceProperty, "Image");
                grid.Children.Add(nameLabel);
                return grid;
            });
            rotator.ItemTemplate = itemTemplate;
            rotator.DotsBorderColor = Color.Aqua;
            rotator.SelectedDotColor = Color.Blue;
            rotator.ItemsSource = ImageCollection;
            this.Content = rotator;
        }
	}
    public class RotatorModel
    {
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
    }
}

{% endhighlight %}
{% endtabs %}

![SfRotator with selected dot color](images/SelectedDotColor.png)

## Unselected Dot Color

The [`UnselectedDotColor`] property is used to customize the color of unselected dots in SfRotator.

{% tabs %}
{% highlight xaml %}

<ContentPage xmlns="http://xamarin.com/schemas/2014/forms"
             xmlns:x="http://schemas.microsoft.com/winfx/2009/xaml"
             xmlns:local="clr-namespace:Rotator"
             xmlns:syncfusion="clr-namespace:Syncfusion.SfRotator.XForms;assembly=Syncfusion.SfRotator.XForms"
             x:Class="Rotator.Rotator">
     <ContentPage.BindingContext>
        <local:RotatorViewModel/>
    </ContentPage.BindingContext>
    <ContentPage.Content>
        <syncfusion:SfRotator x:Name="rotator" 
                              ItemsSource="{Binding ImageCollection}" 
                              SelectedIndex="2"
                              BackgroundColor="#ececec"
                              NavigationStripPosition="Bottom"
                              DotsBorderColor="Aqua" 
                              SelectedDotColor="Blue"
                              UnselectedDotColor="Gray">
            <syncfusion:SfRotator.ItemTemplate>
                <DataTemplate>
                    <Image  Source="{Binding Image}"/>
                </DataTemplate>
            </syncfusion:SfRotator.ItemTemplate>
        </syncfusion:SfRotator>
    </ContentPage.Content>
</ContentPage>

{% endhighlight %}
{% highlight c# %}

using Syncfusion.SfRotator.XForms;
using System;
using System.Collections.Generic;
using System.Linq;
using System.Text;
using System.Threading.Tasks;
using Xamarin.Forms;
using Xamarin.Forms.Xaml;

namespace Rotator
{
	[XamlCompilation(XamlCompilationOptions.Compile)]
	public partial class Rotator : ContentPage
	{
		public Rotator()
		{
			InitializeComponent ();
            SfRotator rotator = new SfRotator();
            var ImageCollection = new List<RotatorModel> {
            new RotatorModel ("movie1.png"),
            new RotatorModel ("movie2.png"),
            new RotatorModel ("movie3.png"),
            new RotatorModel ("movie4.png"),
            new RotatorModel ("movie5.png")
            };
            var itemTemplate = new DataTemplate(() =>
            {
                var grid = new Grid();
                var nameLabel = new Image();
                nameLabel.SetBinding(Image.SourceProperty, "Image");
                grid.Children.Add(nameLabel);
                return grid;
            });
            rotator.ItemTemplate = itemTemplate;
            rotator.DotsBorderColor = Color.Aqua;
            rotator.SelectedDotColor = Color.Blue;
            rotator.UnselectedDotColor = Color.Gray;
            rotator.ItemsSource = ImageCollection;
            this.Content = rotator;
        }
	}
    public class RotatorModel
    {
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
    }
}

{% endhighlight %}
{% endtabs %}

![SfRotator with unselected dot color](images/UnselectedDotColor.png)