---
layout: post
title: Layouts in SfListView
description: Describes about the different layouts and its functionalities in SfListView.
platform: xamarin
control: SfListView
documentation: ug
---

# Layouts

The SfListView support different layouts such as linear layout and grid layout. The [SfListView.LayoutManager](https://help.syncfusion.com/cr/cref_files/xamarin/sflistview/Syncfusion.SfListView.XForms~Syncfusion.ListView.XForms.SfListView~LayoutManager.html) property is used to define the layout.

## Linear Layout

Linear layout arrange items in a single column. Initialize [LinearLayout](https://help.syncfusion.com/cr/cref_files/xamarin/sflistview/Syncfusion.SfListView.XForms~Syncfusion.ListView.XForms.LinearLayout.html), and assign it to the [SfListView.LayoutManager](https://help.syncfusion.com/cr/cref_files/xamarin/sflistview/Syncfusion.SfListView.XForms~Syncfusion.ListView.XForms.SfListView~LayoutManager.html) property to load the SfListView in linear layout. It is the default layout.

{% tabs %}
{% highlight xaml %}
<syncfusion:SfListView x:Name="listView" 
                   ItemsSource="{Binding GalleryInfo}"
                   ItemSize="100">
    <syncfusion:SfListView.LayoutManager>
      <syncfusion:LinearLayout />
    </syncfusion:SfListView.LayoutManager>
</syncfusion:SfListView>
{% endhighlight%}
{% highlight c# %}
listView.LayoutManager = new LinearLayout();
{% endhighlight%}
{% endtabs %}

The following screenshot shows the output of linear layout:

![](SfListView_images/SfListView-Xamarin_img1.png)

## Grid Layout

Grid layout arrange items in a predefined number of columns. Initialize [GridLayout](https://help.syncfusion.com/cr/cref_files/xamarin/sflistview/Syncfusion.SfListView.XForms~Syncfusion.ListView.XForms.GridLayout.html), and assign it to the [SfListView.LayoutManager](https://help.syncfusion.com/cr/cref_files/xamarin/sflistview/Syncfusion.SfListView.XForms~Syncfusion.ListView.XForms.SfListView~LayoutManager.html) property to load the SfListView in grid layout. 

The number of columns can be defined by using the [SpanCount](https://help.syncfusion.com/cr/cref_files/xamarin/sflistview/Syncfusion.SfListView.XForms~Syncfusion.ListView.XForms.GridLayout~SpanCount.html) property of `GridLayout`. Default `SpanCount` is 2.

In horizontal orientation, `SpanCount` defines the number of rows.

{% tabs %}
{% highlight xaml %}
<syncfusion:SfListView x:Name="listView" 
                   ItemsSource="{Binding GalleryInfo}"
                   ItemSize="100">
    <syncfusion:SfListView.LayoutManager>
      <syncfusion:GridLayout SpanCount="2" />
    </syncfusion:SfListView.LayoutManager>
</syncfusion:SfListView>
{% endhighlight%}
{% highlight c# %}
listView.LayoutManager = new GridLayout() { SpanCount = 2 };
{% endhighlight%}
{% endtabs %}

The following screenshot shows the output of Grid layout. You can download the entire source code of this demo from [here](http://www.syncfusion.com/downloads/support/directtrac/general/ze/2.ListViewGridLayout2009216455)

![](SfListView_images/SfListView-GridLayout.png)

### Customize SpanCount Based on Devices

The [SpanCount](https://help.syncfusion.com/cr/cref_files/xamarin/sflistview/Syncfusion.SfListView.XForms~Syncfusion.ListView.XForms.GridLayout~SpanCount.html) property of [GridLayout](https://help.syncfusion.com/cr/cref_files/xamarin/sflistview/Syncfusion.SfListView.XForms~Syncfusion.ListView.XForms.GridLayout.html) can be customized based on platform specific to avoid squeezed problem of listview item in tablet devices or windows desktop. 

To customize the `SpanCount` specific to platform and devices, follow the code example:

{% tabs %}
{% highlight xaml %}
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

The following screenshot shows the output for tablet devices:

![](SfListView_images/SfListView-GridLayoutTablet.png)

## How To

### Change SpanCount Based on Screen Size

In SfListView, [GridLayout](https://help.syncfusion.com/cr/cref_files/xamarin/sflistview/Syncfusion.SfListView.XForms~Syncfusion.ListView.XForms.GridLayout.html) arranges the item in a row based on the [SpanCount](https://help.syncfusion.com/cr/cref_files/xamarin/sflistview/Syncfusion.SfListView.XForms~Syncfusion.ListView.XForms.GridLayout~SpanCount.html) property. The `SpanCount` can be adjust based on the view size of application with orientation in either portrait or landscape mode.
For example, the screen width is 300 and `ItemSize` is 150 in portrait mode, then SpanCount value would be 2.

To calculated the `SpanCount` by using screen width and `ItemSize` property to layout the items, follow the code example.

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

You can download the entire sample code from [here](http://www.syncfusion.com/downloads/support/directtrac/general/ze/1.ListViewGridLayout2126595573)