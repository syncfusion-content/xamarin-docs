---
layout: post
title: Sorting in SfListView
description: Describes about the sorting behavior in SfListView.
platform: xamarin
control: SfListView
documentation: ug
---

# Sorting 

The SfListView allows sorting the data either in ascending or descending order by using the [DataSource.SortDescriptors](https://help.syncfusion.com/cr/cref_files/xamarin/datasource/Syncfusion.DataSource.Portable~Syncfusion.DataSource.DataSource~SortDescriptors.html) property. It also supports to sort the data based on the custom logic.

## Programmatic sorting

The SfListView allows sorting on its data by using the [DataSource.SortDescriptors](https://help.syncfusion.com/cr/cref_files/xamarin/datasource/Syncfusion.DataSource.Portable~Syncfusion.DataSource.DataSource~SortDescriptors.html) property. A [SortDescriptor](https://help.syncfusion.com/cr/cref_files/xamarin/datasource/Syncfusion.DataSource.Portable~Syncfusion.DataSource.SortDescriptor.html) can be created for the property to be sorted, and add it into the `DataSource.SortDescriptors` collection.

N> You can refresh the view by calling [SfListView.RefreshView()](https://help.syncfusion.com/cr/cref_files/xamarin/sflistview/Syncfusion.SfListView.XForms~Syncfusion.ListView.XForms.SfListView~RefreshView.html) method.

SortDescriptor object holds the following three properties:

 * PropertyName: Defines name of the sorted property.
 * Direction: Defines an object of type [ListSortDirection](https://help.syncfusion.com/cr/cref_files/xamarin/datasource/Syncfusion.DataSource.Portable~Syncfusion.DataSource.ListSortDirection.html) that defines the sorting direction.
 * Comparer: Defines comparer to be applied when sorting takes place.
 
{% tabs %}
{% highlight xaml %}
<syncfusion:SfListView x:Name="listView">
  <syncfusion:SfListView.DataSource>
    <data:DataSource>
      <data:DataSource.SortDescriptors>
        <data:SortDescriptor PropertyName="ContactName" Direction="Ascending"/>
      </data:DataSource.SortDescriptors>
    </dataSource:DataSource>
  </syncfusion:SfListView.DataSource>
</syncfusion:SfListView>
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

N> It is mandatory to specify the `PropertyName` of `SortDescriptor`.

The following screenshot shows the output rendered when sorting is applied:

![](SfListView_images/SfListView-Sorting.png)

## Custom sorting

The SfListView allows sorting items based on the custom logic. The custom sorting can be applied to either [SfListView.DataSource.SortComparer](https://help.syncfusion.com/cr/cref_files/xamarin/datasource/Syncfusion.DataSource.Portable~Syncfusion.DataSource.DataSource~SortComparer.html) property or [SortDescriptor.Comparer](https://help.syncfusion.com/cr/cref_files/xamarin/datasource/Syncfusion.DataSource.Portable~Syncfusion.DataSource.SortDescriptor~Comparer.html) which is added into the [DataSource.SortDescriptors](https://help.syncfusion.com/cr/cref_files/xamarin/datasource/Syncfusion.DataSource.Portable~Syncfusion.DataSource.DataSource~SortDescriptors.html) collection.

To perform custom sorting for the underlying data based on the string length of the `ContactName`, follow the code example:

{% tabs %}
{% highlight xaml %}
<ContentPage>
  <ContentPage.Resources>
    <ResourceDictionary>
      <local:CustomComparer x:Key="Comparer" />
    </ResourceDictionary>
  </ContentPage.Resources>
  <syncfusion:SfListView x:Name="listView"
    <syncfusion:SfListView.DataSource>
      <data:DataSource>
        <data:DataSource.SortDescriptors>
          <data:SortDescriptor PropertyName="ContactName" Direction="Ascending" 
                               Comparer="{StaticResource Comparer}"/>
        </data:DataSource.SortDescriptors>
      </data:DataSource>
    </syncfusion:SfListView.DataSource>
  </syncfusion:SfListView>
</ContentPage>
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

To write custom comparer, follow the code example:

{% highlight c# %}
public class CustomComparer : IComparer<object>, ISortDirection
{
  public int Compare(object x, object y)
  {
     int nameX;
     int nameY;

     //For Contacts Type data
     if (x.GetType() == typeof(Contacts))
     {
       //Calculating the length of ContactName if the object type is Contacts
       nameX = ((Contacts)x).ContactName.Length;
       nameY = ((Contacts)y).ContactName.Length;
     }
     else
     {
       nameX = x.ToString().Length;
       nameY = y.ToString().Length;
     }

     // Objects are compared and return the SortDirection
     if (nameX.CompareTo(nameY) > 0)
        return SortDirection == ListSortDirection.Ascending ? 1 : -1;
     else if (nameX.CompareTo(nameY) == -1)
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

## Sort items on tapped header

The SfListView allows sorting items on tapping the header by handling [ItemTapped](https://help.syncfusion.com/cr/cref_files/xamarin/sflistview/Syncfusion.SfListView.XForms~Syncfusion.ListView.XForms.SfListView~ItemTapped_EV.html) event.

{% tabs %}
{% highlight xaml %}
<syncfusion:SfListView x:Name="listView" ItemSize="60"
                       ItemsSource="{Binding customerDetails}" 
                       ItemTapped="ListView_ItemTapped" 
                       IsStickyHeader="True">
  <syncfusion:SfListView.HeaderTemplate>
    <DataTemplate>
      <ViewCell>
        <ViewCell.View>
          <StackLayout BackgroundColor="Teal">
            <Label TextColor="White" FontSize="20" FontAttributes="Bold" Text="CustomerDetails" />
          </StackLayout>
        </ViewCell.View>
      </ViewCell>
    </DataTemplate>
  </syncfusion:SfListView.HeaderTemplate>
</syncfusion:SfListView>
{% endhighlight %}
{% highlight c# %}
listView = new SfListView();
listView.ItemsSource = viewModel.customerDetails;
listView.ItemSize = 60;
listView.ItemTapped += ListView_ItemTapped;
listView.IsStickyHeader = true;
listView.HeaderTemplate = new DataTemplate(() => 
{
  var stackLayout = new StackLayout { BackgroundColor = Color.Teal };
  var label = new Label { Text = "CustomerDetails", TextColor = Color.White, 
                          FontAttributes = FontAttributes.Bold, FontSize = 20 };
  stackLayout.Children.Add(label);
  return stackLayout;
});
{% endhighlight %}
{% endtabs %}

When `ItemTapped` event is raised for the header, add [SortDescriptor](https://help.syncfusion.com/cr/cref_files/xamarin/datasource/Syncfusion.DataSource.Portable~Syncfusion.DataSource.SortDescriptor.html), and refresh the view as in the following code example:

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