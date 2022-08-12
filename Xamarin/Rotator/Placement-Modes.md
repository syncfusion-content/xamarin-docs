---
layout: post
title: Placement Modes in Xamarin Rotator control | Syncfusion
description: Learn here all about Placement Modes support in Syncfusion Xamarin Rotator (SfRotator) control and more.
platform: xamarin 
control: Rotator 
documentation: ug
---

# Placement Modes in Xamarin Rotator (SfRotator)

By default, the rotator control displays the dots of each rotator item. It can be changed to any of the following types:

* [`Default`](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfRotator.XForms.DotPlacement.html#Syncfusion_SfRotator_XForms_DotPlacement_Default)
* [`None`](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfRotator.XForms.DotPlacement.html#Syncfusion_SfRotator_XForms_DotPlacement_None)
* [`Outside`](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfRotator.XForms.DotPlacement.html#Syncfusion_SfRotator_XForms_DotPlacement_OutSide)
 
## DotsPlacement

The Display Type of Rotator can be modified using the [`DotsPlacement`](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfRotator.XForms.SfRotator.html#Syncfusion_SfRotator_XForms_SfRotator_DotPlacement) Mode. The [`“None”`](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfRotator.XForms.DotPlacement.html#Syncfusion_SfRotator_XForms_DotPlacement_None) type can be used when the dots are not needed for the rotator control.

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
                              DotPlacement="None" >
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
			rotator.DotPlacement = DotPlacement.None;
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

![DotsPlacement](images/DotsPlacement.png)
