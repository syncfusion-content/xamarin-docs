---
title: Diagram for Essential Xamarin.Forms Diagram
description: diagram
platform: xamarin
control: SfDiagram
documentation: ug
keywords: 
---

# Diagram
Diagram control allows to create different types of diagrams such as flow charts, use case diagrams, workflow process diagrams, and more.

## PageSettings
Page settings enable to customize the appearance, width, and height of the Diagram page. The size and appearance of the Diagram pages can be customized with the PageSettings property.
The PageWidth and PageHeight properties of page settings define the size of the page. You can also customize the appearance of off-page regions with the property BackgroundColor.
The following code illustrates how to customize the page size and the appearance of page and off-page.
{% tabs %}
{% highlight xml %}
<diagram:SfDiagram x:Name="diagram" BackgroundColor="Lime"> 
<diagram:SfDiagram.PageSettings> 
<diagram:PageSettings PageWidth="500" PageHeight="50” PageBackGround="White" /> 
</diagram:SfDiagram.PageSettings> 
</diagram:SfDiagram>
{% endhighlight %}
{% highlight c# %}
//Sets Page background 
diagram.BackgroundColor = Color.Lime; 
//Sets Page size 
diagram.PageSettings.PageWidth = 500; 
diagram.PageSettings.PageHeight = 500; 
//Customizes the appearance of Page
diagram.PageSettings.PageBackGround= Color.White;
{% endhighlight %}
{% endtabs %}

## Stencil:
Stencil has a collection of Symbols. Stencil is used to clone the desired symbol by dragging it from the Stencil and dropping it into the SfDiagram.
The following code snippet illustrates to add the stencil.
{% tabs %}
{% highlight xml %}
<syncfusion:Stencil x:Name="stencil" >
</syncfsion:Stencil>

{% endhighlight %}
{% highlight c# %}
Stencil stencil = new Stencil(); 
this.Content = stencil;

{% endhighlight %}
{% endtabs %}

## NodeTemplate:
You can replace the entire node template with your own design using SfDiagram.NodeTemplate property.
The following code snippet and screenshot illustrates this.
{% tabs %}
{% highlight xml %}
<DataTemplate x:Key="template">
  <Grid WidthRequest="80" HeightRequest="80">
    <Image Source="diagram.png"/>
  </Grid>
</DataTemplate>
<control:SfDiagram x:Name="diagram" NodeTemplate="{StaticResource template}">
{% endhighlight %}
{% highlight c# %}
var template = new DataTemplate(() =>
{
    Grid grid = new Grid();
    grid.WidthRequest = 80;
    grid.HeightRequest = 80;
    Image image = new Image();
    image.Source = "employee.png";
    grid.Children.Add(image);
    return grid;
});
diagram.NodeTemplate = template;
{% endhighlight %}
{% endtabs %}

## Diagram Constraints
The constraints property of Diagram allows you to enable/disable certain features.
Diagram Constraints allow to enable or disable the following behaviors of Node.
Drag
Resize
Rotate
AnnotationEditing
EnableSelectors
EnableZoomAndPan
IsReadOnly
**Example**
The following code illustrates how to disable the item dragging.
{% tabs %}
{% highlight xml %}
<synfusion:SfDiagram x:Name="diagram" EnableDrag="False">
</syncfusion:SfDiagram>
{% endhighlight %}
{% highlight c# %}
SfDiagram diagram = new SfDiagram(); 
// Disable the item dragging
diagram.EnableDrag = false;
this.Content = diagram;
{% endhighlight %}
{% endtabs %}
