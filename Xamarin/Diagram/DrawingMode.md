---
title: Drawing Mode in Xamarin Diagram control | Syncfusion
description: Learn here all about Drawing Mode support in Syncfusion Xamarin Diagram (SfDiagram) control and more.
platform: Xamarin
control: Diagram
documentation: ug
keywords: 
---
# Drawing Mode in Xamarin Diagram (SfDiagram)

Drawing mode is used to draw continuously on the diagram area for selected mode dynamically.

## Text node

This node has default annotation. TextNode mode will add continuous text node. The following code example illustrates how to enable TextNode mode.
{% tabs %}
{% highlight xml %}
<diagram:SfDiagram x:Name="diagram" DrawingMode="TextNode">
 </diagram:SfDiagram> 
{% endhighlight %}
{% highlight c# %}
diagram.DrawingMode = DrawingMode.TextNode;
{% endhighlight %}
{% endtabs %}

## Connector

Connector mode add continuous orthogonal connectors on the diagram area. In this mode, you can connect connectors in between Points, Nodes, or Ports. The following code example illustrates how to enable Connector mode.
{% tabs %}
{% highlight xml %}
<diagram:SfDiagram x:Name="diagram" DrawingMode="Connector">
 </diagram:SfDiagram>
{% endhighlight %}
{% highlight c# %}
diagram.DrawingMode = DrawingMode.Connector;
{% endhighlight %}
{% endtabs %}
![Drawing mode in Xamarin.Forms diagram](DrawingMode_images/DrawingMode.gif)

N> You can refer to our [Xamarin Diagram](https://www.syncfusion.com/xamarin-ui-controls/xamarin-diagram) feature tour page for its groundbreaking feature representations.You can also explore our [Xamarin Diagram example](https://github.com/syncfusion/xamarin-demos/tree/master/Forms/Diagram) to understand how to present and manipulate data.