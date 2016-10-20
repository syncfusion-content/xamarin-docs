---
layout: post
title: Indicator Color Model for Essential Xamarin.Forms Kanban
description: indicator color model
platform: xamarin
control: Kanban
documentation: ug
---

# Indicator color model

['ColorModel'](http://help.syncfusion.com/cr/cref_files/xamarin/sfkanban/Syncfusion.SfKanban.XForms~Syncfusion.SfKanban.XForms.SfKanban~ColorModel.html) is a collection of ['KanbanColorMapping'](http://help.syncfusion.com/cr/cref_files/xamarin/sfkanban/Syncfusion.SfKanban.XForms~Syncfusion.SfKanban.XForms.KanbanColorMapping.html) that are used to set the indicator color of Kanban cards. In the underlying data model, ColorKey (predefined property) values are set as the ['Key'](http://help.syncfusion.com/cr/cref_files/xamarin/sfkanban/Syncfusion.SfKanban.XForms~Syncfusion.SfKanban.XForms.KanbanColorMapping~Key.html) and ['Color'](http://help.syncfusion.com/cr/cref_files/xamarin/sfkanban/Syncfusion.SfKanban.XForms~Syncfusion.SfKanban.XForms.KanbanColorMapping~Color.html) are mapped to the corresponding Key values as shown in the below code sample.

{% highlight c# %}

List<KanbanColorMapping> colormodels = new List<KanbanColorMapping>();
colormodels.Add(new KanbanColorMapping("Green", Color.Green));
colormodels.Add(new KanbanColorMapping("Red", Color.Red));
colormodels.Add(new KanbanColorMapping("Aqua", Color.Aqua));
colormodels.Add(new KanbanColorMapping("Blue", Color.Blue));
kanban.ColorModel = colormodels;

{% endhighlight %} 


![](SfKanban_images/SfKanban_img1.png)
