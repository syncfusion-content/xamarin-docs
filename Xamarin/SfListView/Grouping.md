---
layout: post
title: Grouping in SfListView
description: Describes about the grouping and its functionalities in SfListView.
platform: xamarin
control: SfListView
documentation: ug
---

# Grouping 

A group represents a collection of items that belongs to a category. When grouping is applied, the data is organized into different groups based on key values. Each group is identified by its [Key](https://help.syncfusion.com/cr/cref_files/xamarin/datasource/Syncfusion.DataSource.Portable~Syncfusion.DataSource.Extensions.GroupResult~Key.html), by which you can get the underlying data in the group.

## Programmatic grouping

The SfListView allows grouping from the code by defining [GroupDescriptor](https://help.syncfusion.com/cr/cref_files/xamarin/datasource/Syncfusion.DataSource.Portable~Syncfusion.DataSource.GroupDescriptor.html) object, and adding it into the [DataSource.GroupDescriptors](https://help.syncfusion.com/cr/cref_files/xamarin/datasource/Syncfusion.DataSource.Portable~Syncfusion.DataSource.DataSource~GroupDescriptors.html) collection. This control groups the data based on the `GroupDescriptor` object added to this collection. 

`GroupDescriptor` object holds the following properties:

 * PropertyName: Describes name of the property to be grouped.
 * KeySelector: Describes selector to return the group key.
 * Comparer: Describes comparer to be applied when sorting takes place.

To apply grouping to the data, follow the code example:

{% tabs %}
{% highlight xaml %}
<syncfusion:SfListView x:Name="listView">
  <syncfusion:SfListView.DataSource>
    <data:DataSource>
      <data:DataSource.GroupDescriptors>
        <data:GroupDescriptor PropertyName="ContactName" />
      </data:DataSource.GroupDescriptors>
    </data:DataSource>
  </syncfusion:SfListView.DataSource>
</syncfusion:SfListView>
{% endhighlight %}
{% highlight c# %}
listView.DataSource.GroupDescriptors.Add(new GroupDescriptor()
{
  PropertyName = "ContactName",
}); 
{% endhighlight %}
{% endtabs %}

## Customizing group header

The SfListView allows customizing the User Interface (UI) for the group header items by using [SfListView.GroupHeaderTemplate](https://help.syncfusion.com/cr/cref_files/xamarin/sflistview/Syncfusion.SfListView.XForms~Syncfusion.ListView.XForms.SfListView~GroupHeaderTemplate.html) property.

To create the custom view for group header items, and binding the [Key](https://help.syncfusion.com/cr/cref_files/xamarin/datasource/Syncfusion.DataSource.Portable~Syncfusion.DataSource.Extensions.GroupResult~Key.html) to it, follow the code example:

{% tabs %}
{% highlight xaml %}
<syncfusion:SfListView x:Name="listView">
  <syncfusion:SfListView.GroupHeaderTemplate>
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
  </syncfusion:SfListView.GroupHeaderTemplate>
</syncfusion:SfListView>
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

## Binding multiple properties in group descriptor

The SfListView supports to bind multiple properties to [GroupDescriptor](https://help.syncfusion.com/cr/cref_files/xamarin/datasource/Syncfusion.DataSource.Portable~Syncfusion.DataSource.GroupDescriptor.html) object by using `KeySelector`, in which the group header items can be created with multiple data model object effectively.

{% highlight c# %}
listView.DataSource.GroupDescriptors.Add(new GroupDescriptor()
{
  PropertyName = "Designation",
  KeySelector = (object obj1) =>
  {
     var item = (obj1 as Employee);
     return item.Designation + item.Level;
  }
});
{% endhighlight %}

## Customizing the group header size

The SfListView allows customizing size of the group header items by setting the [SfListView.GroupHeaderSize](https://help.syncfusion.com/cr/cref_files/xamarin/sflistview/Syncfusion.SfListView.XForms~Syncfusion.ListView.XForms.SfListView~GroupHeaderSize.html) property. The default value of this property is 40. This property responds to runtime changes. So it can be customized based on the requirement.

To customize the group header size in the SfListView, follow the code example:

{% tabs %}
{% highlight xaml %}
<syncfusion:SfListView x:Name="listView" GroupHeaderSize="60" />
{% endhighlight %}
{% highlight c# %}
listView.GroupHeaderSize = 60;
{% endhighlight %}
{% endtabs %}

N> For vertical orientation, the group header size is considered as height. For horizontal orientation, it will be considered as width.

## Custom grouping

The SfListView allows grouping the items based on custom logic. The custom grouping can be applied to either [SfListView.DataSource.GroupComparer](https://help.syncfusion.com/cr/cref_files/xamarin/datasource/Syncfusion.DataSource.Portable~Syncfusion.DataSource.DataSource~GroupComparer.html) property or [GroupDescriptor.Comparer](https://help.syncfusion.com/cr/cref_files/xamarin/datasource/Syncfusion.DataSource.Portable~Syncfusion.DataSource.GroupDescriptor~Comparer.html) which is added into the [DataSource.GroupDescriptors](https://help.syncfusion.com/cr/cref_files/xamarin/datasource/Syncfusion.DataSource.Portable~Syncfusion.DataSource.DataSource~GroupDescriptors.html) collection.

To perform custom grouping for the underlying data based on the group item count, follow the code example:

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

To apply the custom grouping logic, follow the code example:

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

## Expand or collapse groups
 
By default, groups will be in expanded state in the SfListView. Expand or collapse the group at runtime by setting [SfListView.AllowGroupExpandCollapse](https://help.syncfusion.com/cr/cref_files/xamarin/sflistview/Syncfusion.SfListView.XForms~Syncfusion.ListView.XForms.SfListView~AllowGroupExpandCollapse.html) to `true`. So when tapping on group header, the tapped group gets collapse if the group is in expand state and vice-versa. 

{% tabs %}
{% highlight xaml %}
<syncfusion:SfListView x:Name="listView" ItemSize="70" AllowGroupExpandCollapse="True" 
                     ItemsSource="{Binding contactsInfo}" />          
{% endhighlight %}
{% highlight c# %}
listView.AllowGroupExpandCollapse = true;
{% endhighlight %}
{% endtabs %}

The following screenshot shows the output rendered when the groups are collapsed:

![](SfListView_images/SfListView-Grouping.png)

### Programmatically expand or collapse groups

You can expand or collapse the groups programmatically at runtime.

#### Expand or collapse all groups

You can expand or collapse all groups programmatically at runtime by using [SfListView.ExpandAll()](https://help.syncfusion.com/cr/cref_files/xamarin/sflistview/Syncfusion.SfListView.XForms~Syncfusion.ListView.XForms.SfListView~ExpandAll.html) method and [SfListView.CollapseAll()](https://help.syncfusion.com/cr/cref_files/xamarin/sflistview/Syncfusion.SfListView.XForms~Syncfusion.ListView.XForms.SfListView~CollapseAll.html) method.

{% tabs %}
{% highlight c# %}
listView.ExpandAll();
listView.CollapseAll();
{% endhighlight %}
{% endtabs %}

#### Expand or collapse the specific group

You can expand or collapse the specific group by using [SfListView.ExpandGroup(GroupResult group)](https://help.syncfusion.com/cr/cref_files/xamarin/sflistview/Syncfusion.SfListView.XForms~Syncfusion.ListView.XForms.SfListView~ExpandGroup.html) method and [SfListView.CollapseGroup(GroupResult group)](https://help.syncfusion.com/cr/cref_files/xamarin/sflistview/Syncfusion.SfListView.XForms~Syncfusion.ListView.XForms.SfListView~CollapseGroup.html) method.

{% tabs %}
{% highlight c# %}
var group = listView.DataSource.Groups[0];
listView.ExpandGroup(group);
listView.CollapseGroup(group);
{% endhighlight %}
{% endtabs %}

## Stick the group header

The SfListView allows sticking the group header to view by enabling the [SfListView.IsStickyGroupHeader](https://help.syncfusion.com/cr/cref_files/xamarin/sflistview/Syncfusion.SfListView.XForms~Syncfusion.ListView.XForms.SfListView~IsStickyGroupHeader.html) property. If `IsStickyGroupHeader` is `true`, the corresponding group header is in view until the last item of the group goes out of view on scrolling.

N> When the `IsStickyGroupHeader` is set to `true`, [IsStickyHeader](https://help.syncfusion.com/cr/cref_files/xamarin/sflistview/Syncfusion.SfListView.XForms~Syncfusion.ListView.XForms.SfListView~IsStickyHeader.html) property will be changed to `true` because the header item cannot be scrollable when the `IsStickyGroupHeader` is `true`. When the `IsStickyHeader` is set to `false`, if `IsStickyGroupHeader` is `true` then it will be changed to `false` because the group header item cannot be sticky when the `IsStickyHeader` is `true`.

{% tabs %}
{% highlight xaml %}
<syncfusion:SfListView x:Name="listView" ItemSize="70" IsStickyGroupHeader="True" 
                     ItemsSource="{Binding contactsInfo}" />          
{% endhighlight %}
{% highlight c# %}  
listView.IsStickyGroupHeader = true;
{% endhighlight %}
{% endtabs %}

## Events

### GroupExpanding event

The [SfListView.GroupExpanding](https://help.syncfusion.com/cr/cref_files/xamarin/sflistview/Syncfusion.SfListView.XForms~Syncfusion.ListView.XForms.SfListView~GroupExpanding_EV.html) event occurs when the group is being expanded.
 
The [GroupExpandCollapseChangingEventArgs](https://help.syncfusion.com/cr/cref_files/xamarin/sflistview/Syncfusion.SfListView.XForms~Syncfusion.ListView.XForms.GroupExpandCollapseChangingEventHandler.html) of the `GroupExpanding` event provides information about the expanding group, and it has the following members:

 * `Groups`: Gets list of groups which are being expanded.
 * `Cancel`: Decides to cancel the group expansion.

The group expansion can be canceled by setting `GroupExpandCollapseChangingEventArgs.Cancel` to `true`.

{% tabs %}
{% highlight xaml %}
<syncfusion:SfListView x:Name="listView" ItemsSource="{Binding contactsInfo}" 
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

The [GroupExpandCollapseChangedEventArgs](https://help.syncfusion.com/cr/cref_files/xamarin/sflistview/Syncfusion.SfListView.XForms~Syncfusion.ListView.XForms.GroupExpandCollapseChangedEventHandler.html) of the `GroupExpanded` event provides information about the expanded group, and it has the following member:

 * `Groups`: Gets list of groups which are expanded.

### GroupCollapsing event 

The [SfListView.GroupCollapsing](https://help.syncfusion.com/cr/cref_files/xamarin/sflistview/Syncfusion.SfListView.XForms~Syncfusion.ListView.XForms.SfListView~GroupCollapsing_EV.html) event occurs when the group is being collapsed.

The [GroupExpandCollapseChangingEventArgs](https://help.syncfusion.com/cr/cref_files/xamarin/sflistview/Syncfusion.SfListView.XForms~Syncfusion.ListView.XForms.GroupExpandCollapseChangingEventHandler.html) of the `GroupCollapsing` event provides information about the collapsing group, and it contains the following members:

 * `Groups`: Gets list of groups which are being collapsed.

 * `Cancel`: Decides to cancel the group collapsing.

You can cancel the group is being collapsed by using `GroupExpandCollapseChangingEventArgs.Cancel` of `GroupCollapsing` event.

{% tabs %}
{% highlight xaml %}
<syncfusion:SfListView x:Name="listView" ItemsSource="{Binding contactsInfo}" 
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
 
The [GroupExpandCollapseChangedEventArgs](https://help.syncfusion.com/cr/cref_files/xamarin/sflistview/Syncfusion.SfListView.XForms~Syncfusion.ListView.XForms.GroupExpandCollapseChangedEventHandler.html) of the `GroupCollapsed` event provides information about collapsed group, and it contains the following member:

 * `Groups`: Gets list of groups which are collapsed.

## How to 

### group the items by ignoring the case

The SfListView allows grouping items by ignoring the case sensitive using `KeySelector` property in the [GroupDescriptor](https://help.syncfusion.com/cr/cref_files/xamarin/datasource/Syncfusion.DataSource.Portable~Syncfusion.DataSource.GroupDescriptor.html). While returning the `KeySelector`, convert the required property name in the data model which is to group either as `Upper` or `Lower` case as per the requirement. The items will be grouped based on the `KeySelector` with the case sensitive which has been returned in it.

{% highlight c# %}
listView.DataSource.GroupDescriptors.Add(new GroupDescriptor() 
{ 
  PropertyName = "ContactName", 
  KeySelector = (object obj) => 
  { 
    return (obj as Contacts).ContactName.ToUpper()[0]; 
  } 
}); 
{% endhighlight %}


### multilevel grouping in the SfListView

The SfListView allows arranging the grouped items in hierarchical structure by customizing the [GroupHeaderTemplate](https://help.syncfusion.com/cr/cref_files/xamarin/sflistview/Syncfusion.SfListView.XForms~Syncfusion.ListView.XForms.SfListView~GroupHeaderTemplate.html) property, and by adding multiple [GroupDescriptor](https://help.syncfusion.com/cr/cref_files/xamarin/datasource/Syncfusion.DataSource.Portable~Syncfusion.DataSource.GroupDescriptor.html) objects into the [GroupDescriptors](https://help.syncfusion.com/cr/cref_files/xamarin/datasource/Syncfusion.DataSource.Portable~Syncfusion.DataSource.DataSource~GroupDescriptors.html) collection. 

In the `GroupHeaderTemplate`, set the `Padding` property to the custom view based on the requirement in order to arrange the group header items and sub group header items in the hierarchical structure. You can also download the entire source code of this demo from [here](http://www.syncfusion.com/downloads/support/directtrac/general/ze/Listview_Grouping1168276266).

{% highlight xaml %}
xmlns:syncfusion="clr-namespace:Syncfusion.ListView.XForms;assembly=Syncfusion.SfListView.XForms"
xmlns:dataSource="clr-namespace:Syncfusion.DataSource;assembly=Syncfusion.DataSource.Portable"
...
<ContentPage.Resources>
  <ResourceDictionary>
    <local:GroupHeaderConverter x:Key="TemplateConverter"/>
  </ResourceDictionary>
</ContentPage.Resources>
<syncfusion:SfListView ItemsSource="{Binding EmployeeInfo}" ItemSize="60">
  <syncfusion:SfListView.DataSource>
    <dataSource:DataSource>
       <dataSource:DataSource.GroupDescriptors>
          <dataSource:GroupDescriptor PropertyName="Designation" />
          <dataSource:GroupDescriptor PropertyName="Level" />
       </dataSource:DataSource.GroupDescriptors>
    </dataSource:DataSource>
  </syncfusion:SfListView.DataSource>
  <syncfusion:SfListView.GroupHeaderTemplate>
     <DataTemplate>
        <ViewCell>
          <ViewCell.View>
             <StackLayout BackgroundColor="{Binding Level,Converter={StaticResource TemplateConverter}}"
                          Padding="{Binding Level,Converter={StaticResource TemplateConverter}}">
                <Label Text="{Binding Key}" FontSize="22" FontAttributes="Bold" Margin="0"
                       VerticalOptions="Center" HorizontalOptions="Start"/>
             </StackLayout>
          </ViewCell.View>
        </ViewCell>
     </DataTemplate>
  </syncfusion:SfListView.GroupHeaderTemplate>
...
</syncfusion:SfListView>
{% endhighlight %}

{% highlight c# %}
public class GroupHeaderConverter : IValueConverter
{
  public object Convert(object value, Type targetType, object parameter, CultureInfo culture)
  {
     if (targetType.Name == "Color")
     {
        if ((int)value == 1)
           return Color.FromHex("#D3D3D3");
        else
           return Color.Transparent;
     }
     else
     {
        if ((int)value == 1)
           return new Thickness(5, 5, 5, 0);
        else
           return new Thickness((int)value * 15, 5, 5, 0);
     }
  }

  public object ConvertBack(object value, Type targetType, object parameter, CultureInfo culture)
  {
     throw new NotImplementedException();
  }
}
{% endhighlight %}