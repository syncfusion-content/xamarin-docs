---
layout: post
title: Item Drag and Drop in Xamarin.forms ListView | Syncfusion
description: This topics describes about re-ordering the items in Syncfusion Xamarin.Forms ListView by drag and drop and its customizations.  
platform: xamarin
control: SfListView
documentation: ug
---

# Item Reordering in Xamarin ListView (SfListView)

The SfListView allows reordering by dragging and dropping items. It supports displaying the customized view in a template while dragging the item. It can be enabled by setting the [SfListView.DragStartMode](https://help.syncfusion.com/cr/xamarin/Syncfusion.ListView.XForms.SfListView.html#Syncfusion_ListView_XForms_SfListView_DragStartMode) property to `OnHold`. The drag and drop options are listed as follows:

 * None: Disables drag and drop. This is the default value.
 * OnHold: Allows dragging and dropping by holding the item.
 * OnDragIndicator: Allows dragging and dropping by loading the [DragIndicatorView](https://help.syncfusion.com/cr/xamarin/Syncfusion.ListView.XForms.DragIndicatorView.html) within [SfListView.ItemTemplate](https://help.syncfusion.com/cr/xamarin/Syncfusion.ListView.XForms.SfListView.html#Syncfusion_ListView_XForms_SfListView_ItemTemplate).

N> The [GridLayout](https://help.syncfusion.com/cr/xamarin/Syncfusion.ListView.XForms.GridLayout.html) does not support drag and drop. 

The drag and drop scenarios are as follows:

 * Items can be reordered to any position by auto-scrolling.
 * Items can be reordered in same group or in other groups but, no groups can be added to other groups.
 * Groups, header, and footer cannot be reordered.

To enable drag and drop using 'OnHold', follow the code example:

{% tabs %}
{% highlight xaml %}
<ContentPage  xmlns:syncfusion="clr-namespace:Syncfusion.ListView.XForms;assembly=Syncfusion.SfListView.XForms">
  <syncfusion:SfListView x:Name="listView" 
                   ItemsSource="{Binding ToDoList}"
                   DragStartMode="OnHold"
                   BackgroundColor="#FFE8E8EC"
                   ItemSize="60" />
</ContentPage>
{% endhighlight %}
{% highlight c# %}
listView.DragStartMode = DragStartMode.OnHold; 
{% endhighlight %}
{% endtabs %}

To enable drag and drop using both 'OnHold' and 'OnDragIndicator', follow the code example:

{% tabs %}
{% highlight xaml %}
<ContentPage xmlns:syncfusion="clr-namespace:Syncfusion.ListView.XForms;assembly=Syncfusion.SfListView.XForms">
  <syncfusion:SfListView x:Name="listView" 
                   ItemsSource="{Binding ToDoList}"
                   DragStartMode="OnHold, OnDragIndicator"
                   BackgroundColor="#FFE8E8EC"
                   ItemSize="60" />
</ContentPage>
{% endhighlight %}
{% highlight c# %}
listView.DragStartMode = DragStartMode.OnHold | DragStartMode.OnDragIndicator; 
{% endhighlight %}
{% endtabs %}

N> Reordering changes made only in view, and not in underlying collection. Thus, the changes will be reverted when performing sorting, grouping, or any other operation that refreshes view. You can update underlying collection by setting UpdateSource to `true`.

## Drag indicator view

To drag and drop the items by [DragIndicatorView](https://help.syncfusion.com/cr/xamarin/Syncfusion.ListView.XForms.DragIndicatorView.html), set the [SfListView.DragStartMode](https://help.syncfusion.com/cr/xamarin/Syncfusion.ListView.XForms.SfListView.html#Syncfusion_ListView_XForms_SfListView_DragStartMode) property to `OnDragIndicator`. To display the dragging item, define any custom user interface(UI) in `DragIndicatorView`.

N> You must set the SfListView instance as reference to the [ListView](https://help.syncfusion.com/cr/xamarin/Syncfusion.ListView.XForms.DragIndicatorView.html#Syncfusion_ListView_XForms_DragIndicatorView__ctor) property in `DragIndicatorView`.

{% tabs %}
{% highlight xaml %}
<ContentPage xmlns:syncfusion="clr-namespace:Syncfusion.ListView.XForms;assembly=Syncfusion.SfListView.XForms">
  <syncfusion:SfListView x:Name="listView" 
                   ItemsSource="{Binding ToDoList}"
                   DragStartMode="OnDragIndicator"
                   BackgroundColor="#FFE8E8EC"
                   ItemSize="60">
  <syncfusion:SfListView.ItemTemplate>
    <DataTemplate>
      <Grid Padding="10">
          <Grid.ColumnDefinitions>
            <ColumnDefinition Width="*" />
            <ColumnDefinition Width="60" />
          </Grid.ColumnDefinitions>
          <Label x:Name="textLabel" Text="{Binding Name}" Grid.Column="1" FontSize="15" TextColor="#333333" />
          <syncfusion:DragIndicatorView Grid.Column="2" ListView="{x:Reference listView}" 
                    HorizontalOptions="Center" 
                    VerticalOptions="Center">
            <Grid Padding="10, 20, 20, 20">
              <Image Source="DragIndicator.png" />
            </Grid>
          </syncfusion:DragIndicatorView>
        </Grid>
      </Grid>
    </DataTemplate>
  </syncfusion:SfListView.ItemTemplate>
</syncfusion:SfListView>                
</ContentPage>
{% endhighlight %}
{% highlight c# %}
listView.ItemTemplate = new DataTemplate(() =>
{
  var grid = new Grid();
  var name = new Label
  {
    FontSize = 15,
    VerticalOptions = LayoutOptions.Center
  };
  name.SetBinding(Label.TextProperty, new Binding("Name"));

  var indicatorGrid = new Grid()
  {
    Padding = new Thickness(10, 20, 20, 20),
    HorizontalOptions = LayoutOptions.End,
    VerticalOptions = LayoutOptions.Center
  };
  var dragIndicatorView = new DragIndicatorView() { ListView = this.listView };
  var indicator = new Image() { Source = "DragIndicator.png" };

  indicatorGrid.Children.Add(indicator);
  dragIndicatorView.Content = indicatorGrid;

  grid.Children.Add(name);
  grid.Children.Add(dragIndicatorView, 1, 0);
  return grid;
});
{% endhighlight %}
{% endtabs %}

The screenshot shows the output of the reordering items by drag and drop. Download the entire source code from GitHub [here](https://github.com/SyncfusionExamples/Load-dar-view-indicator-in-xamarin.forms-listview).

![Item reordering by drag and drop](SfListView_images/SfListView-ItemReordering.gif)

## Drag item customization

By defining the [SfListView.DragItemTemplate](https://help.syncfusion.com/cr/xamarin/Syncfusion.ListView.XForms.SfListView.html#Syncfusion_ListView_XForms_SfListView_DragItemTemplate) of the SfListView, displays the custom User Interface(UI) when performing drag and drop operations. The template can be defined either in code or XAML.

N> If `BackgroundColor` is set to `DragItemTemplate` or [DragIndicatorView](https://help.syncfusion.com/cr/xamarin/Syncfusion.ListView.XForms.DragIndicatorView.html), set `InputTransparent` to true. Since, dragging does not happen when performing by `DragIndicatorView` in UWP.

{% tabs %}
{% highlight xaml %}
<ContentPage xmlns:syncfusion="clr-namespace:Syncfusion.ListView.XForms;assembly=Syncfusion.SfListView.XForms">
  <syncfusion:SfListView x:Name="listView" 
                   ItemsSource="{Binding ToDoList}"
                   DragStartMode="OnHold"
                   BackgroundColor="#FFE8E8EC"
                   ItemSize="60">
  <syncfusion:SfListView.DragItemTemplate>
    <DataTemplate>
      <Grid Padding="10">
        <Label x:Name="textLabel" Text="{Binding Name}" FontSize="15" />
      </Grid>
    </DataTemplate>
  </syncfusion:SfListView.DragItemTemplate>
</syncfusion:SfListView>                
</ContentPage>
{% endhighlight %}
{% highlight c# %}
listView.ItemTemplate = new DataTemplate(() => {
  var grid = new Grid();
  var name = new Label { FontSize = 15 };
  name.SetBinding(Label.TextProperty, new Binding("Name"));
  grid.Children.Add(name);
  return grid;
});
{% endhighlight %}
{% endtabs %}

## Event

The [ItemDragging](https://help.syncfusion.com/cr/xamarin/Syncfusion.ListView.XForms.SfListView.html) event is raised while dragging and dropping the item in the [SfListView](https://help.syncfusion.com/cr/xamarin/Syncfusion.ListView.XForms.SfListView.html). The [ItemDraggingEventArgs](https://help.syncfusion.com/cr/xamarin/Syncfusion.ListView.XForms.ItemDraggingEventArgs.html) has the following members which provides the information for the `ItemDragging` event:

 * [Action](https://help.syncfusion.com/cr/xamarin/Syncfusion.ListView.XForms.ItemDraggingEventArgs.html#Syncfusion_ListView_XForms_ItemDraggingEventArgs_Action): Returns the drag `Action` such as start, dragging, and drop.
 * [Bounds](https://help.syncfusion.com/cr/xamarin/Syncfusion.ListView.XForms.ItemDraggingEventArgs.html#Syncfusion_ListView_XForms_ItemDraggingEventArgs_Bounds): Return bounds of drag item when dragging and dropping.
 * [Handled](https://help.syncfusion.com/cr/xamarin/Syncfusion.ListView.XForms.ItemDraggingEventArgs.html#Syncfusion_ListView_XForms_ItemDraggingEventArgs_Handled): If this member is set to true, dragging can be handled. It is applicable only if `Action` is `Dragging`.
 * [ItemData](https://help.syncfusion.com/cr/xamarin/Syncfusion.ListView.XForms.ItemDraggingEventArgs.html#Syncfusion_ListView_XForms_ItemDraggingEventArgs_ItemData): Returns the underlying data of the dragging item. 
 * [NewIndex](https://help.syncfusion.com/cr/xamarin/Syncfusion.ListView.XForms.ItemDraggingEventArgs.html#Syncfusion_ListView_XForms_ItemDraggingEventArgs_NewIndex): Returns the item index of the [DataSource.DisplayItems](https://help.syncfusion.com/cr/xamarin/Syncfusion.DataSource.DisplayItems.html) where dragging item is going to be dropped.
 * [OldIndex](https://help.syncfusion.com/cr/xamarin/Syncfusion.ListView.XForms.ItemDraggingEventArgs.html#Syncfusion_ListView_XForms_ItemDraggingEventArgs_OldIndex): Returns the item index of the [DataSource.DisplayItems](https://help.syncfusion.com/cr/xamarin/Syncfusion.DataSource.DisplayItems.html) where dragging item started. The OldIndex and NewIndex will be same if `Action` is `Start`.
 * [Position](https://help.syncfusion.com/cr/xamarin/Syncfusion.ListView.XForms.ItemDraggingEventArgs.html#Syncfusion_ListView_XForms_ItemDraggingEventArgs_Position): Returns the touch position of the drag item from screen coordinates.

## Auto scroll options

### Auto scroll margin

To adjust auto scroll margin, set a value to the [ScrollMargin](https://help.syncfusion.com/cr/xamarin/Syncfusion.ListView.XForms.AutoScroller.html#Syncfusion_ListView_XForms_AutoScroller_ScrollMargin) property of [AutoScroller](https://help.syncfusion.com/cr/xamarin/Syncfusion.ListView.XForms.AutoScroller.html) to enable auto-scrolling while dragging. The default value is 15. Auto-scrolling will be enabled when reaching `ScrollMargin` from view bounds while dragging.

To disable auto-scrolling, set the value to `0` for `ScrollMargin`.

{% tabs %}
{% highlight c# %}
this.listView.AutoScroller.ScrollMargin = 20;
{% endhighlight %}
{% endtabs %}

### Auto scroll interval

To adjust auto-scroll interval while dragging, set the [Interval](https://help.syncfusion.com/cr/xamarin/Syncfusion.ListView.XForms.AutoScroller.html#Syncfusion_ListView_XForms_AutoScroller_Interval) property of [AutoScroller](https://help.syncfusion.com/cr/xamarin/Syncfusion.ListView.XForms.AutoScroller.html). The default value is 150 milliseconds.

{% tabs %}
{% highlight c# %}
this.listView.AutoScroller.Interval = new TimeSpan(0, 0, 0, 0, 200);
{% endhighlight %}
{% endtabs %}

### Disable outside scroll

To disable auto-scroll when dragging item moves outside the SfListView while dragging, set the [AllowOutsideScroll](https://help.syncfusion.com/cr/xamarin/Syncfusion.ListView.XForms.AutoScroller.html#Syncfusion_ListView_XForms_AutoScroller_AllowOutsideScroll) property of [AutoScroller](https://help.syncfusion.com/cr/xamarin/Syncfusion.ListView.XForms.AutoScroller.html) to true. The default value is true.

{% tabs %}
{% highlight c# %}
this.listView.AutoScroller.AllowOutsideScroll = false;
{% endhighlight %}
{% endtabs %}

## Disable dragging for particular item

To disable dragging for a particular item, handle the [ItemDragging](https://help.syncfusion.com/cr/xamarin/Syncfusion.ListView.XForms.SfListView.html) event based on the conditions of [Action](https://help.syncfusion.com/cr/xamarin/Syncfusion.ListView.XForms.ItemDraggingEventArgs.html#Syncfusion_ListView_XForms_ItemDraggingEventArgs_Action) event argument.

{% tabs %}
{% highlight c# %}
private void ListView_ItemDragging(object sender, ItemDraggingEventArgs e)
{
  // Disable the dragging for 4th item.
  if (e.Action == DragAction.Start && e.NewIndex == 3)
    e.Cancel = true;
}
{% endhighlight %}
{% endtabs %}

## Cancel dropping for the dragged item

To cancel dropping for the dragged item, handle the [ItemDragging](https://help.syncfusion.com/cr/xamarin/Syncfusion.ListView.XForms.SfListView.html) event based on the conditions of [Action](https://help.syncfusion.com/cr/xamarin/Syncfusion.ListView.XForms.ItemDraggingEventArgs.html#Syncfusion_ListView_XForms_ItemDraggingEventArgs_Action) event argument. 

{% tabs %}
{% highlight c# %}
using Syncfusion.ListView.XForms.Control.Helpers;
private void ListView_ItemDragging(object sender, ItemDraggingEventArgs e)
{
  // Cancel the dropping if drop the drag item into out of view.
  var listView = sender as ListView;
  var totalExtent = listView.GetVisualContainer().Bounds.Bottom;
  if (e.Action == DragAction.Drop && (e.Bounds.Y < -30 || e.Bounds.Bottom > totalExtent + 40))
    e.Cancel = true;
}
{% endhighlight %}
{% endtabs %}

## Reorder the underlying collection

The underlying collection can be reordered directly by setting the [UpdateSource](https://help.syncfusion.com/cr/xamarin/Syncfusion.ListView.XForms.DragDropController.html#Syncfusion_ListView_XForms_DragDropController_UpdateSource) property to `true`. The default value is `false`. 

{% tabs %}
{% highlight xaml %}
<ContentPage xmlns:syncfusion="clr-namespace:Syncfusion.ListView.XForms;assembly=Syncfusion.SfListView.XForms">
  <syncfusion:SfListView x:Name="listView" 
                   ItemsSource="{Binding ToDoList}"
                   DragStartMode="OnHold"
                   BackgroundColor="#FFE8E8EC"
                   ItemSize="60">
  <syncfusion:SfListView.DragDropController>
                <syncfusion:DragDropController
                    UpdateSource="True">
                </syncfusion:DragDropController>
   </syncfusion:SfListView.DragDropController>
</syncfusion:SfListView>                
</ContentPage>
{% endhighlight %}
{% highlight c# %}
this.listView.DragDropController.UpdateSource = true;
{% endhighlight %}
{% endtabs %}

We can able to update collection even when `UpdateSource` is `false`. Like, user can decide where dragged item should be dropped actually by handling the ItemDragging event with [DragAction.Drop](https://help.syncfusion.com/cr/xamarin/Syncfusion.ListView.XForms.DragAction.html).

{% tabs %}
{% highlight c# %}
private void ListView_ItemDragging(object sender, ItemDraggingEventArgs e)
{
   if (e.Action == DragAction.Drop)
      {
        ViewModel.ToDoList.MoveTo(1, 5);
      }
}
{% endhighlight %}
{% endtabs %}

N> Underlying collection will not be updated when any data operation like sorting or grouping is performed. The order will be maintained only in DisplayItems of data source. When drag and drop an item between groups, the value of the property in which grouping is performed is updated in data object. 

## Delete item when dropping in particular view

To delete the dragged item when dropping into a particular view, handle the [ItemDragging](https://help.syncfusion.com/cr/xamarin/Syncfusion.ListView.XForms.SfListView.html) event based on the conditions of [Action](https://help.syncfusion.com/cr/xamarin/Syncfusion.ListView.XForms.ItemDraggingEventArgs.html#Syncfusion_ListView_XForms_ItemDraggingEventArgs_Action) and `Bounds` event arguments. 

To delete the dragged item from the underlying collection when dropping into delete icon, follow the code example. It will enable or disable whenever drag started, and dropped by IsVisible property in ViewModel.

{% tabs %}
{% highlight xaml %}
<ContentPage xmlns:syncfusion="clr-namespace:Syncfusion.ListView.XForms;assembly=Syncfusion.SfListView.XForms">
<Grid>
  <Grid.RowDefinitions>
    <RowDefinition Height="Auto" />
    <RowDefinition Height="*" />
  </Grid.RowDefinitions>

  <Grid BackgroundColor="#2196F3">
    <Label Text="To Do Items" x:Name="headerLabel"  TextColor="White" FontAttributes="Bold" VerticalOptions="Center" HorizontalOptions="Center" />
    <StackLayout x:Name="stackLayout" IsVisible="{Binding IsVisible}" Orientation="Horizontal" VerticalOptions="Center" HorizontalOptions="Center">
      <Image Source="Delete.png" HeightRequest="30" WidthRequest="30" />
      <Label x:Name="deleteLabel" Text="Delete Item" FontAttributes="Bold" TextColor="White" />
    </StackLayout>
  </Grid>
  <syncfusion:SfListView x:Name="listView" Grid.Row="1"
                   ItemsSource="{Binding ToDoList}"
                   DragStartMode="OnHold"
                   BackgroundColor="#FFE8E8EC"
                   ItemSize="60" />
</Grid>            
</ContentPage>
{% endhighlight %}
{% highlight c# %}
public partial class MainPage : ContentPage
{
  public MainPage()
  {
    InitializeComponent();
    var grid = new Grid();
    grid.RowDefinitions.Add(new RowDefinition { Height = new GridLength(40) });
    grid.RowDefinitions.Add(new RowDefinition { Height = new GridLength(1, GridUnitType.Star) });
    var grid1 = new Grid();
    var headerLabel = new Label()
    {
      Text = "To Do Items"
    };
    var stackLayout = new StackLayout();
    stackLayout.SetBinding(StackLayout.IsVisibleProperty, new Binding("IsVisible"));
    var image = new Image() { Source = "Delete.png" };
    var deleteLabel = new Label() { Text = "DeleteItem" };
    stackLayout.Children.Add(image);
    stackLayout.Children.Add(deleteLabel);
    grid1.Children.Add(headerLabel);
    grid1.Children.Add(stackLayout);
    var listView = new SfListView()
    {
      DragStartMode = DragStartMode.OnHold,
      ItemSize = 60,
      SelectionMode = SelectionMode.None,
      BackgroundColor = Color.FromHex("#FFE8E8EC")
    };
    listView.SetBinding(ListView.ItemsSourceProperty, new Binding("ToDoList"));
    grid.Children.Add(grid1);
    grid.Children.Add(listView, 0, 1);
  }
}
{% endhighlight %}
{% endtabs %}

{% tabs %}
{% highlight c# %}
private async void ListView_ItemDragging(object sender, ItemDraggingEventArgs e)
{
  var viewModel = this.listView.BindingContext as ViewModel;

  if (e.Action == DragAction.Start)
  {
    viewModel.IsVisible = true;
    this.stackLayout.Opacity = 0.25;
  }

  if(e.Action == DragAction.Dragging)
  {
    var position = new Point(e.Position.X - this.listView.Bounds.X, e.Position.Y - this.listView.Bounds.Y);
    if (this.stackLayout.Bounds.Contains(position))
      this.deleteLabel.TextColor = Color.Red;
    else
      this.deleteLabel.TextColor = Color.White;
  }

  if(e.Action == DragAction.Drop)
  {
    var position = new Point(e.Position.X - this.listView.Bounds.X, e.Position.Y - this.listView.Bounds.Y);
    if (this.stackLayout.Bounds.Contains(position))
    {
      await Task.Delay(100);
      viewModel.ToDoList.Remove(e.ItemData as ToDoItem);
    }
    viewModel.IsVisible = false;
    this.deleteLabel.TextColor = Color.White;
    this.headerLabel.IsVisible = true;
  }
}
{% endhighlight %}
{% endtabs %}

Download the sample from GitHub [here](https://github.com/SyncfusionExamples/Delete-dragging-item-on-dropping-into-a-particular-view).

![Delete item while drop in listview](SfListView_images/SfListView-ItemReordering1.gif)

## Skip dragging item into another group

To skip dragging from one group to another group, handle the [ItemDragging](https://help.syncfusion.com/cr/xamarin/Syncfusion.ListView.XForms.SfListView.html) event based on the conditions of [Action](https://help.syncfusion.com/cr/xamarin/Syncfusion.ListView.XForms.ItemDraggingEventArgs.html#Syncfusion_ListView_XForms_ItemDraggingEventArgs_Action) and `Bounds` event arguments.

N> While auto-scrolling, dragging item cannot be skipped.

Skip the dragging item by bounds of dragging item, and bounds of current and next group item.

{% tabs %}
{% highlight c# %}
using Syncfusion.ListView.XForms.Control.Helpers;
private async void ListView_ItemDragging(object sender, ItemDraggingEventArgs e)
{
  if (e.Action == DragAction.Dragging)
  {
    var currentGroup = this.GetGroup(e.ItemData);
    var container = this.ListView.GetVisualContainer();
    var groupIndex = this.ListView.DataSource.Groups.IndexOf(currentGroup);
    var nextGroup = (groupIndex + 1 < this.ListView.DataSource.Groups.Count) ? this.ListView.DataSource.Groups[groupIndex + 1] : null;
    ListViewItem groupItem = null;
    ListViewItem nextGroupItem = null;

    foreach (ListViewItem item in container.Children)
    {
      if (item.BindingContext == null || !item.Visibility)
        continue;

      if (item.BindingContext.Equals(currentGroup))
        groupItem = item;

      if (nextGroup != null && item.BindingContext.Equals(nextGroup))
        nextGroupItem = item;
      }

      if (groupItem != null && e.Bounds.Y <= groupItem.Y + groupItem.Height || nextGroupItem != null && (e.Bounds.Y + e.Bounds.Height >= nextGroupItem.Y))
        e.Handled = true;
  }
}

private GroupResult GetGroup(object itemData)
{
  GroupResult itemGroup = null;

  foreach (var item in this.listView.DataSource.DisplayItems)
  {
    if (item is GroupResult)
      itemGroup = item as GroupResult;

    if (item == itemData)
      break;
  }
  return itemGroup;
}
{% endhighlight %}
{% endtabs %}

Download sample from GitHub [here](https://github.com/SyncfusionExamples/How-to-skip-dragging-an-item-from-one-group-to-another-group-in-xamarin-forms-sflistview)

## Drag and drop customization

### Adjust drag item axis

To adjust drag item coordinates (X and Y) while dragging, returns true from virtual method [CanAdjustDragItemAxis](https://help.syncfusion.com/cr/xamarin/Syncfusion.ListView.XForms.DragDropController.html#Syncfusion_ListView_XForms_DragDropController_CanAdjustDragItemAxis) of [DragDropController](https://help.syncfusion.com/cr/xamarin/Syncfusion.ListView.XForms.DragDropController.html). By default, Y coordinates can be adjusted if [SfListView.Orientation](https://help.syncfusion.com/cr/xamarin/Syncfusion.ListView.XForms.SfListView.html#Syncfusion_ListView_XForms_SfListView_Orientation) is `Vertical`, and X coordinates can be adjusted if `Orientation` is `Horizontal`.

{% tabs %}
{% highlight c# %}
this.listView.DragDropController = new DragDropControllerExt(this.listView);

public class DragDropControllerExt : DragDropController
{
  public DragDropControllerExt(SfListView listView) : base(listView)
  {

  }

  protected override bool CanAdjustDragItemAxis()
  {
    return true;
  }
}
{% endhighlight %}
{% endtabs %}

### Layout item on dragging

In the SfListView, layout the [ListViewItem](https://help.syncfusion.com/cr/xamarin/Syncfusion.ListView.XForms.ListViewItem.html) with different animations, and time on dragging by virtual method [OnLayoutItem](https://help.syncfusion.com/cr/xamarin/Syncfusion.ListView.XForms.DragDropController.html#Syncfusion_ListView_XForms_DragDropController_OnLayoutItem_Xamarin_Forms_View_Xamarin_Forms_Rectangle_).

{% tabs %}
{% highlight c# %}
this.listView.DragDropController = new DragDropControllerExt(this.listView);

public class DragDropControllerExt : DragDropController
{
  public DragDropControllerExt(SfListView listView) : base(listView)
  {

  }

  protected override Task<bool> OnLayoutItem(View element, Rectangle rect)
  {
    return element.LayoutTo(rect, 250, Easing.BounceIn);
  }
}
{% endhighlight %}
{% endtabs %}

## See also

[How to drag and drop an item from one to another listview in Xamarin.Forms](https://www.syncfusion.com/kb/11203/)                                                                                                                                                                                                                                                              
[How to show or hide the drag indicator like iOS listview](https://www.syncfusion.com/kb/9981/)                                                                                                                                                     
[How to retrieve the dragged item index in ViewModel command with the Prism framework in Xamarin.Forms ListView (SfListView)](https://www.syncfusion.com/kb/11371)                                                                                                                                                                                  
[How to show or hide drag indicator based on the DragStartMode in Xamarin.Forms ListView (SfListView)](https://www.syncfusion.com/kb/11425/)                                    
[How to get the dropped item group in Xamarin.Forms ListView (SfListView)](https://www.syncfusion.com/kb/11436)                                                                                                                                                                                                                         
[How to handle button action of ListView item when dragging in Xamarin.Forms (SfListView)](https://www.syncfusion.com/kb/11686/)
