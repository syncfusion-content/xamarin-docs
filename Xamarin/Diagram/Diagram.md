---
title: Diagram control for Xamarin.Forms | Syncfusion
description: Briefs about diagram,stencil,page setting and diagram constraints in SfDiagram for Xamarin.Forms
platform: xamarin
control: SfDiagram
documentation: ug
keywords: 
---

# Diagram
Diagram control allows to create different types of diagrams such as flow charts, use case diagrams, workflow process diagrams, and more.

## Page settings
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

## Node template:
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

## Diagram constraints
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

## Diagram style settings		
It is easier to apply default rendering styles to all shapes, connectors, stencil symbol, and stencil header in a diagram. Pass the following arguments to diagram style setting constructor: 
 * DefaultNodeStyle argument: Defines the node style properties. 
 * DefaultConnectorStyle argument: Defines the connector style properties.
 * DefaultSymbolStyle argument: Defines the symbol style properties. 
 * DefaultHeaderStyle argument: Defines the header style properties. 
The following code shows how to define the diagram style settings for the diagram object.

{% tabs %}
{% highlight c# %}
// Diagram style settings 
Syncfusion.SfDiagram.XForms.Style NodeStyle = new Syncfusion.SfDiagram.XForms.Style() { Brush = new SolidBrush(Color.Blue), StrokeBrush = new SolidBrush(Color.Brown), StrokeWidth = 2, StrokeStyle = StrokeStyle.Dashed };
Syncfusion.SfDiagram.XForms.Style ConnectorStyle = new Syncfusion.SfDiagram.XForms.Style() { StrokeBrush = new SolidBrush(Color.DeepSkyBlue), StrokeWidth = 3.0f, StrokeStyle = StrokeStyle.Dotted };
SymbolStyle SymbolStyle = new SymbolStyle() { Width = 70, Height = 70, BorderThickness = 4, BorderBrush = Color.Gray }; HeaderStyle HeaderStyle = new HeaderStyle() { FontSize = 24, TextBrush = Color.White, Fill = Color.SteelBlue, FontStyle = FontStyle.Italic, HorizontalAlignment = HorizontalAlignment.Center };
DiagramStyleSettings diagramStyleSettings = new DiagramStyleSettings(NodeStyle, ConnectorStyle, SymbolStyle, HeaderStyle);
//Passing diagram style settings instance to SfDiagram constructor
SfDiagram diagram = new SfDiagram(diagramStyleSettings);
{% endhighlight %}
{% endtabs %}

## Zooming enhancement 
Supports customizing the zoom levels. You can set minimum zoom level value to 0.01f and maximum to ‘infinite’. 
{% tabs %}
{% highlight xml %}
<!-- Define the minimum and maximum zoom factor value -->
<control:SfDiagram x:Name="diagram"  MinimumZoomFactor="0.01" MaximumZoomFactor="5.00" />
{% endhighlight %}
{% endtabs %}
{% tabs %}
{% highlight c# %}
// Define the minimum and maximum zoom factor value 
  diagram.MinimumZoomFactor = 0.01f;
  diagram.MaximumZoomFactor = 5.00f;
{% endhighlight %}
{% endtabs %}

N> Diagram supports zooming with custom option in Xamarin.Forms.Android and Xamarin.Forms.iOS alone.

