---
layout: post
title: Grouping | SfListView | Xamarin | Syncfusion
description: How to group the data in SfListView and about the properties and customizations in grouping.
platform: xamarin
control: SfListView
documentation: ug
---

# Grouping 

A group represents a collection of items that belong to a category. When grouping is applied, the data is organized into different groups based on key values. Each group is identified by its [Key](https://help.syncfusion.com/cr/cref_files/xamarin/datasource/Syncfusion.DataSource.Portable~Syncfusion.DataSource.Extensions.GroupResult~Key.html) by which you can get the underlying data in the group.

## Programmatic Grouping

SfListView allows to perform grouping from the code by defining the [GroupDescriptor](https://help.syncfusion.com/cr/cref_files/xamarin/datasource/Syncfusion.DataSource.Portable~Syncfusion.DataSource.GroupDescriptor.html) object and adding it into the [DataSource.GroupDescriptors](https://help.syncfusion.com/cr/cref_files/xamarin/datasource/Syncfusion.DataSource.Portable~Syncfusion.DataSource.DataSource~GroupDescriptors.html) collection. SfListView groups the data based on the `GroupDescriptor` object that is added to this collection. 
`GroupDescriptor` object holds the following properties:

* PropertyName: Name of the property to be grouped.
* KeySelector: Selector to return the group key.
* Comparer: Comparer to be applied in when sorting take place.

The following code example illustrates how to apply grouping to the data in SfListView.

{% tabs %}
{% highlight xaml %}
<listView:SfListView.DataSource>
  <dataSource:DataSource>
    <dataSource:DataSource.GroupDescriptors>
      <dataSource:GroupDescriptor PropertyName="ContactName" />
    </dataSource:DataSource.GroupDescriptors>
  </dataSource:DataSource>
</listView:SfListView.DataSource>
{% endhighlight %}
{% highlight c# %}
listView.DataSource.GroupDescriptors.Add(new GroupDescriptor()
{
  PropertyName = "ContactName",
}); 
{% endhighlight %}
{% endtabs %}

## Define an ItemTemplate for GroupHeader

SfListView allows you to customize the User Interface (UI) for group header items by using [SfListView.GroupHeaderTemplate](https://help.syncfusion.com/cr/cref_files/xamarin/sflistview/Syncfusion.SfListView.XForms~Syncfusion.ListView.XForms.SfListView~GroupHeaderTemplate.html) property.

The following code illustrates how to create the custom view for group header items and binding the data to it.

{% tabs %}
{% highlight xaml %}
<listView:SfListView.GroupHeaderTemplate>
  <DataTemplate>
    <ViewCell>
      <ViewCell.View>
        <StackLayout BackgroundColor="#E4E4E4">
          <Label Text="{Binding Key}" 
                 FontSize="22" 
                 FontAttributes="Bold"
                 VerticalOptions="Center" 
                 HorizontalOptions="Start" 
                 Margin="20,0,0,0" />
        </StackLayout>
      </ViewCell.View>
    </ViewCell>
  </DataTemplate>
</listView:SfListView.GroupHeaderTemplate>
{% endhighlight %}
{% highlight c# %}
listView.GroupHeaderTemplate = new DataTemplate(() =>
{
  var grid = new Grid { BackgroundColor = Color.FromHex("#E4E4E4") };
  var label = new Label
  {
    FontAttributes = FontAttributes.Bold,
    FontSize = 22,
    VerticalOptions = LayoutOptions.Center,
    HorizontalOptions = LayoutOptions.Start,
    Margin = new Thickness(20, 0, 0, 0),
  };
  label.SetBinding(Label.TextProperty, new Binding("Key"));
  grid.Children.Add(label);
  return grid;
});
{% endhighlight %}
{% endtabs %}

## Customize the GroupHeaderSize

SfListView allows you to customize the size of the group header items by setting the [SfListView.GroupHeaderSize](https://help.syncfusion.com/cr/cref_files/xamarin/sflistview/Syncfusion.SfListView.XForms~Syncfusion.ListView.XForms.SfListView~GroupHeaderSize.html) property. The default value of this property is 40. This property responds to runtime changes and hence you can customize it based on your requirement.

The following code example illustrates how to customize the group header size in SfListView.

{% tabs %}
{% highlight xaml %}
<listView:SfListView x:Name="listView" GroupHeaderSize="60" />
{% endhighlight %}
{% highlight c# %}
listView.GroupHeaderSize = 60;
{% endhighlight %}
{% endtabs %}

## Custom Grouping

SfListView allows you to group the items based on custom logic. The custom grouping can be applied either to [SfListView.DataSource.GroupComparer](https://help.syncfusion.com/cr/cref_files/xamarin/datasource/Syncfusion.DataSource.Portable~Syncfusion.DataSource.DataSource~GroupComparer.html) property or to [Comparer](https://help.syncfusion.com/cr/cref_files/xamarin/datasource/Syncfusion.DataSource.Portable~Syncfusion.DataSource.GroupDescriptor~Comparer.html) of [GroupDescriptor](https://help.syncfusion.com/cr/cref_files/xamarin/datasource/Syncfusion.DataSource.Portable~Syncfusion.DataSource.GroupDescriptor.html) property which is added into the [DataSource.GroupDescriptors](https://help.syncfusion.com/cr/cref_files/xamarin/datasource/Syncfusion.DataSource.Portable~Syncfusion.DataSource.DataSource~GroupDescriptors.html) collection.

The following code example illustrates how to perform custom grouping for underlying data based on the group item count.

{% highlight c# %}
listView.DataSource.GroupDescriptors.Add(new GroupDescriptor()
{
  PropertyName = "ContactName",
  KeySelector = (object obj1) =>
  {
    var item = (obj1 as Contacts);
    return item.ContactName[0].ToString();
  }
  Comparer = new CustomGroupComparer()
});
{% endhighlight %}

The following code example illustrates how to apply the custom grouping logic.

{% highlight c# %}
public class CustomGroupComparer : IComparer<GroupResult>, ISortDirection
{
  public CustomGroupComparer()
  {
    this.SortDirection = ListSortDirection.Ascending;
  }

  public ListSortDirection SortDirection
  {
    get;
    set;
  }

  public int Compare(GroupResult x, GroupResult y)
  {
    int groupX;
    int groupY;

    groupX = x.Count;
    groupY = y.Count;

    // Objects are compared and return the SortDirection
    if (groupX.CompareTo(groupY) > 0)
      return SortDirection == ListSortDirection.Ascending ? 1 : -1;
    else if (groupX.CompareTo(groupY) == -1)
      return SortDirection == ListSortDirection.Ascending ? -1 : 1;
    else
      return 0;

  }
}
{% endhighlight %}

## Expand or Collapse the groups
 
By default, the groups will be in expanded state in SfListView. You can expand or collapse the group in runtime by setting [SfListView.AllowGroupExpandCollapse](https://help.syncfusion.com/cr/cref_files/xamarin/sflistview/Syncfusion.SfListView.XForms~Syncfusion.ListView.XForms.SfListView~AllowGroupExpandCollapse.html) to `true`. So, when user tap on group header, then the tapped group gets collapse if the group is in expand state and vice-versa. 

{% tabs %}
{% highlight xaml %}
<listView:SfListView x:Name="listView" ItemSize="70" AllowGroupExpandCollapse="True" 
                     ItemsSource="{Binding contactsinfo}" />          
{% endhighlight %}
{% highlight c# %}
listView.AllowGroupExpandCollapse = true;
{% endhighlight %}
{% endtabs %}

### Programmatically Expand or Collapse the groups

You can allow end-user to expand or collapse the groups programmatically at runtime.

#### Expand or Collapse all the groups

You can expand or collapse all the groups at programmatically at runtime by using [SfListView.ExpandAll()](https://help.syncfusion.com/cr/cref_files/xamarin/sflistview/Syncfusion.SfListView.XForms~Syncfusion.ListView.XForms.SfListView~ExpandAll.html) method and [SfListView.CollapseAll()](https://help.syncfusion.com/cr/cref_files/xamarin/sflistview/Syncfusion.SfListView.XForms~Syncfusion.ListView.XForms.SfListView~CollapseAll.html) method.

{% tabs %}
{% highlight c# %}
listView.ExpandAll();
listView.CollapseAll();
{% endhighlight %}
{% endtabs %}

#### Expand or Collapse the specific group

You can expand or collapse specific group by using [SfListView.ExpandGroup(GroupResult group)](https://help.syncfusion.com/cr/cref_files/xamarin/sflistview/Syncfusion.SfListView.XForms~Syncfusion.ListView.XForms.SfListView~ExpandGroup.html) method and [SfListView.CollapseGroup(GroupResult group)](https://help.syncfusion.com/cr/cref_files/xamarin/sflistview/Syncfusion.SfListView.XForms~Syncfusion.ListView.XForms.SfListView~CollapseGroup.html) method.

{% tabs %}
{% highlight c# %}
var group = listView.DataSource.Groups[0];
listView.ExpandGroup(group);
listView.CollapseGroup(group);
{% endhighlight %}
{% endtabs %}

## Stick the GroupHeader

SfListView allows you to stick the group header to view by enabling the property [SfListView.IsStickyGroupHeader](https://help.syncfusion.com/cr/cref_files/xamarin/sflistview/Syncfusion.SfListView.XForms~Syncfusion.ListView.XForms.SfListView~IsStickyGroupHeader.html). If `SfListView.IsStickyGroupHeader` is `true`, the key value of group is bind to the sticky group header. On scrolling the sticky group header gets updated based on the key value of group.

N> When the `IsStickyGroupHeader` is set as `true`, [IsStickyHeader](https://help.syncfusion.com/cr/cref_files/xamarin/sflistview/Syncfusion.SfListView.XForms~Syncfusion.ListView.XForms.SfListView~IsStickyHeader.html) property will be changed to `true` because the header item can't be scrollable when the `IsStickyGroupHeader` is `true`. When the `IsStickyHeader` is set as `false`, if `IsStickyGroupHeader` is `true` then it will be changed to `false` because the group header item can't be sticky when the `IsStickyHeader` is `true`.

{% tabs %}
{% highlight xaml %}
<listView:SfListView x:Name="listView" ItemSize="70" IsStickyGroupHeader="True" 
                     ItemsSource="{Binding contactsinfo}" />          
{% endhighlight %}
{% highlight c# %}
listView.IsStickyGroupHeader = true;
{% endhighlight %}
{% endtabs %}

## Events

### GroupExpanding event

The [SfListView.GroupExpanding](https://help.syncfusion.com/cr/cref_files/xamarin/sflistview/Syncfusion.SfListView.XForms~Syncfusion.ListView.XForms.SfListView~GroupExpanding_EV.html) event occurs when the group is being expanded.
 
The [GroupExpandCollapseChangingEventArgs](https://help.syncfusion.com/cr/cref_files/xamarin/sflistview/Syncfusion.SfListView.XForms~Syncfusion.ListView.XForms.GroupExpandCollapseChangingEventHandler.html) of the `GroupExpanding` event provides the information about the expanding group and it has the following members.

`Groups` - Gets a list that corresponding groups that is being expanded in view.

`Cancel` – Decides whether to cancel the group expansion.
 
You can cancel the group expansion by setting `GroupExpandCollapseChangingEventArgs.Cancel` to `true`.

{% tabs %}
{% highlight xaml %}
<listView:SfListView x:Name="listView" ItemsSource="{Binding contactsinfo}" 
                     GroupExpanding="ListView_GroupExpanding" />
{% endhighlight %}
{% highlight c# %}
listView.GroupExpanding += ListView_GroupExpanding;
{% endhighlight %}
{% endtabs %}

{% tabs %}
{% highlight c# %}
private void ListView_GroupExpanding(object sender, GroupExpandCollapseChangingEventArgs e)
{
  if (e.Groups[0] == listView.DataSource.Groups[0])
    e.Cancel = true;
}
{% endhighlight %}
{% endtabs %}

### GroupExpanded event

The [SfListView.GroupExpanded](https://help.syncfusion.com/cr/cref_files/xamarin/sflistview/Syncfusion.SfListView.XForms~Syncfusion.ListView.XForms.SfListView~GroupExpanded_EV.html) event occurs after the group is expanded.

The [GroupExpandCollapseChangedEventArgs](https://help.syncfusion.com/cr/cref_files/xamarin/sflistview/Syncfusion.SfListView.XForms~Syncfusion.ListView.XForms.GroupExpandCollapseChangedEventHandler.html) of the `GroupExpanded` event provides the information about the expanded group and it has the following member.

`Groups` - Gets a list that corresponding groups that is expanded in view.

### GroupCollapsing event 

The [SfListView.GroupCollapsing](https://help.syncfusion.com/cr/cref_files/xamarin/sflistview/Syncfusion.SfListView.XForms~Syncfusion.ListView.XForms.SfListView~GroupCollapsing_EV.html) event occurs when the group is being collapsed.

The [GroupExpandCollapseChangingEventArgs](https://help.syncfusion.com/cr/cref_files/xamarin/sflistview/Syncfusion.SfListView.XForms~Syncfusion.ListView.XForms.GroupExpandCollapseChangingEventHandler.html) of the `GroupCollapsing` event provides the information about the collapsing group and it contains the following member.

`Groups` - Gets a list that corresponding groups that is being collapsed in view.

`Cancel` – Decides whether to cancel the group collapsing.

You can cancel the group is being collapsed by using `GroupExpandCollapseChangingEventArgs.Cancel` of `GroupCollapsing` event.

{% tabs %}
{% highlight xaml %}
<listView:SfListView x:Name="listView" ItemsSource="{Binding contactsinfo}" 
                     GroupCollapsing="ListView_GroupCollapsing" />
{% endhighlight %}
{% highlight c# %}
listView.GroupCollapsing += ListView_GroupCollapsing;
{% endhighlight %}
{% endtabs %}

{% tabs %}
{% highlight c# %}
private void ListView_GroupCollapsing(object sender, GroupExpandCollapseChangingEventArgs e)
{
  if (e.Groups[0] == listView.DataSource.Groups[0])
    e.Cancel = true;
}
{% endhighlight %}
{% endtabs %}

### GroupCollapsed event
 
The [SfListView.GroupCollapsed](https://help.syncfusion.com/cr/cref_files/xamarin/sflistview/Syncfusion.SfListView.XForms~Syncfusion.ListView.XForms.SfListView~GroupCollapsed_EV.html) event occurs after the group is collapsed.
 
The [GroupExpandCollapseChangedEventArgs](https://help.syncfusion.com/cr/cref_files/xamarin/sflistview/Syncfusion.SfListView.XForms~Syncfusion.ListView.XForms.GroupExpandCollapseChangedEventHandler.html) of the `GroupCollapsed` event provides the information about collapsed group and it contains the following member.

`Groups` - Gets a list that corresponding groups that is collapsed in view.