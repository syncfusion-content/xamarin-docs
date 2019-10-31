---
layout: post
title: Workflows for Essential Xamarin.Forms Kanban
description: Kanban Workflows
platform: xamarin
control: Kanban
documentation: ug
---

# Workflows

This feature is used to define the flow of the card transitions from one state to another state. You need to create an instance of [`KanbanWorkflow`](http://help.syncfusion.com/cr/cref_files/xamarin/Syncfusion.SfKanban.XForms~Syncfusion.SfKanban.XForms.KanbanWorkflow.html) class and add it to [`SfKanban.Workflows`](http://help.syncfusion.com/cr/cref_files/xamarin/Syncfusion.SfKanban.XForms~Syncfusion.SfKanban.XForms.SfKanban~Workflows.html) property to define the workflow for each column.  The [`KanbanWorkflow`](http://help.syncfusion.com/cr/cref_files/xamarin/Syncfusion.SfKanban.XForms~Syncfusion.SfKanban.XForms.KanbanWorkflow.html) contains the following properties to define the source category and target categories.

* [`Category`](http://help.syncfusion.com/cr/cref_files/xamarin/Syncfusion.SfKanban.XForms~Syncfusion.SfKanban.XForms.KanbanWorkflow~Category.html)            - Used to define the source category/state.
* [`AllowedTransitions`](http://help.syncfusion.com/cr/cref_files/xamarin/Syncfusion.SfKanban.XForms~Syncfusion.SfKanban.XForms.KanbanWorkflow~AllowedTransitions.html)  - Used to define the list of categories/states, the card with the state specified in KanbanWorkflow.Category is allowed to transit.

The following code example describes the workflow functionality.

{% highlight C# %}

var workflows = new List<KanbanWorkflow>();

var openWorkflow = new KanbanWorkflow();  
openWorkflow.Category = "Open"; 
//Define the list of categories which accepts the cards from Open state.
openWorkflow.AllowedTransitions = new List<object> { "In Progress" }; 
workflows.Add(openWorkflow); 

var progressWorkflow = new KanbanWorkflow(); 
progressWorkflow.Category = "In Progress"; 
//Define the list of categories which accepts the cards from “In Progress” state.
progressWorkflow.AllowedTransitions = new List<object> { "Open", "Code Review", "Closed-No Code Changes" }; 
workflows.Add(progressWorkflow); 

kanban.Workflows = workflows;

{% endhighlight %}


In the below output, you can see the card which was picked from Open state is not allowed to drop on “Code Review” and "Done" state, because we have defined to move the card from Open to “In Progress” state only and not to any other states.


![](SfKanban_images/Workflows.png)
