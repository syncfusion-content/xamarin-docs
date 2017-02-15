---
layout: post
title: Layouts in SfListView
description: Describes about the different layouts and its functionalities in SfListView.
platform: xamarin
control: SfListView
documentation: ug
---

# Layouts

SfListView supports two layouts such as Linear Layout and Grid Layout. It's defined by [SfListView.LayoutManager](https://help.syncfusion.com/cr/cref_files/xamarin/sflistview/Syncfusion.SfListView.XForms~Syncfusion.ListView.XForms.SfListView~LayoutManagerProperty.html) property of the SfListView.

## Linear Layout

Linear layout arranges the items in a single column. It's the default layout for the SfListView. Initialize the [LinearLayout](https://help.syncfusion.com/cr/cref_files/xamarin/sflistview/Syncfusion.SfListView.XForms~Syncfusion.ListView.XForms.LinearLayout.html) and assigning it to [SfListView.LayoutManager](https://help.syncfusion.com/cr/cref_files/xamarin/sflistview/Syncfusion.SfListView.XForms~Syncfusion.ListView.XForms.SfListView~LayoutManagerProperty.html) property.

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

The following screenshot shows the output of linear layout.

![](SfListView_images/SfListView-Xamarin_img1.png)

## Grid Layout

Grid layout arranges the items in a predefined number of columns. Initialize the [GridLayout](https://help.syncfusion.com/cr/cref_files/xamarin/sflistview/Syncfusion.SfListView.XForms~Syncfusion.ListView.XForms.GridLayout.html) and assigning it to [SfListView.LayoutManager](https://help.syncfusion.com/cr/cref_files/xamarin/sflistview/Syncfusion.SfListView.XForms~Syncfusion.ListView.XForms.SfListView~LayoutManagerProperty.html) property.GridLayout contains the below properties,

* SpanCount: Gets or sets the items count in a row/column based on orientation. The default value is 2.

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

The following screenshot shows the output of Grid layout. You can download the entire source code of this demo from [here](http://files2.syncfusion.com/Xamarin.Forms/Samples/ListViewGridLayout.zip)

![](SfListView_images/SfListView-GridLayout.png)

### Customize SpanCount based on specfic platform

[SpanCount](https://help.syncfusion.com/cr/cref_files/xamarin/sflistview/Syncfusion.SfListView.XForms~Syncfusion.ListView.XForms.GridLayout~SpanCount.html) property of GridLayout can be customized based on platform specfic to avoid squeezed problems of listview item in tablet devices or desktop for windows. The below code illustrates the customization of SpanCount,

{% highlight c# %}
GridLayout gridLayout = new GridLayout();

if (Device.OS == TargetPlatform.Android || Device.OS == TargetPlatform.iOS)
   gridLayout.SpanCount = Device.Idiom == TargetIdiom.Phone ? 2 : 4;
else if (Device.OS == TargetPlatform.Windows)
   gridLayout.SpanCount = Device.Idiom == TargetIdiom.Desktop || Device.Idiom == TargetIdiom.Tablet ? 4 : 2;

listView.LayoutManager = gridLayout;
{% endhighlight%}

The below screenshot shows the output for windows desktop,
![](SfListView_images/SfListView-GridLayoutUWP.png)

The below screenshot shows the output for Android tablet,
![](SfListView_images/SfListView-GridLayoutAndroid.png)

The below screenshot shows the output for iOS tablet,
![](SfListView_images/SfListView-GridLayoutiOS.png)