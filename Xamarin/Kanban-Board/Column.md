---
layout: post
title: Column in Xamarin.Forms Kanban control
description: Kanban Column
platform: xamarin
control: Kanban
documentation: ug
---

# Column

## Customizing Column Size

By default, columns are sized smartly to arrange the default elements of the cards with better readability. However, you can define the minimum and maximum width for the columns in [`SfKanban`](http://help.syncfusion.com/cr/xamarin/Syncfusion.SfKanban.XForms.SfKanban.html) using [`SfKanban.MinimumColumnWidth`](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfKanban.XForms.SfKanban.html#Syncfusion_SfKanban_XForms_SfKanban_MinimumColumnWidth) and [`SfKanban.MaximumColumnWidth`](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfKanban.XForms.SfKanban.html#Syncfusion_SfKanban_XForms_SfKanban_MaximumColumnWidth) properties respectively. 

{% tabs %}

{% highlight xaml %}

<kanban:SfKanban MinimumColumnWidth ="300" MaximumColumnWidth ="340">
</kanban:SfKanban>

{% endhighlight %}

{% highlight C# %} 

kanban. MinimumColumnWidth = 300;
kanban. MaximumColumnWidth = 340;

{% endhighlight %}

{% endtabs %}


You can also define the exact column width using [`SfKanban.ColumnWidth`](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfKanban.XForms.SfKanban.html#Syncfusion_SfKanban_XForms_SfKanban_ColumnWidth) property.

{% tabs %}

{% highlight xaml %}

<kanban:SfKanban ColumnWidth ="250">
</kanban:SfKanban>

{% endhighlight %}

{% highlight C# %} 

kanban.ColumnWidth = 250;

{% endhighlight %}

{% endtabs %}

## Categorizing Columns

If [`ItemsSource`](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfKanban.XForms.SfKanban.html#Syncfusion_SfKanban_XForms_SfKanban_ItemsSource) contains custom objects, the path of the property which can be used to categorize the card should be explicitly defined using [`ColumnMappingPath`](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfKanban.XForms.SfKanban.html#Syncfusion_SfKanban_XForms_SfKanban_ColumnMappingPath) property. By default, [`SfKanban`](http://help.syncfusion.com/cr/xamarin/Syncfusion.SfKanban.XForms.SfKanban.html) will automatically categorize the items using [`KanbanModel.Category`](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfKanban.XForms.KanbanModel.html#Syncfusion_SfKanban_XForms_KanbanModel_Category) property.

{% tabs %}

{% highlight xaml %}

<kanban:SfKanban ColumnMappingPath="Group">
</kanban:SfKanban>

{% endhighlight %}

{% highlight C# %} 

kanban.ColumnMappingPath = "Group";

{% endhighlight %}

{% endtabs %}

### Multiple category for a column

More than one category can be mapped to a column by assigning multiple values to Categories collection of [`KanbanColumn`](http://help.syncfusion.com/cr/xamarin/Syncfusion.SfKanban.XForms.KanbanColumn.html). For e.g., you can map “In progress, Validate types under “In progress” column.

{% highlight C# %} 

progressColumn.Categories = new List<object>() { "In Progress", "Validated" };

{% endhighlight %}

![Multiple category support for a column in Xamarin.Forms Kanban](SfKanban_images/MultipleCategoryMapping.png)

## Headers

Header shows the category [`Title`](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfKanban.XForms.KanbanColumn.html#Syncfusion_SfKanban_XForms_KanbanColumn_Title), items count, min and max informations of a column. The UI of the header can be replaced entirely using [`SfKanban.HeaderTemplate`](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfKanban.XForms.SfKanban.html#Syncfusion_SfKanban_XForms_SfKanban_HeaderTemplate) property. The following code snippet and screenshot illustrates this.

{% tabs %}

{% highlight xaml %}

     <kanban:SfKanban.HeaderTemplate >
         <DataTemplate>
             <StackLayout WidthRequest="300" HeightRequest="40"  BackgroundColor="Silver">
                 <Label Margin="10" Text="{Binding Path=Title}" TextColor="Purple" HorizontalOptions="Start" />
             </StackLayout>
         </DataTemplate>
     </kanban:SfKanban.HeaderTemplate>

{% endhighlight %}

{% highlight C# %} 

var headerTemplate = new DataTemplate(() => {
    StackLayout root = new StackLayout() { 
        WidthRequest = 300, 
        HeightRequest = 40, 
        BackgroundColor = Color.Silver 
    };
    Label label = new Label();
    label.Margin = new Thickness(10); 
    label.SetBinding(Label.TextProperty, new Binding("Title") );
    label.TextColor = Color.Purple;
    label.HorizontalOptions = LayoutOptions.Start; 
    root.Children.Add(label);
    return root;
    });
kanban.HeaderTemplate = headerTemplate;

{% endhighlight %}

{% endtabs %}

The following output is displayed as a result of the above code example.

![Headers in Xamarin.Forms kanban](SfKanban_images/HeaderTemplate.png)

## Expand/Collapse Column

Columns can be expanded/collapsed by tapping the toggle button which is placed at top right corner of the Kanban header. [`KanbanColumn.IsExpanded`](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfKanban.XForms.KanbanColumn.html#Syncfusion_SfKanban_XForms_KanbanColumn_IsExpanded) ‘ property is used to programmatically expand/collapse the Kanban column. The following code example describes the above behavior.   

{% tabs %}

{% highlight xaml %}

<kanban:SfKanban.Columns>
    <kanban:KanbanColumn x:Name="column1" Title="To Do" IsExpanded="false" />
    <kanban:KanbanColumn x:Name="column2" Title="In Progress" IsExpanded="false" />
</kanban:SfKanban.Columns>

{% endhighlight %}

{% highlight C# %}

KanbanColumn column1 = new KanbanColumn();
column1.IsExpanded = false; 
KanbanColumn column2 = new KanbanColumn();
column2.IsExpanded = false;

kanban.Columns.Add(column1);
kanban.Columns.Add(column2);

{% endhighlight %}

{% endtabs %}

The following output is displayed as a result of the above code example.

![Expand and Collapse column support in Xamarin.Forms Kanban](SfKanban_images/ExpandColumn.png)


## Enable/Disable Drag & Drop 

You can enable and disable the drag and drop operation of the cards for particular column using [`KanbanColumn.AllowDrag`](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfKanban.XForms.KanbanColumn.html#Syncfusion_SfKanban_XForms_KanbanColumn_AllowDrag) and [`KanbanColumn.AllowDrop`](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfKanban.XForms.KanbanColumn.html#Syncfusion_SfKanban_XForms_KanbanColumn_AllowDrop) properties.

The following code is used to disable the drag operation from progress column.

{% tabs %}

{% highlight xaml %}

<kanban:SfKanban.Columns>
    <kanban:KanbanColumn AllowDrag="false"/>
</kanban:SfKanban.Columns>

{% endhighlight %}

{% highlight C# %}

KanbanColumn progressColumn = new KanbanColumn();
progressColumn.AllowDrag = false;

{% endhighlight %}

{% endtabs %}

The following code is used to disable the drop operation of the cards into the progress column.

{% tabs %}

{% highlight xaml %}

<kanban:SfKanban.Columns>
    <kanban:KanbanColumn AllowDrop="false"/>
</kanban:SfKanban.Columns>

{% endhighlight %}

{% highlight C# %}

KanbanColumn progressColumn = new KanbanColumn();
progressColumn.AllowDrop = false; 

{% endhighlight %}

{% endtabs %}

The following output demonstrates the above example code.
 
![DragAndDrop support in Xamarin.Forms Kanban](SfKanban_images/DragAndDrop.png)


## Items Count

[`ItemsCount`](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfKanban.XForms.KanbanColumn.html#Syncfusion_SfKanban_XForms_KanbanColumn_ItemsCount) property is used to get the total cards count in each column.

{% highlight C# %}

int count = todoColumn.ItemsCount;         

{% endhighlight %}


## Work In-Progress Limit

[`MinimumLimit`](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfKanban.XForms.KanbanColumn.html#Syncfusion_SfKanban_XForms_KanbanColumn_MinimumLimit) and [`MaximumLimit`](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfKanban.XForms.KanbanColumn.html#Syncfusion_SfKanban_XForms_KanbanColumn_MaximumLimit) properties are used to define the minimum and maximum number of items in a column. If the actual items count is exceeded or lesser than the specified limits, the error bars are used to indicate this violation. Following properties of [`ErrorbarSettings`](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfKanban.XForms.KanbanColumn.html#Syncfusion_SfKanban_XForms_KanbanColumn_ErrorbarSettings) are used to customize the appearance of error bar.

* [`Color`](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfKanban.XForms.KanbanErrorBarSettings.html#Syncfusion_SfKanban_XForms_KanbanErrorBarSettings_Color) - used to change the default color of the error bar.
* [`MaxValidationColor`](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfKanban.XForms.KanbanErrorBarSettings.html#Syncfusion_SfKanban_XForms_KanbanErrorBarSettings_MaxValidationColor) - used to change the maximum validation color of the error bar.
* [`MinValidationColor`](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfKanban.XForms.KanbanErrorBarSettings.html#Syncfusion_SfKanban_XForms_KanbanErrorBarSettings_MinValidationColor) - used to change the minimum validation color of the error bar.
* [`Height`](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfKanban.XForms.KanbanErrorBarSettings.html#Syncfusion_SfKanban_XForms_KanbanErrorBarSettings_Height) - used to change the height of the error bar.

{% tabs %}

{% highlight xaml %}

<kanban:KanbanColumn x:Name="todoColumn" Title="To Do" MinimumLimit="2" MaximumLimit="1">
</kanban:KanbanColumn>

{% endhighlight %}

{% highlight C# %}

todoColumn.MinimumLimit = 2; 
todoColumn.MaximumLimit = 1;   

{% endhighlight %}

{% endtabs %}



{% tabs %}

{% highlight xaml %}

<kanban:KanbanColumn x:Name="todoColumn" Title="To Do" MinimumLimit="3" MaximumLimit="5">
    <kanban:KanbanColumn.ErrorbarSettings>
        <kanban:KanbanErrorBarSettings Color="Green" MinValidationColor="Orange" MaxValidationColor="Red" Height="4"/>
    </kanban:KanbanColumn.ErrorbarSettings>
</kanban:KanbanColumn>

{% endhighlight %}

{% highlight C# %}

todoColumn.ErrorbarSettings.Color = Color.Green;
todoColumn.ErrorbarSettings.MinValidationColor = Color.Orange;
todoColumn.ErrorbarSettings.MaxValidationColor = Color.Red;
todoColumn.ErrorbarSettings.Height = 4;

{% endhighlight %}

{% endtabs %}

![Work in progress limit for column in Xamarin.Forms Kanban](SfKanban_images/ErrorbarSettings.png)


