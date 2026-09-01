---
layout: post
title: Placement Modes in Xamarin Rotator Control | Syncfusion
description: Explore the placement modes available in the Syncfusion Xamarin Rotator (SfRotator) control for customizing your mobile application interface.
platform: xamarin 
control: Rotator 
documentation: ug
---

# Placement Modes in Xamarin Rotator (SfRotator)

The Xamarin Rotator, `SfRotator`, provides a flexible way to display navigation dots for image items. You can customize the appearance of these dots using the following placement modes:
- **[`Default`](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfRotator.XForms.DotPlacement.html#Syncfusion_SfRotator_XForms_DotPlacement_Default)**: Display dots at their default position.
- **[`None`](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfRotator.XForms.DotPlacement.html#Syncfusion_SfRotator_XForms_DotPlacement_None)**: Hide dots completely, useful when you want a clean, dot-free interface.
- **[`Outside`](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfRotator.XForms.DotPlacement.html#Syncfusion_SfRotator_XForms_DotPlacement_OutSide)**: Place dots outside the image area.
 
## DotsPlacement Property

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
