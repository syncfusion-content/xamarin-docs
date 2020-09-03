---
layout: post
title: Layouts in Xamarin.Forms ListView | Syncfusion
description: Describes about the different layouts such as Linear and GridLayout, its functionalities in SfListView.
platform: xamarin
control: SfListView
documentation: ug
---

# Layouts in Xamarin ListView (SfListView)

The SfListView supports different layouts such as linear layout and grid layout. The [SfListView.LayoutManager](https://help.syncfusion.com/cr/xamarin/Syncfusion.ListView.XForms.SfListView.html#Syncfusion_ListView_XForms_SfListView_LayoutManager) property is used to define the layout.

## Linear Layout

Linear layout arrange items in a single column. Initialize the [LinearLayout](https://help.syncfusion.com/cr/xamarin/Syncfusion.ListView.XForms.LinearLayout.html), and assign it to the [SfListView.LayoutManager](https://help.syncfusion.com/cr/xamarin/Syncfusion.ListView.XForms.SfListView.html#Syncfusion_ListView_XForms_SfListView_LayoutManager) property to load the SfListView in linear layout. It is the default layout.

{% tabs %}
{% highlight xaml %}
<ContentPage xmlns:syncfusion="clr-namespace:Syncfusion.ListView.XForms;assembly=Syncfusion.SfListView.XForms">
  <syncfusion:SfListView x:Name="listView" 
                    ItemsSource="{Binding GalleryInfo}"
                    ItemSize="100">
      <syncfusion:SfListView.LayoutManager>
        <syncfusion:LinearLayout />
      </syncfusion:SfListView.LayoutManager>
  </syncfusion:SfListView>
</ContentPage>
{% endhighlight%}
{% highlight c# %}
listView.LayoutManager = new LinearLayout();
{% endhighlight%}
{% endtabs %}

![Xamarin.Forms listview with linear view](SfListView_images/SfListView-Xamarin_img1.jpg)

## Grid Layout

Grid layout arrange items in a predefined number of columns. Initialize the [GridLayout](https://help.syncfusion.com/cr/xamarin/Syncfusion.ListView.XForms.GridLayout.html), and assign it to the [SfListView.LayoutManager](https://help.syncfusion.com/cr/xamarin/Syncfusion.ListView.XForms.SfListView.html#Syncfusion_ListView_XForms_SfListView_LayoutManager) property to load the SfListView in grid layout. 

The number of columns can be defined by using the [SpanCount](https://help.syncfusion.com/cr/xamarin/Syncfusion.ListView.XForms.GridLayout.html#Syncfusion_ListView_XForms_GridLayout_SpanCount) property of `GridLayout`. Default `SpanCount` is 2.

In horizontal orientation, `SpanCount` defines the number of rows.

{% tabs %}
{% highlight xaml %}
<ContentPage xmlns:syncfusion="clr-namespace:Syncfusion.ListView.XForms;assembly=Syncfusion.SfListView.XForms">
  <syncfusion:SfListView x:Name="listView" 
                    ItemsSource="{Binding GalleryInfo}"
                    ItemSize="100">
      <syncfusion:SfListView.LayoutManager>
        <syncfusion:GridLayout SpanCount="2" />
      </syncfusion:SfListView.LayoutManager>
  </syncfusion:SfListView>
</ContentPage>
{% endhighlight%}
{% highlight c# %}
listView.LayoutManager = new GridLayout() { SpanCount = 2 };
{% endhighlight%}
{% endtabs %}

Download the entire source code from GitHub [here](https://github.com/SyncfusionExamples/GridLayout-with-xamarin.forms-listview).

![Xamarin.Forms listview with grid view](SfListView_images/SfListView-GridLayout.jpg)

## Customize span count based on platform

The [SpanCount](https://help.syncfusion.com/cr/xamarin/Syncfusion.ListView.XForms.GridLayout.html#Syncfusion_ListView_XForms_GridLayout_SpanCount) property of the [GridLayout](https://help.syncfusion.com/cr/xamarin/Syncfusion.ListView.XForms.GridLayout.html) can be customized based on the specified platform to avoid squeezed problem of listview item in phone and tablet devices or windows desktop.

{% tabs %}
{% highlight xaml %}
<ContentPage xmlns:syncfusion="clr-namespace:Syncfusion.ListView.XForms;assembly=Syncfusion.SfListView.XForms">
  <syncfusion:SfListView.LayoutManager>
    <syncfusion:GridLayout>
        <syncfusion:GridLayout.SpanCount>
        <OnPlatform x:TypeArguments="x:Int32">
          <OnPlatform.WinPhone>
            <OnIdiom x:TypeArguments="x:Int32" Phone="2" Tablet="4" Desktop="4"/>
          </OnPlatform.WinPhone>
          <OnPlatform.Android>
            <OnIdiom x:TypeArguments="x:Int32" Phone="2" Tablet="4" />
          </OnPlatform.Android>
          <OnPlatform.iOS>
            <OnIdiom x:TypeArguments="x:Int32" Phone="2" Tablet="4" />
          </OnPlatform.iOS>
        </OnPlatform>
      </syncfusion:GridLayout.SpanCount>
    </syncfusion:GridLayout>
  </syncfusion:SfListView.LayoutManager>
  </syncfusion:SfListView>
</ContentPage>
{% endhighlight%}
{% highlight c# %}
GridLayout gridLayout = new GridLayout();

if (Device.OS == TargetPlatform.Android || Device.OS == TargetPlatform.iOS)
   gridLayout.SpanCount = Device.Idiom == TargetIdiom.Phone ? 2 : 4;
else if (Device.OS == TargetPlatform.Windows)
   gridLayout.SpanCount = Device.Idiom == TargetIdiom.Desktop || Device.Idiom == TargetIdiom.Tablet ? 4 : 2;

listView.LayoutManager = gridLayout;
{% endhighlight%}
{% endtabs %}

![Xamarin.Forms listview with grid view span](SfListView_images/SfListView-GridLayoutTablet.jpg)

## Change span count based on screen size

In the SfListView, the [GridLayout](https://help.syncfusion.com/cr/xamarin/Syncfusion.ListView.XForms.GridLayout.html) allows changing the span count based on the view size of application with orientation in either portrait or landscape mode.

{% tabs %}
{% highlight c# %}
public partial class GridLayoutPage : ContentPage
{
  protected override void OnSizeAllocated(double width, double height) 
  { 
    base.OnSizeAllocated(width, height); 
 
    if (width > 0 && pageWidth != width) 
    {       
        var size = Application.Current.MainPage.Width / listView.ItemSize; 
        gridLayout.SpanCount = (int)size; 
        listView.LayoutManager = gridLayout; 
     } 
  }
}
{% endhighlight %}
{% endtabs %}

You can download the entire sample code [here](http://www.syncfusion.com/downloads/support/directtrac/general/ze/SpanCount-1456879973).

## See also

[How to display each row with different columns in Xamarin.Forms ListView (SfListView)](https://www.syncfusion.com/kb/11236)                                                                                                                                                                                        
