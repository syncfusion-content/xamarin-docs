---
title: Adding drawing mode in Diagram control for Xamarin.Forms | Syncfusion
description: Describes how to add drawing mode in diagram control for Xamarin.Forms
platform: Xamarin
control: Diagram
documentation: ug
keywords: 
---
# Drawing mode
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

