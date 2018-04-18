---
layout: post
title: Layout
description: layout
platform: xamarin
control: TreeMap
documentation: ug
---

# Layout

You can decide on the visual representation of nodes belonging to all the treemap levels using the `LayoutType` property of the TreeMap.

There are four different **TreeMap** layouts such as

* Squarified
* SliceAndDiceAuto
* SliceAndDiceHorizontal
* SliceAndDiceVertical

## Squarified

**Squarified** layout creates rectangles with best aspect ratio.

{% highlight C# %} 
      
        SfTreeMap tree = new SfTreeMap();
        tree.WeightValuePath = "Population";
        tree.ColorValuePath = "Growth";
        tree.DataSource = new PopulationViewModel ().PopulationDetails;      
        tree.LayoutType = LayoutTypes.Squarified;

{% endhighlight %}



![](/js/TreeMap/Layout_images/Layout_img1.png)

## SliceAndDiceAuto

**SliceAndDiceAuto** layout creates rectangles with high aspect ratio and displays them sorted both horizontally and vertically.

{% highlight C# %} 

    SfTreeMap tree = new SfTreeMap();
    tree.LayoutType = LayoutTypes.SliceAndDiceAuto;

{% endhighlight %}



![](/js/TreeMap/Layout_images/Layout_img2.png)

## SliceAndDiceHorizontal

**SliceAndDiceHorizontal** layout creates rectangles with high aspect ratio and displays them sorted horizontally.

{% highlight C# %} 

       SfTreeMap tree = new SfTreeMap();
       tree.LayoutType = LayoutTypes.SliceAndDiceHorizontal;

{% endhighlight %}



![](/js/TreeMap/Layout_images/Layout_img3.png)

## SliceAndDiceVertical

**SliceAndDiceVertical** layout creates rectangles with high aspect ratio and displays them sorted vertical.

{% highlight C# %} 

        SfTreeMap tree = new SfTreeMap();
        tree.LayoutType = LayoutTypes.SliceAndDiceVertical;


{% endhighlight %}



![](/js/TreeMap/Layout_images/Layout_img4.png)

