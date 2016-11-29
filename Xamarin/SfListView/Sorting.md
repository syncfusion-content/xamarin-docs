---
layout: post
title: Sorting in SfListView
description: Describes about the sorting behavior in SfListView.
platform: xamarin
control: SfListView
documentation: ug
---

# Sorting 

SfListView allows you to sort the data either in ascending or descending order by using [DataSource.SortDescriptors](https://help.syncfusion.com/cr/cref_files/xamarin/datasource/Syncfusion.DataSource.Portable~Syncfusion.DataSource.DataSource~SortDescriptors.html) property. It also provides support to sort the data based on the custom logic.


## Programmatic Sorting

SfListView allows you to apply sorting on its data by using [DataSource.SortDescriptors](https://help.syncfusion.com/cr/cref_files/xamarin/datasource/Syncfusion.DataSource.Portable~Syncfusion.DataSource.DataSource~SortDescriptors.html) property. You can create a [SortDescriptor](https://help.syncfusion.com/cr/cref_files/xamarin/datasource/Syncfusion.DataSource.Portable~Syncfusion.DataSource.SortDescriptor.html) for the property to be sorted and add it into the `DataSource.SortDescriptors` collection.

N> You can refresh the view by calling [SfListView.RefreshView()](https://help.syncfusion.com/cr/cref_files/xamarin/sflistview/Syncfusion.SfListView.XForms~Syncfusion.ListView.XForms.SfListView~RefreshView.html) method.

SortDescriptor object holds following three properties:

* PropertyName: Name of the sorted property.
* Direction: An object of type [ListSortDirection](https://help.syncfusion.com/cr/cref_files/xamarin/datasource/Syncfusion.DataSource.Portable~Syncfusion.DataSource.ListSortDirection.html) defines the sorting direction.
* Comparer: Comparer to be applied when sorting take place.
 
{% tabs %}
{% highlight xaml %}
xmlns:sync="clr-namespace:Syncfusion.ListView.XForms;assembly=Syncfusion.SfListView.XForms"
xmlns:dataSource="clr-namespace:Syncfusion.DataSource;assembly=Syncfusion.DataSource.Portable"
...
<sync:SfListView.DataSource>
  <dataSource:DataSource>
    <dataSource:DataSource.SortDescriptors>
      <dataSource:SortDescriptor PropertyName="ContactName" Direction="Ascending"/>
    </dataSource:DataSource.SortDescriptors>
  </dataSource:DataSource>
</sync:SfListView.DataSource>
{% endhighlight %}
{% highlight c# %}
listView.DataSource.SortDescriptors.Add(new SortDescriptor()
{
  PropertyName = "ContactName",
  Direction = ListSortDirection.Ascending,
}); 
listView.RefreshView();
{% endhighlight %}
{% endtabs %}

## Custom Sorting

SfListView allows you to sort the items based on the custom logic. The custom sorting can be applied to either [SfListView.DataSource.SortComparer](https://help.syncfusion.com/cr/cref_files/xamarin/datasource/Syncfusion.DataSource.Portable~Syncfusion.DataSource.DataSource~SortComparer.html) property or [SortDescriptor.Comparer](https://help.syncfusion.com/cr/cref_files/xamarin/datasource/Syncfusion.DataSource.Portable~Syncfusion.DataSource.SortDescriptor~Comparer.html) which is added into the [DataSource.SortDescriptors](https://help.syncfusion.com/cr/cref_files/xamarin/datasource/Syncfusion.DataSource.Portable~Syncfusion.DataSource.DataSource~SortDescriptors.html) collection.

The following code example illustrates how to perform custom sorting for underlying data based on the string length of the `ContactName`.

{% tabs %}
{% highlight xaml %}
xmlns:local="clr-namespace:Sorting;assembly=Sorting"
xmlns:listView="clr-namespace:Syncfusion.ListView.XForms;assembly=Syncfusion.SfListView.XForms"
xmlns:sfdatasource="clr-namespace:Syncfusion.DataSource;assembly=Syncfusion.DataSource.Portable"
...
<ContentPage.Resources>
  <ResourceDictionary>
    <local:CustomComparer x:Key="Comparer" />
  </ResourceDictionary>
</ContentPage.Resources>
...
<listView:SfListView.DataSource>
  <sfdatasource:DataSource>
    <sfdatasource:DataSource.SortDescriptors>
      <sfdatasource:SortDescriptor PropertyName="ContactName" Direction="Ascending" Comparer="{StaticResource Comparer}"/>
    </sfdatasource:DataSource.SortDescriptors>
  </sfdatasource:DataSource>
</listView:SfListView.DataSource>
{% endhighlight %}
{% highlight c# %}
listView.DataSource.SortDescriptors.Add(new SortDescriptor()
{
  PropertyName = "ContactName",
  Direction = ListSortDirection.Ascending,
  Comparer = new CustomComparer()
});
{% endhighlight %}
{% endtabs %}

The following code example illustrates how to write a Custom Comparer.

{% highlight c# %}
public class CustomComparer : IComparer<object>, ISortDirection
{
  public int Compare(object x, object y)
  {
     int namX;
     int namY;

     //For Contacts Type data
     if (x.GetType() == typeof(Contacts))
     {
       //Calculating the length of ContactName if the object type is Contacts
       namX = ((Contacts)x).ContactName.Length;
       namY = ((Contacts)y).ContactName.Length;
     }
     else
     {
       namX = x.ToString().Length;
       namY = y.ToString().Length;
     }

     // Objects are compared and return the SortDirection
     if (namX.CompareTo(namY) > 0)
        return SortDirection == ListSortDirection.Ascending ? 1 : -1;
     else if (namX.CompareTo(namY) == -1)
        return SortDirection == ListSortDirection.Ascending ? -1 : 1;
     else
        return 0;
   }

   //Get or Set the SortDirection value
   private ListSortDirection _SortDirection;
   public ListSortDirection SortDirection
   {
     get { return _SortDirection; }
     set { _SortDirection = value; }
   }
}
{% endhighlight %}

## Sort the items on Header Tapped

SfListView allows you to sort the items on tapping the header by handling [ItemTapped](https://help.syncfusion.com/cr/cref_files/xamarin/sflistview/Syncfusion.SfListView.XForms~Syncfusion.ListView.XForms.SfListView~ItemTapped_EV.html) event of SfListView.

{% tabs %}
{% highlight xaml %}
xmlns:listView="clr-namespace:Syncfusion.ListView.XForms;assembly=Syncfusion.SfListView.XForms"
...
<listView:SfListView x:Name="listView" ItemSize="60"
                     ItemsSource="{Binding customerDetails}" ItemTapped="ListView_ItemTapped" IsStickyHeader="True">
<listView:SfListView.HeaderTemplate>
  <DataTemplate>
    <ViewCell>
      <ViewCell.View>
        <StackLayout BackgroundColor="Teal">
          <Label TextColor="White" FontSize="20" FontAttributes="Bold" Text="CustomerDetails" />
        </StackLayout>
      </ViewCell.View>
    </ViewCell>
  </DataTemplate>  
</listView:SfListView.HeaderTemplate>
{% endhighlight %}
{% highlight c# %}
listView = new SfListView();
listView.ItemsSource = viewmodel.customerDetails;
listView.ItemSize = 60;
listView.ItemTapped += ListView_ItemTapped;
listView.IsStickyHeader = true;
listView.HeaderTemplate = new DataTemplate(() => 
{
  var stacklayout = new StackLayout { BackgroundColor = Color.Teal };
  var label = new Label { Text = "CustomerDetails", TextColor = Color.White, 
                          FontAttributes = FontAttributes.Bold, FontSize = 20 };
  stacklayout.Children.Add(label);
  return stacklayout;
});
{% endhighlight %}
{% endtabs %}

When `ItemTapped` event is raised for Header, you can add the [SortDescriptor](https://help.syncfusion.com/cr/cref_files/xamarin/datasource/Syncfusion.DataSource.Portable~Syncfusion.DataSource.SortDescriptor.html) and refresh the view like below code example.

{% highlight c# %}
private void ListView_ItemTapped(object sender, Syncfusion.ListView.XForms.ItemTappedEventArgs e)
{
  //Applying sorting to the underlying data when the header item is tapped.
  if (e.ItemType == ItemType.Header && listView.IsStickyHeader)
  {
    listView.DataSource.SortDescriptors.Clear();
    listView.DataSource.SortDescriptors.Add(new SortDescriptor()
    {
      PropertyName = "ContactName",
      Direction = ListSortDirection.Ascending
    });
    listView.RefreshView();
  }
}
{% endhighlight %}