---
layout: post
title: Data Binding | SfDataGrid | Xamarin | Syncfusion
description: Data Binding and different sources that can be bound to a SfDataGrid.
platform: xamarin
control: SfDataGrid
documentation: UG
---

# Data Binding

The SfDataGrid is bound to an external data source to display the data. It supports the data sources such as `List`, `ObservableCollection`, and so on. [SfDataGrid.ItemsSource](http://help.syncfusion.com/cr/cref_files/xamarin/sfdatagrid/Syncfusion.SfDataGrid.XForms~Syncfusion.SfDataGrid.XForms.SfDataGrid~ItemsSource.html) property helps to bind the SfDataGrid with the collection of objects.

In order to bind the data source of the SfDataGrid, set the `SfDataGrid.ItemsSource` property as shown below such that each row in the SfDataGrid would bind to an object in the data source and each column would bind to a property in the data model object.
{% tabs %}
{% highlight xaml %}
<?xml version="1.0" encoding="utf-8" ?>
<ContentPage xmlns="http://xamarin.com/schemas/2014/forms"
             xmlns:x="http://schemas.microsoft.com/winfx/2009/xaml"
             xmlns:local="clr-namespace:DataGridDemo;assembly=DataGridDemo"
             xmlns:syncfusion="clr-namespace:Syncfusion.SfDataGrid.XForms;assembly=Syncfusion.SfDataGrid.XForms" 
             x:Class="DataGridDemo.Sample">

    <ContentPage.BindingContext>
        <local:OrderInfoRepository x:Name="viewModel" />
    </ContentPage.BindingContext>

    <ContentPage.Content>
        <syncfusion:SfDataGrid x:Name="dataGrid"
                               ItemsSource="{Binding OrderInfoCollection}">
        </syncfusion:SfDataGrid>
    </ContentPage.Content>
</ContentPage>
{% endhighlight %} 
{% highlight c# %}
OrderInfoRepository viewModel = new OrderInfoRepository ();
dataGrid.ItemsSource = viewModel.OrderInfoCollection; 
{% endhighlight %}
{% endtabs %}

If the data source implements `ICollectionChanged` interface, then SfDataGrid will automatically refresh the view when an item is added, removed or while list cleared. When you add or remove an item in `ObservableCollection`, the SfDataGrid automatically refreshes the view as the `ObservableCollection` implements the `INotifyCollectionChanged`. But when you do the same in `List`, SfDataGrid will not refresh the view automatically.

If the data model implements the `INotifyPropertyChanged` interface, then the SfDataGrid responds to the property change in runtime to update the view.
