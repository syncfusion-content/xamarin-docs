---
layout: post
title: Events for Essential Xamarin.Forms Kanban
description: Kanban Events
platform: xamarin
control: Kanban
documentation: ug
---

## Events

#ItemTapped

This event is triggered when we tap on the kanban item. The argument contains the following information.
[Column](http://help.syncfusion.com/cr/cref_files/xamarin/sfkanban/Syncfusion.SfKanban.XForms~Syncfusion.SfKanban.XForms.KanbanTappedEventArgs~Column.html)          - Used to get the column, where the tapped event occurs.
[Index](http://help.syncfusion.com/cr/cref_files/xamarin/sfkanban/Syncfusion.SfKanban.XForms~Syncfusion.SfKanban.XForms.KanbanTappedEventArgs~Index.html) 			- Used to get the index of the tapped item.
[Data](http://help.syncfusion.com/cr/cref_files/xamarin/sfkanban/Syncfusion.SfKanban.XForms~Syncfusion.SfKanban.XForms.KanbanTappedEventArgs~Data.html) 			- Used to get the model data of the tapped item.

#DragStart

This event is triggered when we start to drag card. The argument contains the following information.

[SourceColumn](http://help.syncfusion.com/cr/cref_files/xamarin/sfkanban/Syncfusion.SfKanban.XForms~Syncfusion.SfKanban.XForms.KanbanDragEventArgs~SourceColumn.html) 	- Used to get the column, where the drag event occurs
[Data](http://help.syncfusion.com/cr/cref_files/xamarin/sfkanban/Syncfusion.SfKanban.XForms~Syncfusion.SfKanban.XForms.KanbanDragEventArgs~Data.html)			- Used to get the model data of the captures item.
[SourceIndex](http://help.syncfusion.com/cr/cref_files/xamarin/sfkanban/Syncfusion.SfKanban.XForms~Syncfusion.SfKanban.XForms.KanbanDragEventArgs~SourceIndex.html)		- Used to get the index of the captured item.
[Cancel](http://help.syncfusion.com/cr/cref_files/xamarin/sfkanban/Syncfusion.SfKanban.XForms~Syncfusion.SfKanban.XForms.KanbanDragStartEventArgs~Cancel.html)			- Used to set the value indicating whether to continue the drag event.
[KeepItem](http://help.syncfusion.com/cr/cref_files/xamarin/sfkanban/Syncfusion.SfKanban.XForms~Syncfusion.SfKanban.XForms.KanbanDragStartEventArgs~KeepItem.html)		- Used to set the value indicating whether to keep the original item in the source column. The item will be removed from the source column only after the drag ended on other column.

#DragEnd  

This event is triggered when whenever dragging is cancelled. The argument contains the following information.

[SourceColumn](http://help.syncfusion.com/cr/cref_files/xamarin/sfkanban/Syncfusion.SfKanban.XForms~Syncfusion.SfKanban.XForms.KanbanDragEventArgs~SourceColumn.html) 	- Used to get the column, where the drag event occurs
[Data](http://help.syncfusion.com/cr/cref_files/xamarin/sfkanban/Syncfusion.SfKanban.XForms~Syncfusion.SfKanban.XForms.KanbanDragEventArgs~Data.html)			- Used to get the model data of the captures item.
[SourceIndex](http://help.syncfusion.com/cr/cref_files/xamarin/sfkanban/Syncfusion.SfKanban.XForms~Syncfusion.SfKanban.XForms.KanbanDragEventArgs~SourceIndex.html)		- Used to get the index of the captured item.
[TargetColumn](http://help.syncfusion.com/cr/cref_files/xamarin/sfkanban/Syncfusion.SfKanban.XForms~Syncfusion.SfKanban.XForms.KanbanDragEndEventArgs~TargetColumn.html)	- Used to get the target column upon which the item is dropped.
[TargetIndex](http://help.syncfusion.com/cr/cref_files/xamarin/sfkanban/Syncfusion.SfKanban.XForms~Syncfusion.SfKanban.XForms.KanbanDragEndEventArgs~TargetIndex.html)		- Used to get the index in the target column where the item is going to be inserted.
[Cancel](http://help.syncfusion.com/cr/cref_files/xamarin/sfkanban/Syncfusion.SfKanban.XForms~Syncfusion.SfKanban.XForms.KanbanDragEndEventArgs~Cancel.html)			- Used to set a value that determines whether to insert the item in the target column.
[TargetCategory](http://help.syncfusion.com/cr/cref_files/xamarin/sfkanban/Syncfusion.SfKanban.XForms~Syncfusion.SfKanban.XForms.KanbanDragEndEventArgs~TargetCategory.html) 	- Used to get the dropped category value.

N> When this event is cancelled, item will not be dropped on to the target column. 

#DragEnter  

This event is triggered when item enters a column. The argument contains the following information.

[SourceColumn](http://help.syncfusion.com/cr/cref_files/xamarin/sfkanban/Syncfusion.SfKanban.XForms~Syncfusion.SfKanban.XForms.KanbanDragEventArgs~SourceColumn.html) 		- Used to get the column, where the drag event occurs
[Data](http://help.syncfusion.com/cr/cref_files/xamarin/sfkanban/Syncfusion.SfKanban.XForms~Syncfusion.SfKanban.XForms.KanbanDragEventArgs~Data.html)				- Used to get the model data of the captures item.
[SourceIndex](http://help.syncfusion.com/cr/cref_files/xamarin/sfkanban/Syncfusion.SfKanban.XForms~Syncfusion.SfKanban.XForms.KanbanDragEventArgs~SourceIndex.html)			- Used to get the index of the captured item.
[TargetColumn](http://help.syncfusion.com/cr/cref_files/xamarin/sfkanban/Syncfusion.SfKanban.XForms~Syncfusion.SfKanban.XForms.KanbanDragEnterEventArgs~TargetColumn.html)		- Used to get the target column
[TargetIndex](http://help.syncfusion.com/cr/cref_files/xamarin/sfkanban/Syncfusion.SfKanban.XForms~Syncfusion.SfKanban.XForms.KanbanDragEnterEventArgs~TargetIndex.html)			- Used to get the target index of item.
[Cancel](http://help.syncfusion.com/cr/cref_files/xamarin/sfkanban/Syncfusion.SfKanban.XForms~Syncfusion.SfKanban.XForms.KanbanDragEnterEventArgs~Cancel.html)				- Used to get the value indicating whether to end the dragging.
[IsAboveMaximumLimit](http://help.syncfusion.com/cr/cref_files/xamarin/sfkanban/Syncfusion.SfKanban.XForms~Syncfusion.SfKanban.XForms.KanbanDragEnterEventArgs~IsAboveMaximumLimit.html)	- Used to set a value that indicates whether the number of items in the column exceeds the maximum allowed limit.

N> This event can be cancelled. When it is cancelled, ‘DragOver’ events will not be fired for that target column at all and placeholder should not appear on further move over the same column. 

#DragLeave 

This event is triggered when the item leaves the column. So it means, this event should be preceded by ‘DragStart’ or ‘DragEnter’ events. The argument contains the following information.

[SourceColumn](http://help.syncfusion.com/cr/cref_files/xamarin/sfkanban/Syncfusion.SfKanban.XForms~Syncfusion.SfKanban.XForms.KanbanDragEventArgs~SourceColumn.html)        - Used to get the column, where the drag event occurs
[Data](http://help.syncfusion.com/cr/cref_files/xamarin/sfkanban/Syncfusion.SfKanban.XForms~Syncfusion.SfKanban.XForms.KanbanDragEventArgs~Data.html)                - Used to get the model data of the captures item.
[SourceIndex](http://help.syncfusion.com/cr/cref_files/xamarin/sfkanban/Syncfusion.SfKanban.XForms~Syncfusion.SfKanban.XForms.KanbanDragEventArgs~SourceIndex.html)         - Used to get the index of the captured item.
[TargetColumn](http://help.syncfusion.com/cr/cref_files/xamarin/sfkanban/Syncfusion.SfKanban.XForms~Syncfusion.SfKanban.XForms.KanbanDragLeaveEventArgs~TargetColumn.html)		- Used to get the target column out of which the user drags the item.
[IsBelowMinimumLimit](http://help.syncfusion.com/cr/cref_files/xamarin/sfkanban/Syncfusion.SfKanban.XForms~Syncfusion.SfKanban.XForms.KanbanDragLeaveEventArgs~IsBelowMinimumLimit.html) - Used to set value that indicating whether the number of items in the column is less than the minimum allowed limit.

#DragOver

This event will be fired when placeholder appears in new position or whenever placeholder position changes on further move within same column. Usually this event will be called after ‘DragStart’ or ‘DragEnter’ events. The argument contains the following information.

[SourceColumn](http://help.syncfusion.com/cr/cref_files/xamarin/sfkanban/Syncfusion.SfKanban.XForms~Syncfusion.SfKanban.XForms.KanbanDragEventArgs~SourceColumn.html) 	- Used to get the column, where the drag event occurs
[Data](http://help.syncfusion.com/cr/cref_files/xamarin/sfkanban/Syncfusion.SfKanban.XForms~Syncfusion.SfKanban.XForms.KanbanDragEventArgs~Data.html)			- Used to get the model data of the captures item.
[SourceIndex](http://help.syncfusion.com/cr/cref_files/xamarin/sfkanban/Syncfusion.SfKanban.XForms~Syncfusion.SfKanban.XForms.KanbanDragEventArgs~SourceIndex.html)		- Used to get the index of the captured item.
[TargetColumn](http://help.syncfusion.com/cr/cref_files/xamarin/sfkanban/Syncfusion.SfKanban.XForms~Syncfusion.SfKanban.XForms.KanbanDragOverEventArgs~TargetColumn.html)	- Used to get the target column upon which the item is being dragged.
[TargetIndex](http://help.syncfusion.com/cr/cref_files/xamarin/sfkanban/Syncfusion.SfKanban.XForms~Syncfusion.SfKanban.XForms.KanbanDragOverEventArgs~TargetIndex.html)		- Used to get the target index of the item.
[Cancel](http://help.syncfusion.com/cr/cref_files/xamarin/sfkanban/Syncfusion.SfKanban.XForms~Syncfusion.SfKanban.XForms.KanbanDragOverEventArgs~Cancel.html)			- Used to set the value that indicating whether to show the item placeholder for the current target index.

#ColumnsGenerated 

This event will be fired after the columns are auto-generated. Using this event user can change the header text of the column. 
