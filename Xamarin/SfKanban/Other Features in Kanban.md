---
layout: post
title: Other Features in Essential Xamarin.Forms Kanban
description: other features in kanban
platform: xamarin
control: Kanban
documentation: ug
---

# Other features in Kanban

['AllowDrag'](http://help.syncfusion.com/cr/cref_files/xamarin/sfkanban/Syncfusion.SfKanban.XForms~Syncfusion.SfKanban.XForms.KanbanColumn~AllowDrag.html) – It enable or disable the dragging cards in the corresponding Kanban column.

['AllowDrop'](http://help.syncfusion.com/cr/cref_files/xamarin/sfkanban/Syncfusion.SfKanban.XForms~Syncfusion.SfKanban.XForms.KanbanColumn~AllowDrop.html) – It used to enable or disable the Kanban column to drop the Kanban cards while dragging. 

{% tabs %}

{% highlight xaml %}

<kanban:SfKanban.Columns>

<kanban:KanbanColumn x:Name="column1" AllowDrop="false" AllowDrag="false" Title="To Do">

</kanban:KanbanColumn>

</kanban:SfKanban.Columns>

{% endhighlight %}

{% highlight c# %}

KanbanColumn column = new KanbanColumn();

column.AllowDrop = false;

column.AllowDrag = false;

kanban.Columns.Add(column);

{% endhighlight %} {% endtabs %}

Kanban Column Width – we can modify the default width of the kanban columns using ['ColumnWidth'](http://help.syncfusion.com/cr/cref_files/xamarin/sfkanban/Syncfusion.SfKanban.XForms~Syncfusion.SfKanban.XForms.SfKanban~ColumnWidth.html) property

{% tabs %}

{% highlight xaml %}

<kanban:SfKanban x:Name="kanban" ColumnWidth="100" ItemsSource="{Binding Cards}">

</kanban:SfKanban>

{% endhighlight %}

{% highlight c# %}

kanban.ColumnWidth = 200;

{% endhighlight %} 

{% endtabs %}

{% tabs %}

![](SfKanban_images/SfKanban_img2.png)

#Kanban Expand/Collapse Column 

Columns can be collapsed or expanded interactively using ['IsExpanded'](http://help.syncfusion.com/cr/cref_files/xamarin/sfkanban/Syncfusion.SfKanban.XForms~Syncfusion.SfKanban.XForms.KanbanColumn~IsExpanded.html) property. Also set card limits for columns using ['MaximumLimit'](http://help.syncfusion.com/cr/cref_files/xamarin/sfkanban/Syncfusion.SfKanban.XForms~Syncfusion.SfKanban.XForms.KanbanColumn~MaximumLimit.html), ['MinimumLimit'](http://help.syncfusion.com/cr/cref_files/xamarin/sfkanban/Syncfusion.SfKanban.XForms~Syncfusion.SfKanban.XForms.KanbanColumn~MinimumLimit.html) properties.

{% tabs %}

{% highlight xaml %}

<kanban:SfKanban.Columns>

<kanban:KanbanColumn x:Name="column1" Title="To Do" MinimumLimit="5" MaximumLimit="15" IsExpanded="false" >
</kanban:KanbanColumn>

<kanban:KanbanColumn x:Name="column2" Title="In Progress" IsExpanded="false" >
</kanban:KanbanColumn>

</kanban:SfKanban.Columns>

{% endhighlight %}

{% highlight c# %}

KanbanColumn column1 = new KanbanColumn();
column1.MinimumLimit = 5;
column1.MaximumLimit = 15;
column1.IsExpanded   = false;
KanbanColumn column2 = new KanbanColumn();
column2.IsExpanded   = false;
kanban.Columns.Add(column1);
kanban.Columns.Add(column2);

{% endhighlight %} {% endtabs %}

![](SfKanban_images/SfKanban_img3.png)

# Events

['itemTapped'](http://help.syncfusion.com/cr/cref_files/xamarin/sfkanban/Syncfusion.SfKanban.XForms~Syncfusion.SfKanban.XForms.SfKanban~ItemTapped_EV.html)

This event will be fired when we tap on the item.

['dragStart'](http://help.syncfusion.com/cr/cref_files/xamarin/sfkanban/Syncfusion.SfKanban.XForms~Syncfusion.SfKanban.XForms.SfKanban~DragStart_EV.html)
' 
This event will be fired when we start to drag a item.

['dragEnd'](http://help.syncfusion.com/cr/cref_files/xamarin/sfkanban/Syncfusion.SfKanban.XForms~Syncfusion.SfKanban.XForms.SfKanban~DragEnd_EV.html)

This event should be fired whenever dragging is cancelled in following cases,
Event can be cancelled. When this event is cancelled, item will not be dropped on to the target column.

['dragEnter'](http://help.syncfusion.com/cr/cref_files/xamarin/sfkanban/Syncfusion.SfKanban.XForms~Syncfusion.SfKanban.XForms.SfKanban~DragEnter_EV.html)

This event should be fired when a item enters a column. Event can be cancelled. When it is cancelled, DragOver events will not be fired for that target column at all and placeholder should not appear on further move over the same column.

['dragLeave'](http://help.syncfusion.com/cr/cref_files/xamarin/sfkanban/Syncfusion.SfKanban.XForms~Syncfusion.SfKanban.XForms.SfKanban~DragLeave_EV.html)

This event should be fired when the item leaves the column. So it means, this event should be preceded by DragStart or DragEnter events.

['dragOver'](http://help.syncfusion.com/cr/cref_files/xamarin/sfkanban/Syncfusion.SfKanban.XForms~Syncfusion.SfKanban.XForms.SfKanban~DragOver_EV.html)

This event will be fired when placeholder appears in new position or whenever placeholder position changes on further move within same column.  Usually this event will be called after DragStart or DragEnter events.

['columnsGenerated'](http://help.syncfusion.com/cr/cref_files/xamarin/sfkanban/Syncfusion.SfKanban.XForms~Syncfusion.SfKanban.XForms.SfKanban~ColumnsGenerated_EV.html)
 
This event will be fired when after the columns are auto-generated.  In this event, user can change the header text of the column.

![](SfKanban_images/SfKanban_img4.png)
