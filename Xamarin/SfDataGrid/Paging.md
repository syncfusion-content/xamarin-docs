---
layout: post
title: Paging | SfDataGrid | Xamarin | Syncfusion
description: How to enable paging and use its properties
platform: xamarin
control: SfDataGrid
documentation: ug
---

# Paging – Xamarin.Forms

The SfDataGrid provides interactive support to manipulate data using the [SfDataPager](http://help.syncfusion.com/cr/cref_files/xamarin/sfdatagrid/Syncfusion.SfDataGrid.XForms~Syncfusion.SfDataGrid.XForms.DataPager_namespace.html# “”) control. It also provides built-in options to page data on demand when dealing with large volumes of data. SfDataGrid lets you to place the `SfDataPager` above or below it as per your requirement which lets you to easily manage the data paging.

To use the paging functionality in SfDataGrid add the below namespace to your project.
[Syncfusion.SfDataGrid.XForms.DataPager](http://help.syncfusion.com/cr/xamarin/sfdatagrid# “”)

There are two different modes in Paging as stated below.

* NormalPaging: NormalPaging loads the entire data collection to the `SfDataPager`.
* OnDemandPaging: OnDemandPaging loads the data to current page dynamically in `SfDataPager`.

## Normal Paging

SfDataGrid performs paging of data using the `SfDataPager`. Follow the below procedure to enable paging in SfDataGrid.

* Create a new SfDataPager instance and bind the data collection to the [SfDataPager.Source](http://help.syncfusion.com/cr/cref_files/xamarin/sfdatagrid/Syncfusion.SfDataGrid.XForms~Syncfusion.SfDataGrid.XForms.DataPager.SfDataPager~Source.html# “”) property based on which [SfDataPager.PagedSource](http://help.syncfusion.com/cr/cref_files/xamarin/sfdatagrid/Syncfusion.SfDataGrid.XForms~Syncfusion.SfDataGrid.XForms.DataPager.SfDataPager~PagedSource.html# “”) is created internally. 
* Bind the `PagedSource` property to the [ItemsSource](http://help.syncfusion.com/cr/cref_files/xamarin/sfdatagrid/Syncfusion.SfDataGrid.XForms~Syncfusion.SfDataGrid.XForms.SfDataGrid~ItemsSource.html# “”) of the SfDataGrid. 
* Set the number of rows to be displayed in a page by setting the [SfDataPager.PageSize](http://help.syncfusion.com/cr/cref_files/xamarin/sfdatagrid/Syncfusion.SfDataGrid.XForms~Syncfusion.SfDataGrid.XForms.DataPager.SfDataPager~PageSize.html# “”) property.
* Set the number of buttons that need to be displayed in view by setting the [SfDataPager.NumericButtonCount](http://help.syncfusion.com/cr/cref_files/xamarin/sfdatagrid/Syncfusion.SfDataGrid.XForms~Syncfusion.SfDataGrid.XForms.DataPager.SfDataPager~NumericButtonCount.html# “”) property.

N>The `SfDataPager.PageSize` property should not be assigned with a value of 0.

The following code example illustrates using `SfDataPager` with the SfDataGrid control.
{% tabs %}
{% highlight xaml %}

<local:SamplePage x:Class="SampleBrowser.Paging"
                  xmlns="http://xamarin.com/schemas/2014/forms"
                  xmlns:x="http://schemas.microsoft.com/winfx/2009/xaml"
                  xmlns:local="clr-namespace:SampleBrowser;assembly=SampleBrowser"
                  xmlns:sfgrid="clr-namespace:Syncfusion.SfDataGrid.XForms;assembly=Syncfusion.SfDataGrid.XForms"
                  xmlns:sfpager="clr-namespace:Syncfusion.SfDataGrid.XForms.DataPager;
                                 assembly=Syncfusion.SfDataGrid.XForms">

  <local:SamplePage.BindingContext>
      <local:DataPagerViewModel x:Name="viewModel" />
  </local:SamplePage.BindingContext>
  
  <local:SamplePage.ContentView>
    <Grid> 
      <Grid.RowDefinitions>
        <RowDefinition Height="Auto" />
        <RowDefinition Height="*" />
      </Grid.RowDefinitions>

      <sfpager:SfDataPager x:Name ="dataPager"
                           Grid.Row="0"           
                           PageSize="15" 
                           HeightRequest ="50"
                           NumericButtonCount="20">
           
        <sfpager:SfDataPager.HeightRequest>
          <OnPlatform x:TypeArguments="x:Double"
                      iOS="50"
                      Android="50"
                      WinPhone="70"/>
        </sfpager:SfDataPager.HeightRequest>
      </sfpager:SfDataPager>
       
      <sfgrid:SfDataGrid x:Name="dataGrid"
                         Grid.Row="1"
                         AutoGenerateColumns="true"
                         ColumnSizer="Star"
                         SelectionMode="Single">             
      </sfgrid:SfDataGrid>
    </Grid> 
  </local:SamplePage.ContentView>
</local:SamplePage>

{% endhighlight %}
{% highlight c# %}

public partial class MainPage : ContentPage
{
    SfDataGrid sfGrid = new SfDataGrid();
    SfDataPager sfPager = new SfDataPager();
    ViewModel viewModel = new ViewModel();
    public MainPage()
    {
        InitializeComponent();
        sfPager.PageSize = 15;  //Setting the number of rows in a page        
        sfPager.Source = viewModel.Info;  //Setting data source to SfDataPager
        sfGrid.ItemsSource = sfPager.PagedSource;  //Setting ItemsSource to SfDataGrid
        sfGrid.ColumnSizer = ColumnSizer.Star;

        Grid myGrid = new Grid();
        myGrid.HorizontalOptions = LayoutOptions.FillAndExpand;

        myGrid.RowDefinitions = new RowDefinitionCollection
        {
          new RowDefinition { Height = 50 },
          new RowDefinition {},    
        };
        myGrid.Children.Add(sfPager, 0, 0);
        myGrid.Children.Add(sfGrid, 0, 1);
        this.Content = myGrid;
    }
}

{% endhighlight %}
{% endtabs %}

The following screenshot shows the final outcome upon execution of the above code

![](SfDataGrid_images/Paging_img1.jpeg)

## On Demand Paging	

In normal Paging, data collection is entirely loaded initially to the `SfDataPager`. However, SfDataGrid also allows you to load the data for the current page dynamically by setting the set [SfDataPager.UseOnDemandPaging](http://help.syncfusion.com/cr/cref_files/xamarin/sfdatagrid/Syncfusion.SfDataGrid.XForms~Syncfusion.SfDataGrid.XForms.DataPager.SfDataPager~UseOnDemandPaging.html# “”) to `true`.

To load current page item dynamically you must hook the [OnDemandLoading](http://help.syncfusion.com/cr/cref_files/xamarin/sfdatagrid/Syncfusion.SfDataGrid.XForms~Syncfusion.SfDataGrid.XForms.DataPager.SfDataPager~OnDemandLoading_EV.html# “”) event. In the `OnDemandLoading` event, use the[LoadDynamicItems](http://help.syncfusion.com/cr/cref_files/xamarin/sfdatagrid/Syncfusion.SfDataGrid.XForms~Syncfusion.SfDataGrid.XForms.DataPager.SfDataPager~LoadDynamicItems.html# “”) method to load the data for the corresponding page in `SfDataPager`.

The `OnDemandLoading` event is triggered when the pager moves to the corresponding page. The `OnDemandLoading` event contains the following event arguments:

* [StartIndex](http://help.syncfusion.com/cr/cref_files/xamarin/sfdatagrid/Syncfusion.SfDataGrid.XForms~Syncfusion.SfDataGrid.XForms.DataPager.OnDemandLoadingEventArgs~StartIndex.html# “”): Corresponding page start index.
* [PageSize](http://help.syncfusion.com/cr/cref_files/xamarin/sfdatagrid/Syncfusion.SfDataGrid.XForms~Syncfusion.SfDataGrid.XForms.DataPager.OnDemandLoadingEventArgs~PageSize.html# “”): Number of items to be loaded for that page.

The following code example illustrates how to load data for the DataPager control dynamically.

{% highlight c# %}
private void OnDemandPageLoading(object sender, OnDemandLoadingEventArgs args)
{
   sfDataPager.LoadDynamicItems(args.StartIndex, source.Skip(args.StartIndex).Take(args.PageSize));
}
{% endhighlight %}


N> In On Demand paging, you cannot assign a value for the Source property in SfDataPager.

When you use `OnDemandPaging`, `SfDataPager.PagedSource` loads only the current page data. Upon navigation to another page, `OnDemandLoading` event is fired which loads another set of data but maintains the previous page data also. When you navigate to previous page again, OnDemandLoading event is not fired and the required data is loaded which was maintained in cache. However for further performance enhancement if you don’t want to maintain the previous page data, you can call [Syncfusion.Data.PagedCollectionView.ResetCache()](http://help.syncfusion.com/cr/cref_files/xamarin/data/Syncfusion.Data.Portable~Syncfusion.Data.PagedCollectionView~ResetCache.html# “”) in `OnDemandLoading` event. ResetCache method call resets the cache except current page.

The following code example illustrates how to use ResetCache method:

{% highlight c# %}
private void OnDemandPageLoading(object sender, OnDemandLoadingEventArgs args)
{
  sfDataPager.LoadDynamicItems(args.StartIndex, source.Skip(args.StartIndex).Take(args.PageSize));
  (sfDataPager.PagedSource as PagedCollectionView).ResetCache();
}
{% endhighlight %}

