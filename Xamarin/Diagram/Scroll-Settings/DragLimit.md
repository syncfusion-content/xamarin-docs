---
layout: post
title: Drag Limit in Xamarin Diagram control | Syncfusion
description: Learn here all about Drag Limit support in Syncfusion Xamarin Diagram (SfDiagram) control, its elements and more.
platform: Xamarin.Forms
control: SfDiagram
documentation: ug
---

# Drag Limit in Xamarin Diagram (SfDiagram)

The drag limit allows you to define the dragging region of the Diagram while diagram objects are getting dragged. The `DragLimit` property of scroll settings class helps to limit the dragging area. It includes the following options:

* Infinity: Allows you to drag the diagram objects in all directions without any restriction.
* Diagram: Allows you to drag the diagram objects within the Diagram content.
* Limited: Allows you to drag the diagram objects within the specified area. The `EditableArea` property is used to specify the area that is allowed to dragging.

The default operation is `Infinity.`

{% tabs %}
{% highlight xaml %}
<!--Initialize the Sfdiagram-->
<syncfusion:SfDiagram x:Name="diagram">
    <!--Initialize the scroll setting class with drag limit value-->
    <syncfusion:SfDiagram.ScrollSettings>
        <syncfusion:ScrollSettings DragLimit="Limited" EditableArea="100,100,400,300"/>
    </syncfusion:SfDiagram.ScrollSettings>
</syncfusion:SfDiagram>
{% endhighlight %}
{% highlight C# %}
//Initialize the SfDiagram.
SfDiagram diagram = new SfDiagram();
//Initialize the scroll settings with drag limit and drag limit area.
diagram.ScrollSettings = new ScrollSettings()
{
    DragLimit = ScrollLimit.Limited,
    EditableArea = new Rect(100, 100, 400, 300),
};
{% endhighlight %}
{% endtabs %}

| DragLimit | Output |
|---|---|
| Infinity |![DragLimit infinity](ScrollSettings_Images/DragLimit_Infinity.gif) |
| Diagram |![DragLimit diagram](ScrollSettings_Images/DragLimit_DiagramContent.gif) |
| Limited <br> EditableArea = (100, 100, 400, 300) | ![DragLimit limited](ScrollSettings_Images/DragLimit_Limited.gif) |
