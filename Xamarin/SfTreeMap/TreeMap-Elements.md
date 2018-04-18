---
layout: post
title: TreeMap-Elements
description: treemap elements
platform: xamarin
control: TreeMap
documentation: ug
---

# TreeMap Elements

TreeMap contains various elements such as,

* Legend
* Headers
* Labels

## Legend

You can set the color value of **leaf nodes** using `LegendSettings`. This legend is appropriate only for the **TreeMap** whose leaf nodes are colored using `rangeColorMapping`.

You can set `showLegend` property value to **“True”** to enable or disable legend visibility.

### TreeMap Legend

You can decide the size of the legend icons by setting `iconSize` property of the `LegendSettings` property avail in **TreeMap**.

### Label for Legend

You can customize the labels of the **legend item** using `legendLabel` property of `rangeColorMapping`. 

{% highlight c# %}
…

    LegendSettings legendSettings = new LegendSettings();
    legendSettings.ShowLegend= true;
    legendSettings.IconSize = new Size(15, 15);
    legendSettings.Size = new Size (350, 70);
    treeMap.LegendSettings= legendSettings;

{% endhighlight %}

![](/js/TreeMap/TreeMap-Elements_images/TreeMap-Elements_img1.png)



## Header

You can set headers for each level by setting the `showHeader` property of the each **TreeMap** levels. The `headerHeight` property helps to set the height of the header and Group path value determines the header value. 

{% highlight c# %}

    TreeMapFlatLevel level = new TreeMapFlatLevel() { HeaderStyle = new Syncfusion.SfTreeMap.XForms.Style() { Color= Device.OnPlatform(iOS: Color.Gray, Android: Color.Gray, WinPhone: Color.White) }, 
    GroupPath = "Continent", HeaderHeight = 20, GroupGap = 5, ShowHeader = true };      


{% endhighlight %}



![](/js/TreeMap/TreeMap-Elements_images/TreeMap-Elements_img2.png)

## Label

You can also set labels for the leaf nodes by setting the `showLabels` property as true. Group path value is displayed as a label for leaf nodes. 

{% highlight c# %}

    TreeMapFlatLevel level = new TreeMapFlatLevel() { HeaderStyle = new Syncfusion.SfTreeMap.XForms.Style() { Color= Device.OnPlatform(iOS: Color.Gray, Android: Color.Gray, WinPhone: Color.White) }, GroupPath = "Continent", HeaderHeight = 20, GroupGap = 5, ShowHeader = true ,ShowLabels=true};
    level.GroupBackground = Device.OnPlatform(iOS: Color.White, Android: Color.White, WinPhone: Color.Black);
 
{% endhighlight %}



![](/js/TreeMap/TreeMap-Elements_images/TreeMap-Elements_img3.png)

