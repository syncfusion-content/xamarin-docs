---
layout: post
title: Loading URL Images in Syncfusion Rotator control for Xamarin.Forms.
description: Loading URL Images in Rotator control in Xamarin.Forms
platform: xamarin 
control: Rotator 
documentation: ug
---

# Loading URL Images

This section describes how to load the online images in SfRotator Control.

{% tabs %}
{% highlight xaml %}
<?xml version="1.0" encoding="utf-8" ?>
<ContentPage xmlns="http://xamarin.com/schemas/2014/forms"
             xmlns:x="http://schemas.microsoft.com/winfx/2009/xaml"
             xmlns:local="clr-namespace:Rotator"
             xmlns:rotator="clr-namespace:Syncfusion.SfRotator.XForms;assembly=Syncfusion.SfRotator.XForms"
             x:Class="Rotator.MainPage">
    <ContentPage.BindingContext>
        <local:RotatorViewModel/>
    </ContentPage.BindingContext>
    <ContentPage.Content>
        <StackLayout>
            <rotator:SfRotator x:Name="rotator" 
                        ItemsSource="{Binding ImageCollection}" 
                        NavigationDirection="Horizontal">
                <rotator:SfRotator.ItemTemplate>
                    <DataTemplate>
                        <StackLayout >
                            <Image Source="{Binding Image}" HeightRequest="250"/>
                        </StackLayout>
                    </DataTemplate>
                </rotator:SfRotator.ItemTemplate>
            </rotator:SfRotator>
        </StackLayout>
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
            InitializeComponent();
            SfRotator sfRotator = new SfRotator();
            sfRotator.ItemsSource = GetDataSource();

            var imageTemplate = new DataTemplate(() =>
            {
                Image image = new Image();
                image.SetBinding(Image.SourceProperty, "Image");
                return image;
            });

            sfRotator.ItemTemplate = imageTemplate;
            this.Content = sfRotator;
        }
        List<CustomData> GetDataSource()
        {
            List<CustomData> list = new List<CustomData>();
            list.Add(new CustomData("https://cdn.syncfusion.com/content/images/Images/Camtasia_Succinctly.png?v=22022017060923"));
            list.Add(new CustomData("https://cdn.syncfusion.com/content/images/Images/SQL_Queries_Succinctly.png?v=04022017014551"));
            list.Add(new CustomData("https://upload.wikimedia.org/wikipedia/commons/0/0c/Cow_female_black_white.jpg"));
            list.Add(new CustomData("https://cdn.syncfusion.com/content/images/Images/Keystonejs_Succinctly.png?v=22022017060923"));
            list.Add(new CustomData("https://cdn.syncfusion.com/content/images/Images/sql_server_for_c_sharp_developers_succinctly_cover_img.png?v=22022017060923"));
            list.Add(new CustomData("https://cdn.syncfusion.com/content/images/Images/sql_server_for_c_sharp_developers_succinctly_cover_img.png?v=22022017060923"));
            return list;
        }
    }
}


ViewModel Class:

public class RotatorViewModel
    {
        public RotatorViewModel()
        {
            ImageCollection= = new ObservableCollection<RotatorModel>();
            ImageCollection.Add(new RotatorModel("https://cdn.syncfusion.com/content/images/Images/Camtasia_Succinctly.png?v=22022017060923"));
            ImageCollection.Add(new RotatorModel("https://cdn.syncfusion.com/content/images/Images/SQL_Queries_Succinctly.png?v=04022017014551"));
            ImageCollection.Add(new RotatorModel("https://upload.wikimedia.org/wikipedia/commons/0/0c/Cow_female_black_white.jpg"));
            ImageCollection.Add(new RotatorModel("https://cdn.syncfusion.com/content/images/Images/Keystonejs_Succinctly.png?v=22022017060923"));
            ImageCollection.Add(new RotatorModel("https://cdn.syncfusion.com/content/images/Images/sql_server_for_c_sharp_developers_succinctly_cover_img.png?v=22022017060923"));
            ImageCollection.Add(new RotatorModel("https://cdn.syncfusion.com/content/images/Images/sql_server_for_c_sharp_developers_succinctly_cover_img.png?v=22022017060923"));
        }

        private ObservableCollection<RotatorModel> imageCollection;
        public ObservableCollection<RotatorModel> ImageCollection
        {
            get { return imageCollection; }
            set { imageCollection = value; }
        }
    }

Model Class:

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

{% endhighlight %}
{% endtabs %}

// Custom Data 

using System;
using Xamarin.Forms;

namespace Rotator
{
    public class CustomData : ContentPage
    {
        public CustomData(string image)
        {
            Image = image;
        }
        public string Image
        {
            get;
            set;
        }
        public CustomData()
        {

        }
    }
}

{% endhighlight %}

{% endtabs %}

![Loading URL Image](images/URLImage.png)