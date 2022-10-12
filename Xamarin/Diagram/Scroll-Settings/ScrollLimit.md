---
layout: post
title: Scroll Limit in Xamarin Diagram control | Syncfusion
description: Learn here all about Scroll Limit support in Syncfusion Xamarin Diagram (SfDiagram) control, its elements and more.
platform: Xamarin.Forms
control: SfDiagram
documentation: ug
---

# Scroll Limit in Xamarin Diagram (SfDiagram)

The scroll limit allows you to define the scrollable region of the Diagram while pan on the page. The `ScrollLimit` property of scroll settings helps to limit the scrolling area. It includes the following options:

* Infinity: Allows you to scroll in all directions without any restriction.
* Diagram: Allows you to scroll within the Diagram content.
* Limited: Allows you to scroll within the specified area.

{% capture codesnippet1 %}
{% tabs %}
{% highlight xaml %}
<!--Initialize the Sfdiagram-->
<syncfusion:SfDiagram x:Name="diagram">
    <!--Initialize the scroll setting class with scroll limit-->
    <syncfusion:SfDiagram.ScrollSettings>
        <syncfusion:ScrollSettings ScrollLimit="DiagramContent"/>
    </syncfusion:SfDiagram.ScrollSettings>
</syncfusion:SfDiagram>
{% endhighlight %}
{% highlight C# %}
//Initialize the SfDiagram.
SfDiagram diagram = new SfDiagram();
//Initialize the scroll settings with scroll limit.
diagram.ScrollSettings = new ScrollSettings()
{
    ScrollLimit = ScrollLimit.DiagramContent,
};
{% endhighlight %}
{% endtabs %}
{% endcapture %}
{{ codesnippet1 | UnOrderList_Indent_Level_1 }}

## Scrollable area

You can restrict scrolling beyond any particular rectangle area by using the `ScrollableArea` property of ScrollSettings. To restrict scrolling beyond any custom region,you have to set the `ScrollLimit` to Limited. The default value is Rect.Empty.

{% tabs %}
{% highlight xaml %}
<!--Initialize the Sfdiagram-->
<syncfusion:SfDiagram x:Name="diagram">
    <!--Initialize the scroll setting class with scroll limit and scrollable area values-->
    <syncfusion:SfDiagram.ScrollSettings>
        <syncfusion:ScrollSettings ScrollLimit="Limited" ScrollableArea="0,0,1500,1500"/>
    </syncfusion:SfDiagram.ScrollSettings>
</syncfusion:SfDiagram>
{% endhighlight %}
{% highlight C# %}
//Initialize the SfDiagram.
SfDiagram diagram = new SfDiagram();
//Initialize the scroll settings with scroll limit and scrollabl area value.
diagram.ScrollSettings = new ScrollSettings()
{
    ScrollLimit = ScrollLimit.Limited,
    ScrollableArea = new Rect(0,0,1500,1500),
};
{% endhighlight %}
{% endtabs %}

| ScrollLimit | Output |
|---|---|
| Infinity |![ScrollLimit infinity](ScrollSettings_Images/ScrollLimit_Infinity.gif) |
| Diagram |![ScrollLimit Diagram](ScrollSettings_Images/ScrollLimit_DiagramContent.gif) |
| Limited <br> ScrollableArea = (0,0,1500,1500) | ![ScrollLimit Limited](ScrollSettings_Images/ScrollLimit_Limited.gif) |
