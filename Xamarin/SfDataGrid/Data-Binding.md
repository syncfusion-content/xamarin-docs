---
layout: post
title: Data Binding | SfDataGrid | Xamarin | Syncfusion
description: Data Binding
platform: xamarin
control: SfDataGrid
documentation: UG
---

# Data Binding

The **SfDataGrid** is bound to an external data source to display the data. It supports the data sources such as List, Observable Collection, and so on. **SfDataGrid.ItemsSource** property helps to bind the **SfDataGrid** with the collection of objects.

In order to bind the data source of the **SfDataGrid**, set the **SfDataGrid.ItemsSource** property as shown below such that each row in the **SfDataGrid** would bind to an object in the data source and each column would bind to a property in the data model object.

{% highlight c# %}
OrderInfoRepository viewModel = new OrderInfoRepository ();
dataGrid.ItemsSource = viewModel.OrderInfoCollection; 
{% endhighlight %}

If the data source implements ICollectionChanged interface, then **SfDataGrid** will automatically refresh the view when an item is added, removed or while list cleared. When you add or remove an item in ObservableCollection, the **SfDataGrid** automatically refreshes the view as ObservableCollection implements INotifyCollectionChanged. But when you do the same in List, **SfDataGrid** will not refresh the view automatically.

If the data model implements the INotifyPropertyChanged interface, then the **SfDataGrid** responds to the property change in runtime to update the view.
