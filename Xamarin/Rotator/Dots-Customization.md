---
layout: post
title: Dots Customization in Xamarin Rotator Control | Syncfusion
description: Explore the customization options for dots in the Syncfusion Xamarin Rotator (SfRotator) control, including border, selected, and unselected dot colors.
platform: xamarin 
control: Rotator 
documentation: ug
---

# Dots Customization in Xamarin Rotator (SfRotator)

The Xamarin Rotator control allows you to customize the appearance of the pagination dots, including options to modify the border color of the dots, as well as the colors for selected and unselected dots. These customizations can enhance the aesthetics of your mobile application and provide visual feedback to users.
## Dots Border Color

The [`DotsBorderColor`](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfRotator.XForms.SfRotator.html#Syncfusion_SfRotator_XForms_SfRotator_DotsBorderColor) property customizes the color of the dots' border within an [`SfRotator`](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfRotator.XForms.SfRotator.html) control.

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

The [`SelectedDotColor`](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfRotator.XForms.SfRotator.html#Syncfusion_SfRotator_XForms_SfRotator_SelectedDotColor) property is used to customize the color of selected dots in [`SfRotator`](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfRotator.XForms.SfRotator.html).

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

The [`UnselectedDotColor`](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfRotator.XForms.SfRotator.html#Syncfusion_SfRotator_XForms_SfRotator_UnselectedDotColor) property is used to customize the color of unselected dots in [`SfRotator`](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfRotator.XForms.SfRotator.html).

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

## Selected Dot Color

The [`SelectedDotColor`](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfRotator.XForms.SfRotator.html#Syncfusion_SfRotator_XForms_SfRotator_SelectedDotColor) property allows customization of the color for the currently selected dot in an [`SfRotator`](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfRotator.XForms.SfRotator.html) control.

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
                              Placement="Bottom"
                              DotsBorderColor="Aqua"
                              SelectedDotColor="Blue">
            <syncfusion:SfRotator.ItemTemplate>
                <DataTemplate>
                    <Image Source="{Binding Image}"/>
                </DataTemplate>
            </syncfusion:SfRotator.ItemTemplate>
        </syncfusion:SfRotator>
    </ContentPage.Content>
</ContentPage>

{% endhighlight %}
{% highlight csharp %}

using Syncfusion.SfRotator.XForms;
using Xamarin.Forms;
using Xamarin.Forms.Xaml;
using System.Collections.Generic;

namespace Rotator
{
    [XamlCompilation(XamlCompilationOptions.Compile)]
    public partial class Rotator : ContentPage
    {
        public Rotator()
        {
            InitializeComponent();
            SfRotator rotator = new SfRotator();
            var imageCollection = new List<RotatorModel>
            {
                new RotatorModel("movie1.png"),
                new RotatorModel("movie2.png"),
                new RotatorModel("movie3.png"),
                new RotatorModel("movie4.png"),
                new RotatorModel("movie5.png")
            };
            var itemTemplate = new DataTemplate(() =>
            {
                var grid = new Grid();
                var image = new Image();
                image.SetBinding(Image.SourceProperty, "Image");
                grid.Children.Add(image);
                return grid;
            });
            rotator.ItemTemplate = itemTemplate;
            rotator.DotsBorderColor = Color.Aqua;
            rotator.SelectedDotColor = Color.Blue;
            rotator.ItemsSource = imageCollection;
            this.Content = rotator;
        }
    }

    public class RotatorModel
    {
        public RotatorModel(string imageString)
        {
            Image = imageString;
        }

        public string Image { get; set; }
    }
}

{% endhighlight %}
{% endtabs %}

![SfRotator with selected dot color](images/SelectedDotColor.png)

## Unselected Dot Color

The [`UnselectedDotColor`](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfRotator.XForms.SfRotator.html#Syncfusion_SfRotator_XForms_SfRotator_UnselectedDotColor) property customizes the color of the unselected dots in an [`SfRotator`](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfRotator.XForms.SfRotator.html) control.

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
                              Placement="Bottom"
                              DotsBorderColor="Aqua"
                              SelectedDotColor="Blue"
                              UnselectedDotColor="Gray">
            <syncfusion:SfRotator.ItemTemplate>
                <DataTemplate>
                    <Image Source="{Binding Image}"/>
                </DataTemplate>
            </syncfusion:SfRotator.ItemTemplate>
        </syncfusion:SfRotator>
    </ContentPage.Content>
</ContentPage>

{% endhighlight %}
{% highlight csharp %}

using Syncfusion.SfRotator.XForms;
using Xamarin.Forms;
using Xamarin.Forms.Xaml;
using System.Collections.Generic;

namespace Rotator
{
    [XamlCompilation(XamlCompilationOptions.Compile)]
    public partial class Rotator : ContentPage
    {
        public Rotator()
        {
            InitializeComponent();
            SfRotator rotator = new SfRotator();
            var imageCollection = new List<RotatorModel>
            {
                new RotatorModel("movie1.png"),
                new RotatorModel("movie2.png"),
                new RotatorModel("movie3.png"),
                new RotatorModel("movie4.png"),
                new RotatorModel("movie5.png")
            };
            var itemTemplate = new DataTemplate(() =>
            {
                var grid = new Grid();
                var image = new Image();
                image.SetBinding(Image.SourceProperty, "Image");
                grid.Children.Add(image);
                return grid;
            });
            rotator.ItemTemplate = itemTemplate;
            rotator.DotsBorderColor = Color.Aqua;
            rotator.SelectedDotColor = Color.Blue;
            rotator.UnselectedDotColor = Color.Gray;
            rotator.ItemsSource = imageCollection;
            this.Content = rotator;
        }
    }

    public class RotatorModel
    {
        public RotatorModel(string imageString)
        {
            Image = imageString;
        }

        public string Image { get; set; }
    }
}

{% endhighlight %}
{% endtabs %}

![SfRotator with unselected dot color](images/UnselectedDotColor.png)
