---
title: Node in Xamarin Diagram control | Syncfusion
description: Learn here all about Node support in Syncfusion Xamarin Diagram (SfDiagram) control, its elements and more.
platform: xamarin
control: SfDiagram
documentation: ug
keywords: 
---

# Node in Xamarin Diagram (SfDiagram)
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
Node node = new Node(){ Width = 120, Height = 80, OffsetX = 200, OffsetY = 200 };
//Initialize SfGraphics
SfGraphics graphics = new SfGraphics();
Pen pen = new Pen();
pen.StrokeBrush = new SolidBrush(Color.Red);
pen.StrokeWidth = 2;
SolidBrush brush = new SolidBrush(Color.Yellow);
brush.FillColor = Color.Yellow;
pen.Brush = brush;
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
<diagram:Node OffsetX="300" OffsetY="300" Width="60" Height="70" Template="{StaticResource template}" />
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
The Node Constraints allow you to enable or disable the following behaviors of Node.
•EnableDrag
•EnableResize
•EnableRotate
•EnableTextEditing
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

## RotateEnd
The ['RotateEndEvent'](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfDiagram.XForms.RotateEndEventArgs.html) will be triggered while rotating the node. The following code example explains how to create a RotateEndEvent trigger. 

{% tabs %}
{% highlight xml %}
<diagram:SfDiagram x:Name="diagram" VerticalOptions="FillAndExpand" RotateEnd="Diagram_RotateEnd" />
{% endhighlight %}

{% highlight c# %}
SfDiagram diagram = new SfDiagram();
diagram.RotateEnd += Diagram_RotateEnd; 
this.Content = diagram;

private void Diagram_RotateEnd(object sender, RotateEndEventArgs args)
{
    Node node = (Node)args.Item;
}
{% endhighlight %}
{% endtabs %}

## Node Style Customization
You can customize the appearance of a node by changing its fill color and border color. The following code explains how to customize the appearance of the node style.

{% tabs %}
{% highlight xml %}
<sfDiagram:SfDiagram  VerticalOptions="FillAndExpand" x:Name="diagram" >
    <sfDiagram:SfDiagram.Nodes>
        <sfDiagram:NodeCollection>
            <sfDiagram:Node Width="100" Height="100" OffsetX="200" OffsetY="200">
                <sfDiagram:Node.Style>
                    <sfDiagram:Style>
                        <sfDiagram:Style.Brush>
                            <sfDiagram:SolidBrush FillColor="Red" />
                        </sfDiagram:Style.Brush>
                        <sfDiagram:Style.StrokeBrush>
                            <sfDiagram:SolidBrush FillColor="Yellow" />
                        </sfDiagram:Style.StrokeBrush>
                    </sfDiagram:Style>
                </sfDiagram:Node.Style>
            </sfDiagram:Node>
        </sfDiagram:NodeCollection>
    </sfDiagram:SfDiagram.Nodes>
</sfDiagram:SfDiagram>
{% endhighlight %}

{% highlight c# %}
SfDiagram diagram = new SfDiagram();
Node node = new Node 
{ 
    Width = 100, 
    Height = 100, 
    OffsetX = 200, 
    OffsetY = 200,
    Style=new Syncfusion.SfDiagram.XForms.Style()
    {
        Brush=new SolidBrush(Color.Red),
        StrokeBrush=new SolidBrush(Color.Yellow)
    }
};
diagram.AddNode(node);
this.Content = diagram;

{% endhighlight %}
{% endtabs %} 

N> You can refer to our [Xamarin Diagram](https://www.syncfusion.com/xamarin-ui-controls/xamarin-diagram) feature tour page for its groundbreaking feature representations.You can also explore our [Xamarin Diagram example](https://github.com/syncfusion/xamarin-demos/tree/master/Forms/Diagram) to understand how to present and manipulate data.