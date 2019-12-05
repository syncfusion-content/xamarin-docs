---
layout: post
title: Header Visibility in Syncfusion Rotator control for Xamarin.Forms 
description: Learn how to set the header visiblity in Rotator control for Xamarin.Forms
platform: xamarin 
control: Rotator
documentation: ug
---

# Header Visibility

The `IsTextVisible` property can be used to enable the text area visibility in bottom area of SfRotator for providing additional information of items. IsTextVisible property is used to change the visibility of the Text panel that is displayed when SfRotatorItem collection is set and will have no effect when setting Item template.

N> By default, the property value is false.

{% tabs %}

{% highlight xaml %}

<ContentPage xmlns="http://xamarin.com/schemas/2014/forms"
             xmlns:x="http://schemas.microsoft.com/winfx/2009/xaml"
             xmlns:local="clr-namespace:Rotator"
             xmlns:syncfusion="clr-namespace:Syncfusion.SfRotator.XForms;assembly=Syncfusion.SfRotator.XForms"
             x:Class="Rotator.Rotator">
    <ContentPage.Content>
        <syncfusion:SfRotator x:Name="rotator" 
                              BackgroundColor="#ececec"
                              IsTextVisible="true">
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
        SfRotator rotator = new SfRotator();
        StackLayout stackLayout = new StackLayout();
        public Rotator()
        {
            InitializeComponent();
            stackLayout.HeightRequest = 300;
            List<SfRotatorItem> collectionOfItems = new List<SfRotatorItem>();
            collectionOfItems.Add(new SfRotatorItem() { Image = "movie1.png", ItemText = "Agile Software" });
            collectionOfItems.Add(new SfRotatorItem() { Image = "movie2.png", ItemText = "Delphi Succinctly" });
            collectionOfItems.Add(new SfRotatorItem() { Image = "movie3.png", ItemText = "NancyFX Succinctly" });
            collectionOfItems.Add(new SfRotatorItem() { Image = "movie4.png", ItemText = "Roslyn Succinctly" });
            collectionOfItems.Add(new SfRotatorItem() { Image = "movie5.png", ItemText = "Spark Succinctly" });
            rotator.DataSource = collectionOfItems;
            rotator.IsTextVisible = true;
            rotator.DotPlacement = DotPlacement.OutSide;
            stackLayout.Children.Add(rotator);
            this.Content = stackLayout;
            }
        }
    }

{% endhighlight %}

{% endtabs %}

![IsTextVisible](images/IsTextVisible.png)