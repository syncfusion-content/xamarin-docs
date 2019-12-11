---
layout: post
title: Sliding Direction in Syncfusion Rotator control
description: Learn how to set the autoplay option, loop the items, enable Text Area  and choose the navigation direction in Rotator control for Xamarin.Forms
platform: xamarin 
control: Rotator
documentation: ug
---

# Sliding Direction

The `NavigationDirection` property specifies the direction in which items should be navigated in SfRotator control.

## Horizontal

Rotator Items can be navigated in horizontal direction.

{% tabs %}

{% highlight xaml %}

<ContentPage xmlns="http://xamarin.com/schemas/2014/forms"
             xmlns:x="http://schemas.microsoft.com/winfx/2009/xaml"
             xmlns:local="clr-namespace:RangeSlider"
             xmlns:syncfusion="clr-namespace:Syncfusion.SfRotator.XForms;assembly=Syncfusion.SfRotator.XForms"
             x:Class="RangeSlider.Rotator">
    <ContentPage.BindingContext>
        <local:RotatorViewModel/>
    </ContentPage.BindingContext>
    <ContentPage.Content>
        <syncfusion:SfRotator x:Name="rotator" 
                        NavigationDelay="2000" 
                        ItemsSource="{Binding ImageCollection}" 
                        SelectedIndex="2"
                        NavigationDirection="Horizontal"
                        NavigationStripMode="Thumbnail" 
                        BackgroundColor="#ececec"
                        EnableAutoPlay="true"
                        EnableLooping="true"
                        NavigationStripPosition="Bottom">
            <syncfusion:SfRotator.ItemTemplate>
                <DataTemplate>
                    <Image  Source="{Binding Image}"/>
                </DataTemplate>
            </syncfusion:SfRotator.ItemTemplate>
        </syncfusion:SfRotator>
    </ContentPage.Content>
</ContentPage>

{% endhighlight %}

{% highlight C# %}

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
            rotator.NavigationStripMode = NavigationStripMode.Thumbnail;
			rotator.NavigationDirection = NavigationDirection.Horizontal;
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

## Vertical

Rotator Items can be navigated in vertical direction.

{% tabs %}

{% highlight xaml %}

<ContentPage xmlns="http://xamarin.com/schemas/2014/forms"
             xmlns:x="http://schemas.microsoft.com/winfx/2009/xaml"
             xmlns:local="clr-namespace:RangeSlider"
             xmlns:syncfusion="clr-namespace:Syncfusion.SfRotator.XForms;assembly=Syncfusion.SfRotator.XForms"
             x:Class="RangeSlider.Rotator">
    <ContentPage.BindingContext>
        <local:RotatorViewModel/>
    </ContentPage.BindingContext>
    <ContentPage.Content>
        <syncfusion:SfRotator x:Name="rotator" 
                        NavigationDelay="2000" 
                        ItemsSource="{Binding ImageCollection}" 
                        SelectedIndex="2"
                        NavigationDirection="Vertical"
                        NavigationStripMode="Thumbnail" 
                        BackgroundColor="#ececec"
                        EnableAutoPlay="true"
                        EnableLooping="true"
                        NavigationStripPosition="Bottom">
            <syncfusion:SfRotator.ItemTemplate>
                <DataTemplate>
                    <Image  Source="{Binding Image}"/>
                </DataTemplate>
            </syncfusion:SfRotator.ItemTemplate>
        </syncfusion:SfRotator>
    </ContentPage.Content>
</ContentPage>	

{% endhighlight %}

{% highlight C# %}

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
            rotator.NavigationStripMode = NavigationStripMode.Thumbnail;
	        rotator.NavigationDirection = NavigationDirection.Vertical;
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

## LeftToRight

Rotator items can be navigate from Left to Right only.

{% tabs %}

{% highlight xaml %}

<?xml version="1.0" encoding="utf-8" ?>
<ContentPage xmlns="http://xamarin.com/schemas/2014/forms"
             xmlns:x="http://schemas.microsoft.com/winfx/2009/xaml"
             xmlns:d="http://xamarin.com/schemas/2014/forms/design"
             xmlns:mc="http://schemas.openxmlformats.org/markup-compatibility/2006"
             mc:Ignorable="d"
             xmlns:rotator="clr-namespace:Syncfusion.SfRotator.XForms;assembly=Syncfusion.SfRotator.XForms"
             x:Class="RotatorNavigation.MainPage">
    
    <StackLayout>
        <rotator:SfRotator NavigationDirection="LeftToRight" x:Name="rotator"/>
    </StackLayout>

</ContentPage>

{% endhighlight %}

{% highlight C# %}

public partial class MainPage : ContentPage
{
    SfRotator rotator;
    StackLayout stackLayoout;
    public MainPage()
    {
        InitializeComponent();
        rotator = new SfRotator();
        stackLayoout = new StackLayout();
        rotator.NavigationDirection = NavigationDirection.LeftToRight;
        stackLayoout.Children.Add(rotator);
        this.Content = stackLayoout;
    }
}

{% endhighlight %}

{% endtabs %}

## RightToLeft

Rotator items can be navigate from Right to Left only.

{% tabs %}

{% highlight xaml %}

<?xml version="1.0" encoding="utf-8" ?>
<ContentPage xmlns="http://xamarin.com/schemas/2014/forms"
             xmlns:x="http://schemas.microsoft.com/winfx/2009/xaml"
             xmlns:d="http://xamarin.com/schemas/2014/forms/design"
             xmlns:mc="http://schemas.openxmlformats.org/markup-compatibility/2006"
             mc:Ignorable="d"
             xmlns:rotator="clr-namespace:Syncfusion.SfRotator.XForms;assembly=Syncfusion.SfRotator.XForms"
             x:Class="RotatorNavigation.MainPage">
    
    <StackLayout>
        <rotator:SfRotator NavigationDirection="RightToLeft" x:Name="rotator"/>
    </StackLayout>

</ContentPage>

{% endhighlight %}

{% highlight C# %}

public partial class MainPage : ContentPage
{
    SfRotator rotator;
    StackLayout stackLayoout;
    public MainPage()
    {
        InitializeComponent();
        rotator = new SfRotator();
        stackLayoout = new StackLayout();
        rotator.NavigationDirection = NavigationDirection.RightToLeft;
        stackLayoout.Children.Add(rotator);
        this.Content = stackLayoout;
    }
}

{% endhighlight %}

{% endtabs %}

## TopToBottom

Rotator items can be navigate from Top to Bottom only.

{% tabs %}

{% highlight xaml %}

<?xml version="1.0" encoding="utf-8" ?>
<ContentPage xmlns="http://xamarin.com/schemas/2014/forms"
             xmlns:x="http://schemas.microsoft.com/winfx/2009/xaml"
             xmlns:d="http://xamarin.com/schemas/2014/forms/design"
             xmlns:mc="http://schemas.openxmlformats.org/markup-compatibility/2006"
             mc:Ignorable="d"
             xmlns:rotator="clr-namespace:Syncfusion.SfRotator.XForms;assembly=Syncfusion.SfRotator.XForms"
             x:Class="RotatorNavigation.MainPage">
    
    <StackLayout>
        <rotator:SfRotator NavigationDirection="TopToBottom" x:Name="rotator"/>
    </StackLayout>

</ContentPage>

{% endhighlight %}

{% highlight C# %}

public partial class MainPage : ContentPage
{
    SfRotator rotator;
    StackLayout stackLayoout;
    public MainPage()
    {
        InitializeComponent();
        rotator = new SfRotator();
        stackLayoout = new StackLayout();
        rotator.NavigationDirection = NavigationDirection.TopToBottom;
        stackLayoout.Children.Add(rotator);
        this.Content = stackLayoout;
    }
}

{% endhighlight %}

{% endtabs %}

## BottomToTop

Rotator items can be navigate from Bottom to Top only.

{% tabs %}

{% highlight xaml %}

<?xml version="1.0" encoding="utf-8" ?>
<ContentPage xmlns="http://xamarin.com/schemas/2014/forms"
             xmlns:x="http://schemas.microsoft.com/winfx/2009/xaml"
             xmlns:d="http://xamarin.com/schemas/2014/forms/design"
             xmlns:mc="http://schemas.openxmlformats.org/markup-compatibility/2006"
             mc:Ignorable="d"
             xmlns:rotator="clr-namespace:Syncfusion.SfRotator.XForms;assembly=Syncfusion.SfRotator.XForms"
             x:Class="RotatorNavigation.MainPage">
    
    <StackLayout>
        <rotator:SfRotator NavigationDirection="BottomToTop" x:Name="rotator"/>
    </StackLayout>

</ContentPage>

{% endhighlight %}

{% highlight C# %}

public partial class MainPage : ContentPage
{
    SfRotator rotator;
    StackLayout stackLayoout;
    public MainPage()
    {
        InitializeComponent();
        rotator = new SfRotator();
        stackLayoout = new StackLayout();
        rotator.NavigationDirection = NavigationDirection.BottomToTop;
        stackLayoout.Children.Add(rotator);
        this.Content = stackLayoout;
    }
}

{% endhighlight %}

{% endtabs %}
