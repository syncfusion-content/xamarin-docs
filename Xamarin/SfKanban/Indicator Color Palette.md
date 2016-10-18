---
layout: post
title: Getting Started for Essential Xamarin.Forms Kanban
description: getting started kanban
platform: xamarin
control: Kanban
documentation: ug
---

# Indicator color model

Color Model is a collection of ColorMapping that are used to set the indicator color of Kanban cards. In the underlying data model, ColorKey (predefined property) values are set as the Key and Color are mapped to the corresponding Key values as shown in the below code sample.

{% highlight c# %}

List<KanbanColorMapping> colormodels = new List<KanbanColorMapping>();
colormodels.Add(new KanbanColorMapping("Green", Color.Green));
colormodels.Add(new KanbanColorMapping("Red", Color.Red));
colormodels.Add(new KanbanColorMapping("Aqua", Color.Aqua));
colormodels.Add(new KanbanColorMapping("Blue", Color.Blue));
kanban.ColorModel = colormodels;

{% endhighlight %} 


![](SfKanban_images/SfKanban_img1.png)
