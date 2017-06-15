---
layout: post
title: Data Binding in SfListView
description: Describes about data binding and different sources that can be bound to SfListView.
platform: xamarin
control: SfListView
documentation: ug
---

# Data Binding

SfListView lets you bound an external data source using [ItemsSource](https://help.syncfusion.com/cr/cref_files/xamarin/sflistview/Syncfusion.SfListView.XForms~Syncfusion.ListView.XForms.SfListView~ItemsSource.html) property to display the data in view. It supports the data sources such as [List](https://msdn.microsoft.com/en-us/library/6sh2ey19(v=vs.110).aspx), [ObservableCollection](https://msdn.microsoft.com/en-us/library/ms668604(v=vs.110).aspx), and so on as a collection of objects.

To bind the data source for SfListView, set the `ItemsSource` property as shown below such that each listview item in SfListView would bind to an object in the data source.

{% tabs %}
{% highlight xaml %}
<?xml version="1.0" encoding="utf-8" ?>
<ContentPage xmlns="http://xamarin.com/schemas/2014/forms"
             xmlns:x="http://schemas.microsoft.com/winfx/2009/xaml"
             xmlns:syncfusion="clr-namespace:Syncfusion.ListView.XForms;assembly=Syncfusion.SfListView.XForms"
             xmlns:local="clr-namespace:GettingStarted;assembly=GettingStarted"
             x:Class="GettingStarted.MainPage">
             
  <ContentPage.BindingContext>
    <local:BookInfoRepository />
  </ContentPage.BindingContext>

  <syncfusion:SfListView x:Name="listView" 
                         ItemsSource="{Binding BookInfo}" />
</ContentPage>
{% endhighlight %}
{% highlight c# %}
BookInfoRepository viewModel = new BookInfoRepository ();
listView.ItemsSource = viewModel.BookInfo; 
{% endhighlight %}
{% endtabs %}

## Binding the data source as ObservableCollection and List

If the data source implements `ICollectionChanged` interface, then SfListView will automatically refresh the view when an item is added, removed or cleared. When you add, or remove an item in `ObservableCollection`, the SfListView automatically refreshes the view as the `ObservableCollection` implements the [INotifyCollectionChanged](https://msdn.microsoft.com/en-us/library/system.collections.specialized.inotifycollectionchanged(v=vs.110).aspx).

But when you do the same with `List`, SfListView will not refresh the view automatically because it does not respond the collection changed. So, you need to implement the `INotifyPropertyChanged` interface in the data model, then the SfListView responds to the property change in runtime to update the view.

## Binding with IEnumerable

SfListView control supports to bind any collection that implements the [IEnumerable](https://msdn.microsoft.com/en-us/library/system.collections.ienumerable) interface. All the data operations such as sorting, grouping, filtering is supported when you are binding collection derived from `IEnumerable`.

## Defining the LiveDataUpdateMode

SfListView provides support to update the view during data manipulation operations such as add, delete and property changes at runtime using [LiveDataUpdateMode](https://help.syncfusion.com/cr/cref_files/xamarin/datasource/Syncfusion.DataSource.Portable~Syncfusion.DataSource.LiveDataUpdateMode.html) property. The default value is `LiveDataUpdateMode.Default`.

<table>
<tr>
<th>LiveDataUpdateMode</th>
<th>Description</th>
</tr>
<tr>
<td>Default</td>
<td>Updates only the corresponding underlying data when the property is changed</td>
</tr>
<tr>
<td>AllowDataShaping</td>
<td>Updates the corresponding underlying data. Also, it reshapes the data based on sorting, filtering, grouping when the property is changed</td>
</tr>
</table>

{% highlight c# %}
private void UpdateData_Clicked(object sender, EventArgs e)
{
   listView.DataSource.LiveDataUpdateMode = LiveDataUpdateMode.AllowDataShaping;
   ViewModel.Items[0].Title = "ListViewItem_0";
}
{% endhighlight %}

## Defining the source data type

When the data source contains the different data model types which are derived from the same type, you need to set [SourceType](https://help.syncfusion.com/cr/cref_files/xamarin/datasource/Syncfusion.DataSource.Portable~Syncfusion.DataSource.DataSource~SourceType.html) as base type for all different types to carry out the data operations such as sorting and grouping.

{% highlight c# %}
listView.DataSource.SourceType = typeof(Contacts);
{% endhighlight %}