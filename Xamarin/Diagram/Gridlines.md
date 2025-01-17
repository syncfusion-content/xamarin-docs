---
title: Gridlines in Xamarin Diagram control | Syncfusion&reg;
description: Learn here all about Gridlines support in Syncfusion&reg; Xamarin Diagram (SfDiagram) control, its elements and more.
platform: xamarin
control: Diagram
documentation: ug
keywords: 
---
# Gridlines in Xamarin Diagram (SfDiagram)
Gridlines are the pattern of lines drawn behind the diagram elements. It provides a visual guidance when dragging or arranging the node on the diagram surface.

## Gridlines visibility
The “ShowGrid” property in PageSettings will show or hide the gridlines. The following code example illustrates how to enable grid visibility.
{% tabs %}
{% highlight xml %}

<diagram:SfDiagram x:Name="diagram" > 
<diagram:SfDiagram.PageSettings> 
<diagram:PageSettings ShowGrid =“true”/> 
</diagram:SfDiagram.PageSettings> 
</diagram:SfDiagram>

{% endhighlight %}
{% highlight c# %}

diagram.PageSettings.ShowGrid = true;

{% endhighlight %}
{% endtabs %}

## Customizing gridlines
Grid cell size and gridline color can be modified using the “GridSize” and “GridColor” properties respectively. The following code example illustrates how to customize the grid.
{% tabs %}
{% highlight xml %}
<diagram:SfDiagram x:Name="diagram" > 
<diagram:SfDiagram.PageSettings> 
<diagram:PageSettings GridColor ="Pink” GridSize =“14”/> 
</diagram:SfDiagram.PageSettings> 
</diagram:SfDiagram>

{% endhighlight %}
{% highlight c# %}
diagram.PageSettings.GridColor = Color.Pink;
diagram.PageSettings.GridSize = 14;
{% endhighlight %}
{% endtabs %}

## Snapping gridlines
Nodes can be aligned and resized easily using gridlines by enabling the snap to grid. The following code example illustrates how to enable the snap to grid.
{% tabs %}
{% highlight xml %}
<diagram:SfDiagram x:Name="diagram" > 
<diagram:SfDiagram.PageSettings> 
<diagram:PageSettings SnapToGrid=”true”/> 
</diagram:SfDiagram.PageSettings> 
</diagram:SfDiagram>
{% endhighlight %}
{% highlight c# %}
diagram.PageSettings.SnapToGrid = true;
{% endhighlight %}
{% endtabs %}
![Snapping gridlines in Xamarin.Forms diagram](Gridlines_images/Gridlines.gif)

N> You can refer to our [Xamarin Diagram](https://www.syncfusion.com/xamarin-ui-controls/xamarin-diagram) feature tour page for its groundbreaking feature representations.You can also explore our [Xamarin Diagram example](https://github.com/syncfusion/xamarin-demos/tree/master/Forms/Diagram) to understand how to present and manipulate data.