---
layout: post
title: Events in Xamarin Rotator Control | Syncfusion
description: Explore the various events supported by the Syncfusion Xamarin Rotator (SfRotator) control, their features, and implementations.
platform: xamarin 
control: Rotator 
documentation: ug
---

# Events in Xamarin Rotator (SfRotator)

The Rotator control in Xamarin enables users to interact with items through events such as `SelectionChanged` and `ItemTapped`. These events are crucial for handling user interactions and updating UI elements in real-time.

## Selection Changed

The `SelectionChanged` event is triggered when the selection of the rotator changes, either by swiping through the items or by dynamically updating the [`SelectedIndex`](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfRotator.XForms.SfRotator.html#Syncfusion_SfRotator_XForms_SfRotator_SelectedIndex) property of the [`SfRotator`](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfRotator.XForms.SfRotator.html).

## Item Tapped

The [`ItemTapped`](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfRotator.XForms.SfRotator.html#Syncfusion_SfRotator_XForms_SfRotator_ItemTapped) event is fired whenever an item in the rotator is tapped. This can be used to trigger actions such as navigation or selection operations.

{% tabs %}

{% highlight xaml %}

<?xml version="1.0" encoding="utf-8" ?>
<ContentPage xmlns="http://xamarin.com/schemas/2014/forms"
             xmlns:x="http://schemas.microsoft.com/winfx/2009/xaml"
             xmlns:local="clr-namespace:Rotator"
             xmlns:rotator="clr-namespace:Syncfusion.SfRotator.XForms;assembly=Syncfusion.SfRotator.XForms"
             x:Class="Rotator.MainPage">
    <rotator:SfRotator.BindingContext>
        <local:RotatorViewModel/>
    </rotator:SfRotator.BindingContext>
    <ContentPage.Content>
        <Grid HorizontalOptions="FillAndExpand" VerticalOptions="Fill">
            <rotator:SfRotator x:Name="rotator" 
                               ItemTapped="Rotator_ItemTapped"
                               SelectedIndexChanged="Rotator_SelectedIndexChanged"
                        ItemsSource="{Binding ImageCollection}" 
                        VerticalOptions="Start">
                <rotator:SfRotator.ItemTemplate>
                    <DataTemplate>
                        <StackLayout>
                            <Image Source="{Binding Image}" />
                        </StackLayout>
                    </DataTemplate>
                </rotator:SfRotator.ItemTemplate>
            </rotator:SfRotator>
        </Grid>
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

namespace Rotator
{
    public partial class MainPage : ContentPage
    {

       RotatorViewModel viewmodel = new RotatorViewModel();
        public MainPage()
        {
            InitializeComponent();
            StackLayout layout = new StackLayout();
            SfRotator rotator = new SfRotator();
            rotator.ItemTapped += Rotator_ItemTapped;
            rotator.SelectedIndexChanged += Rotator_SelectedIndexChanged;
            rotator.ItemsSource = viewmodel.ImageCollection;
            var itemTemplate = new DataTemplate(() =>
            {
                var grid = new Grid();
                var nameLabel = new Image();
                nameLabel.SetBinding(Image.SourceProperty, "Image");
                grid.Children.Add(nameLabel);
                return grid;
            });
            rotator.ItemTemplate = itemTemplate;
            layout.Children.Add(rotator);
            this.Content = layout;
            this.BindingContext = viewmodel;

        }

        private void Rotator_ItemTapped(object sender, EventArgs e)
        {
            DisplayAlert("Notification", "Rotator Item is Tapped", "Ok");
        }

        private void Rotator_SelectedIndexChanged(object sender, SelectedIndexChangedEventArgs e)
        {
            DisplayAlert("Notification", "Selected Index is Changed", "Ok");
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

RotatorViewModel Class:

using System;
using System.Collections.Generic;
using System.Collections.ObjectModel;
using System.Text;

namespace Rotator
{
    public class RotatorViewModel
    {
        public RotatorViewModel()
        {
            ImageCollection.Add(new RotatorModel("movie1.png"));
            ImageCollection.Add(new RotatorModel("image1.png"));
            ImageCollection.Add(new RotatorModel("movie3.png"));
            ImageCollection.Add(new RotatorModel("movie4.png"));
            ImageCollection.Add(new RotatorModel("movie5.png"));
        }

        private ObservableCollection<RotatorModel> imageCollection = new ObservableCollection<RotatorModel>();
        public ObservableCollection<RotatorModel> ImageCollection
        {
            get { return imageCollection; }
            set { imageCollection = value; }
        }
    }
}

{% endhighlight %}

{% endtabs %}

The following screenshot illustrates the output of the above code.

![Rotator_SelectedIndexChanged](images/SelectedIndexChanged.png)
![Rotator_ItemTapped](images/ItemTapped.png)




   




