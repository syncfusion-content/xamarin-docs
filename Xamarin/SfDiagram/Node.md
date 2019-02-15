---
title: Node in Xamarin.Forms Diagram control | Syncfusion
description: Briefs about node,customization of node and node constraints in SfDiagram for Xamarin.Forms
platform: xamarin
control: SfDiagram
documentation: ug
keywords: 
---

# Node
Nodes are graphical objects used to visually represent the geometrical information, process flow, internal business procedure or any other kind of data and it represents the functions of a complete system in regards to how it interacts with external entities.

## Create node
A Node can be created and added to the Diagram, either programmatically or interactively. Nodes are stacked on the Diagram area from bottom to top in the order they are added.
The following code snippet illustrates how to create the node.
{% tabs %}
{% highlight xml %}
<!--Initialize SfDiagram-->
<syncfusion:SfDiagram  x:Name="diagram">
    <!--Initialize NodeCollection-->
    <syncfusion:SfDiagram.Nodes>
        <syncfusion:NodeCollection>
            <!--Initialize Node-->
            <syncfusion:Node Width="100" Height="100" OffsetX="200" OffsetY="200">
            </syncfusion:Node>
        </syncfusion:NodeCollection>
    </syncfusion:SfDiagram.Nodes>
</syncfusion:SfDiagram>
{% endhighlight %}
{% highlight c# %}
//Initialize Node
Node n = new Node() { Width = 120, Height = 40, OffsetX = 300,OffsetY = 60, ShapeType = ShapeType.Ellipse };
//Adds the node to the SfDiagram
diagram.AddNode(n);
{% endhighlight %}
{% endtabs %}
![Create node in Xamarin.Forms diagram](Node_images/Node_img1.jpeg)

## Create a node with custom path/shape
Node can be created with different custom shapes and path using SfGraphics.
The following code snippet is used to create the Node with custom shape/path.
{% tabs %}
{% highlight c# %}
//Initialize Node
Node node = new Node();
//Initialize SfGraphics
SfGraphics graphics = new SfGraphics();
Pen pen = new Pen();
pen.StrokeBrush = new SolidBrush(Color.Red);
pen.StrokeWidth = 2;
SolidBrush brush = new SolidBrush(Color.Yellow);
brush.FillColor = Color.Yellow;
pen.Brush = brush2;
graphics.DrawRectangle(pen, new Rectangle(0, 0, 50, 50));
//Update the SfGraphics to the node
node.UpdateSfGraphics(graphics);
{% endhighlight %}
{% endtabs %}

## Accessing a node from the diagram instance
We can access the Node from the diagram instance using the following code snippet.
{% tabs %}
{% highlight c# %}
//Access the node from the diagram instance.
Node node = diagram.Nodes[0];
{% endhighlight %}
{% endtabs %}

## Remove a node
The following code snippet is used to remove the node from the diagram.
{% tabs %}
{% highlight c# %}
//Remove the node from the diagram.
Node node = new Node();
diagram.RemoveNode(node);
{% endhighlight %}
{% endtabs %}

## Customization:
We can Customize the entire node with our own customized design using Template property.
{% tabs %}
{% highlight xml %}
<!--Initialize the DataTemplate-->
<DataTemplate x:Key="template">
  <Grid WidthRequest="80" HeightRequest="80">
    <Image Source="diagram.png"/>
  </Grid>
</DataTemplate>
<!--Initialize node-->
<diagram:Node OffsetX="300" OffsetY="300" Width="60" Height="70" Template="{StaticResource template}" >
{% endhighlight %}
{% highlight c# %}
//Initialize the template
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
//Initialize node with template.
Node node = new Node() { Width = 120, Height = 40, OffsetX = 300, OffsetY = 60, Template = template};
{% endhighlight %}
{% endtabs %}

## Constraints
Node Constraints allow us to enable or disable the following behaviors of Node.
•Drag
•Resize
•Rotate
•AnnotationEditing
•IsLocked.
Example
The following code illustrates how to disable node dragging.
{% tabs %}
{% highlight xml %}
<!--Initialize the node with constraints-->
<syncfusion:Node OffsetX="300" OffsetY="60" Width="120" Height="40" ShapeType="Ellipse" EnableDrag=”False”>
{% endhighlight %}
{% highlight c# %}
//Initialize the node with constraints
Node node = new Node() {EnableDrag = false;, Width = 50, Height = 50, OffsetX = 100, OffsetY = 100};
{% endhighlight %}
{% endtabs %}
