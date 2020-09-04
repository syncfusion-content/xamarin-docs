---
layout: post
title: Sorting in Syncfusion ListView
description: This section describes about the sorting behavior in Syncfusion Xamarin.Forms ListView and its various customization features.
platform: xamarin
control: SfListView
documentation: ug
---

# Sorting in Xamarin ListView (SfListView)

The SfListView supports sorting the data either in ascending or descending order by using [DataSource.SortDescriptors](https://help.syncfusion.com/cr/xamarin/Syncfusion.DataSource.DataSource.html#Syncfusion_DataSource_DataSource_SortDescriptors) property and by using the custom logic.

N> When ItemsSource changed for ListView, `DataSource.SortDescriptors` will be cleared by default. You need to add `DataSource.SortDescriptors` again after changing ItemsSource if you want to retain sorting in listview.

N> To sort the newly added listview items at runtime, set the `listView.DataSource.LiveDataUpdateMode` to `LiveDataUpdateMode.AllowDataShaping`. To learn more details about the [LiveDataUpdateMode](https://help.syncfusion.com/cr/xamarin/Syncfusion.DataSource.LiveDataUpdateMode.html), refer to [here](https://help.syncfusion.com/xamarin/datasource/datasource-gettingstarted#defining-the-livedataupdatemode).

## Programmatic sorting

Sorting the data by creating the [SortDescriptor](https://help.syncfusion.com/cr/xamarin/Syncfusion.DataSource.SortDescriptor.html) with required property name and direction and adding it into the [DataSource.SortDescriptors](https://help.syncfusion.com/cr/xamarin/Syncfusion.DataSource.DataSource.html#Syncfusion_DataSource_DataSource_SortDescriptors) property.

`SortDescriptor` object holds the following three properties:

* [PropertyName](https://help.syncfusion.com/cr/xamarin/Syncfusion.DataSource.SortDescriptor.html#Syncfusion_DataSource_SortDescriptor_PropertyName): Describes the name of the sorted property.
* [Direction](https://help.syncfusion.com/cr/xamarin/Syncfusion.DataSource.SortDescriptor.html#Syncfusion_DataSource_SortDescriptor_Direction): Describes an object of type [ListSortDirection](https://help.syncfusion.com/cr/xamarin/Syncfusion.DataSource.ListSortDirection.html) that defines the sorting direction.
* [Comparer](https://help.syncfusion.com/cr/xamarin/Syncfusion.DataSource.SortDescriptor.html#Syncfusion_DataSource_SortDescriptor_Comparer): Describes the comparer to be applied when sorting take place.

{% tabs %}
{% highlight xaml %}
<ContentPage xmlns:syncfusion="clr-namespace:Syncfusion.ListView.XForms;assembly=Syncfusion.SfListView.XForms"
             xmlns:data="clr-namespace:Syncfusion.DataSource;assembly=Syncfusion.DataSource.Portable">
  <sync:SfListView x:Name="listView">
            <sync:SfListView.DataSource>
                <data:DataSource>
                    <data:DataSource.SortDescriptors>
                        <data:SortDescriptor PropertyName="ContactName" Direction="Ascending"/>
                    </data:DataSource.SortDescriptors>
                </data:DataSource>
            </sync:SfListView.DataSource>
  </syncfusion:SfListView>
</ContentPage>
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

![Sort items in listview](SfListView_images/SfListView-Sorting.png)

## Custom sorting

Sort the items based on the custom logic and it can be applied to either [SfListView.DataSource.SortComparer](https://help.syncfusion.com/cr/xamarin/Syncfusion.DataSource.DataSource.html#Syncfusion_DataSource_DataSource_SortComparer) property or [SortDescriptor.Comparer](https://help.syncfusion.com/cr/xamarin/Syncfusion.DataSource.SortDescriptor.html#Syncfusion_DataSource_SortDescriptor_Comparer) which is added into the [DataSource.SortDescriptors](https://help.syncfusion.com/cr/xamarin/Syncfusion.DataSource.DataSource.html#Syncfusion_DataSource_DataSource_SortDescriptors) collection.

You can download the entire sample code from the [github](https://github.com/SyncfusionExamples/xamarin-forms-listview-custom-sorting).

N> If the `PropertyName` in the [SortDescriptor](https://help.syncfusion.com/cr/xamarin/Syncfusion.DataSource.SortDescriptor.html) and `GroupDescriptor` are same then, [GroupResult](https://help.syncfusion.com/cr/xamarin/Syncfusion.DataSource.Extensions.GroupResult.html) will be passed as parameters for the `SortDescriptor.Comparer`. Otherwise data objects are passed. To sort the data items alone, set the different `PropertyName` in both `SortDescriptor` and `GroupDescriptor` properties.

{% tabs %}
{% highlight xaml %}
<ContentPage xmlns:syncfusion="clr-namespace:Syncfusion.ListView.XForms;assembly=Syncfusion.SfListView.XForms"
             xmlns:data="clr-namespace:Syncfusion.DataSource;assembly=Syncfusion.DataSource.Portable">
  <ContentPage.Resources>
    <ResourceDictionary>
      <local:CustomSortComparer x:Key="CustomSortComparer" />
    </ResourceDictionary>
  </ContentPage.Resources>
  <syncfusion:SfListView x:Name="listView"
    <syncfusion:SfListView.DataSource>
      <data:DataSource>
        <data:DataSource.SortDescriptors>
          <data:SortDescriptor Comparer="{StaticResource CustomSortComparer}"/>
        </data:DataSource.SortDescriptors>
      </data:DataSource>
    </syncfusion:SfListView.DataSource>
  </syncfusion:SfListView>
</ContentPage>
{% endhighlight %}
{% highlight c# %}
listView.DataSource.SortDescriptors.Add(new SortDescriptor()
{
  Comparer = new CustomSortComparer()
});
{% endhighlight %}
{% endtabs %}

{% tabs %}
{% highlight c# %}
public class CustomSortComparer : IComparer<object>
{
  public int Compare(object x, object y)
  {
     if (x.GetType() == typeof(ListViewContactsInfo))
     {
        var xitem = (x as ListViewContactsInfo).ContactName;
        var yitem = (y as ListViewContactsInfo).ContactName;

        if (xitem.Length > yitem.Length)
        {
           return 1;
        }
        else if (xitem.Length < yitem.Length)
        {
           return -1;
        }
        else
        {
           if (string.Compare(xitem, yitem) == -1)
               return -1;
           else if (string.Compare(xitem, yitem) == 1)
               return 1;
        }
     }

     return 0;
   }
}
{% endhighlight %}
{% endtabs %}

For more information about custom sorting of groups, please refer the documentation [here](https://help.syncfusion.com/xamarin/sflistview/grouping#custom-sorting-of-groups).

## Sort the items on header tapped

To apply the sorting when tapping the header, handle the [ItemTapped](https://help.syncfusion.com/cr/xamarin/Syncfusion.ListView.XForms.SfListView.html) event of the SfListView.

{% tabs %}
{% highlight xaml %}
<ContentPage xmlns:syncfusion="clr-namespace:Syncfusion.ListView.XForms;assembly=Syncfusion.SfListView.XForms"
             xmlns:data="clr-namespace:Syncfusion.DataSource;assembly=Syncfusion.DataSource.Portable">
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
</ContentPage>
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

When the `ItemTapped` event is raised for the Header, add the [SortDescriptor](https://help.syncfusion.com/cr/xamarin/Syncfusion.DataSource.SortDescriptor.html) and refresh the view.

{% tabs %}
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
  }
}
{% endhighlight %}
{% endtabs %}

## Sort the items along with grouping
 
The SfListView allows sorting the items along with grouping by adding the [DataSource.GroupDescriptors](https://help.syncfusion.com/cr/xamarin/Syncfusion.DataSource.DataSource.html#Syncfusion_DataSource_DataSource_GroupDescriptors) and the [DataSource.SortDescriptors](https://help.syncfusion.com/cr/xamarin/Syncfusion.DataSource.DataSource.html#Syncfusion_DataSource_DataSource_SortDescriptors) with required property name. 

## Sorting with grouping by year

Sorting the items along with grouping by using [KeySelector](https://help.syncfusion.com/cr/xamarin/Syncfusion.DataSource.GroupDescriptor.html#Syncfusion_DataSource_GroupDescriptor_KeySelector) based on retuning the year value of the data-time property.

{% tabs %}
{% highlight xaml %}
<ContentPage xmlns:syncfusion="clr-namespace:Syncfusion.ListView.XForms;assembly=Syncfusion.SfListView.XForms"
             xmlns:data="clr-namespace:Syncfusion.DataSource;assembly=Syncfusion.DataSource.Portable">
  <ContentPage.Content>
    <syncfusion:SfListView x:Name="listView" ItemsSource="{Binding Items}" ItemSize="50">
      <syncfusion:SfListView.GroupHeaderTemplate>
        <DataTemplate>
		  <Grid>
          <Label Text= "{Binding Key}" BackgroundColor="Teal" FontAttributes="Bold" TextColor="White"/>
		  </Grid>
        </DataTemplate>
      </syncfusion:SfListView.GroupHeaderTemplate>
    </syncfusion:SfListView>
  </ContentPage.Content>
</ContentPage>
{% endhighlight %}
{% highlight c# %}
var listView = new SfListView();
listView.ItemSize = 50;
listView.ItemsSource = viewModel.Items;
listView.GroupHeaderTemplate = new DataTemplate(() => 
{
   var grid = new Grid();
   var headerLabel = new Label
   {
   TextColor = Color.White,
   FontAttributes = FontAttributes.Bold,
   BackgroundColor=Color.Teal
   };
   headerLabel.SetBinding(Label.TextProperty, new Binding("key"));
   grid.Children.Add(headerLabel);
   return grid;
});
listView.DataSource.GroupDescriptors.Add(new GroupDescriptor()
{
  PropertyName = "DateOfBirth",
  KeySelector = (object obj1) =>
  {
   var item = (obj1 as Contacts);
   return item.DateOfBirth.Year;
  },
});
this.listView.DataSource.SortDescriptors.Add(new SortDescriptor()
{
  PropertyName = "DateOfBirth",
  Direction = ListSortDirection.Ascending
});
{% endhighlight %}
{% endtabs %}

The following screenshot shows the output when items are sorted by year. Download the entire source code from GitHub [here](https://github.com/SyncfusionExamples/Using-sorting-and-grouping-xamarin.forms-listview)

![Custom sort by year in listview](SfListView_images/SfListView-Sorting1.png)

## Sorting with grouping by month and year

Sorting the items along with grouping by using `KeySelector` based on retuning the month and year value of the data-time property.

{% tabs %}
{% highlight xaml %}
<ContentPage xmlns:syncfusion="clr-namespace:Syncfusion.ListView.XForms;assembly=Syncfusion.SfListView.XForms"
             xmlns:data="clr-namespace:Syncfusion.DataSource;assembly=Syncfusion.DataSource.Portable">
  <ContentPage.Content>
    <syncfusion:SfListView x:Name="listView">
      <syncfusion:SfListView.DataSource>
        <data:DataSource>
        <data:DataSource.GroupDescriptors>
            <data:GroupDescriptor PropertyName="ContactName" />
          </data:DataSource.GroupDescriptors>
          <data:DataSource.SortDescriptors>
            <data:SortDescriptor PropertyName="ContactName" Direction="Ascending"/>
          </data:DataSource.SortDescriptors>
        </data:DataSource>
      </syncfusion:SfListView.DataSource>
    </syncfusion:SfListView>
  </ContentPage.Content>
</ContentPage>
{% endhighlight %}
{% highlight c# %}
public partial class MainPage : ContentPage
{
   public MainPage()
   {
       InitializeComponent();
       listView.DataSource.GroupDescriptors.Add(new GroupDescriptor()
       {
           PropertyName = "DateOfBirth",
           KeySelector = (object obj1) =>
           {
               var item = (obj1 as Contacts);
               return item.DateOfBirth.Month + "/" + item.DateOfBirth.Year;
           },
           Comparer = new CustomGroupComparer()
       });
       this.listView.DataSource.SortDescriptors.Add(new SortDescriptor()
       {
           PropertyName = "DateOfBirth",
           Direction = ListSortDirection.Ascending
       });
   }
}
{% endhighlight %}
{% endtabs %}

The following screenshot shows the output when items are sorted by month and year.

![Custom sort by month in listview](SfListView_images/SfListView-Sorting2.png)

