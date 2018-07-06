---
title: Adding drawing mode in Diagram control for Xamarin.Forms
description: Learn how to add drawing mode in diagram control.
platform: Xamarin
control: Diagram
documentation: ug
keywords: 
---
# DrawingMode
Drawing mode is used to draw continuously on the diagram area for selected mode dynamically.

## Text node
This node has default annotation. TextNode mode will add continuous text node. The following code example illustrates how to enable TextNode mode.
{% tabs %}
{% highlight xml %}
<diagram:SfDiagram x:Name="diagram" DrawingMode="TextNode">
 </diagram:SfDiagram> 
{% endhighlight %}
{% endtabs %}

{% tabs %}
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
{% endtabs %}

{% tabs %}
{% highlight c# %}
diagram.DrawingMode = DrawingMode.Connector;
{% endhighlight %}
{% endtabs %}
![](DrawingMode_images/DrawingMode.gif)

