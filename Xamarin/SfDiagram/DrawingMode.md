---
title: Adding drawing mode in Diagram control for Xamarin.Forms
description: Learn how to add drawing mode in diagram control.
platform: Xamarin
control: Diagram
documentation: ug
keywords: 
---
# DrawingMode
Drawing mode are used to draw continuously for selected mode on the diagram area, dynamically.

## Text node
Text node is a node, which has default annotation. This mode will add continuous text node. The following code example illustrates how to enable TextNode mode.
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
Connector mode will add continuous orthogonal connector in diagram area. In this mode we can connect connectors in between Points, Nodes or Ports. The following code example illustrates how to enable Connector mode.
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

