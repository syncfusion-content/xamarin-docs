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

{% endhighlight %}
{% endtabs %}

{% tabs %}

{% highlight c# %}

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