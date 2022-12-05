---
layout: post
title: Shape annotations in Xamarin Pdf Viewer control | Syncfusion
description: Learn here all about Shape annotations support in Syncfusion Xamarin Pdf Viewer (SfPdfViewer) control and more.
platform: Xamarin
control: SfPdfViewer
documentation: ug
---

# Shape annotations in Xamarin Pdf Viewer (SfPdfViewer)

[Xamarin PDF Viewer](https://www.syncfusion.com/xamarin-ui-controls/xamarin-pdf-viewer) allows you to include shape annotations in a PDF document and provides options to modify or remove the existing shape annotations. The supported shape annotations are:

1. Rectangle
2. Circle
3. Line
4. Arrow
5. Polygon
6. Cloud
7. Polyline

In all the code snippets, Rectangle shape annotation is used for illustration purpose.

## Adding shape annotations using toolbar

### Enabling shape annotation mode

Set the `AnnotationMode` property of the PDF viewer to `Rectangle`. After setting the annotation mode to any of the shapes, the zooming, panning, and scrolling options will be disabled. The shapes can be drawn only on the currently visible page area. Refer to the following code.

{% tabs %}
{% highlight xaml %}

<syncfusion:SfPdfViewer x:Name="pdfViewer"/>
<Button x:Name="shapeAnnotationButton" Command="{Binding AnnotationModeCommand, Source={x:Reference Name=pdfViewer}}" CommandParameter="Rectangle" />

{% endhighlight %}

{% highlight c# %}

SfPdfViewer pdfViewer = new SfPdfViewer();
pdfViewer.AnnotationMode = AnnotationMode.Rectangle;

{% endhighlight %}
{% endtabs %}

### Disabling shape annotation mode

Setting the `AnnotationMode` to `None` disables the shape annotation mode. When the annotation mode is reset, the zooming, panning, and scrolling will be enabled again.

{% tabs %}
{% highlight xaml %}

<syncfusion:SfPdfViewer x:Name="pdfViewer"/>
<Button x:Name="resetAnnotationButton" Command="{Binding AnnotationModeCommand, Source={x:Reference Name=pdfViewer}}" CommandParameter="None" />

{% endhighlight %}
{% highlight c# %}

SfPdfViewer pdfViewer = new SfPdfViewer();
pdfViewer.AnnotationMode = AnnotationMode.None;

{% endhighlight %}
{% endtabs %}

### Detecting the inclusion shape annotations

The event `ShapeAnnotationAdded` will be raised when shape annotations are added to the PDF. 

{% tabs %}
{% highlight xaml %}

<syncfusion:SfPdfViewer x:Name="pdfViewer" ShapeAnnotationAdded="PdfViewer_ShapeAnnotationAdded"/>

{% endhighlight %}

{% highlight c# %}

SfPdfViewer pdfViewer = new SfPdfViewer();
pdfViewer.ShapeAnnotationAdded += PdfViewer_ShapeAnnotationAdded;

{% endhighlight %}
{% endtabs %}

## Adding the shape annotations programmatically 

By `AddAnnotation` method, You can add the shape annotations programmatically. The created shape annotation object passed as a parameter. The `ShapeAnnotation` instance acquires the `ShapeAnnotationType`, page number and bounds as the parameters. 

The following code sample illustrates the adding of rectangle annotation programmatically. 

{% tabs %}
{% highlight c# %}

//Bounds in which the rectangle shape annotation should be added
Rectangle bounds = new Rectangle(100, 100, 200, 200);
//Creates a new rectangle shape annotation
ShapeAnnotation shapeAnnotation = new ShapeAnnotation(ShapeAnnotationType.Rectangle, 1, rectangle);         
//Sets the stroke color for the rectangle shape annotation 
shapeAnnotation.Settings.StrokeColor = Color.Red;
//Add the rectangle shape annotation to the specified page
pdfViewer.AddAnnotation(shapeAnnotation);

{% endhighlight %}
{% endtabs %}

N> For the purpose of illustration, we have only provided the code example for adding rectangle annotation. But the same procedure can be followed for adding other shape annotations too.

## How to draw a cloud shape annotation?

To draw a cloud shape annotation, you should set the `BorderEffect` property of the shape annotation settings to `BorderEffect.Cloudy`. Only the rectangle and polygon annotations can be drawn with cloud border style. The following sample code illustrates how to draw a rectangle annotation with the cloud border style.

{% tabs %}
{% highlight c# %}

SfPdfViewer pdfViewer = new SfPdfViewer();
pdfViewer.AnnotationMode = AnnotationMode.Rectangle;
pdfViewer.AnnotationSettings.Rectangle.Settings.BorderEffect = BorderEffect.Cloudy;

{% endhighlight %}
{% endtabs %}

N> The value of `BorderEffect` property will does not affect other shape annotations such as circle, line, and arrow annotations. For complex cloud polygons, the cloud border-style appearance might differ from other PDF readers like Adobe.

## Detecting tap on shape annotations

Tapping a shape annotation selects it or deselects it if it is already selected. The event `ShapeAnnotationTapped` is raised when a shape is tapped.

{% tabs %}
{% highlight xaml %}

<syncfusion:SfPdfViewer x:Name="pdfViewer" ShapeAnnotationTapped="PdfViewer_ShapeAnnotationTapped"/>

{% endhighlight %}

{% highlight c# %}

SfPdfViewer pdfViewer = new SfPdfViewer();
pdfViewer.ShapeAnnotationTapped += PdfViewer_ShapeAnnotationTapped;

{% endhighlight %}
{% endtabs %}

## Selecting shape annotations

You can select a shape annotation by tapping on it, this action is followed by the appearance of the selector around the selected annotation. When a shape is selected, the `ShapeAnnotationSelected` event will be raised.

The properties of the selected shape annotation can be obtained from the `args` parameter of the event handler. 

{% tabs %}
{% highlight c# %}

private void PdfViewer_ShapeAnnotationSelected(object sender, ShapeAnnotationSelectedEventArgs args)
{
	//Get the type of the annotation. Here it is rectangle
	AnnotationMode annotationMode = args.AnnotationType;
	//Get the bounds of the rectangle
	Rectangle bounds = args.Bounds;
	//Get the page number in which the annotations are present
	int pageNumber = args.PageNumber;
}

{% endhighlight %}
{% endtabs %}

### Selecting shape annotation programmatically

By `SelectAnnotation` method, You can select the shape annotation programmatically. The specified shape annotation object passed as a parameter.

The following code sample illustrates the same.

{% tabs %}
{% highlight c# %}

//Selects the specified shape annotation
pdfViewer.SelectAnnotation(shapeAnnotation);

{% endhighlight %}
{% endtabs %}

N> Once `SelectAnnotation` method is called and as long as the annotation stays selected, the `SelectedAnnotation` property will return the same instance as the parameter of this method.

## Deselecting shape annotations

You can deselect a selected shape annotation by tapping on it or somewhere else on the PDF page. Deselection can be detected using the `ShapeAnnotationDeselected` event.

{% tabs %}
{% highlight xaml %}

<syncfusion:SfPdfViewer x:Name="pdfViewer" ShapeAnnotationDeselected="PdfViewer_ShapeAnnotationDeselected"/>

{% endhighlight %}
{% highlight c# %}

SfPdfViewer pdfViewer = new SfPdfViewer();
pdfViewer.ShapeAnnotationDeselected += PdfViewer_ShapeAnnotationDeselected;

{% endhighlight %}
{% endtabs %}

### Deselecting shape annotation programmatically

By `DeselectAnnotation` method, You can deselect the shape annotation programmatically. The specified shape annotation object passed as a parameter. 

The following code sample illustrates the same.

{% tabs %}
{% highlight c# %}

//Deselects the specified shape annotation
pdfViewer.DeselectAnnotation(shapeAnnotation);

{% endhighlight %}
{% endtabs %}

N> Calling `DeselectAnnotation` method has no effect if the given annotation is not selected. The `SelectedAnnotation` property will return null until any other annotation gets selected.

## Customizing the appearance of shape annotations

You can customize the default values of stroke color, opacity, and thickness of all shape annotations to be added. This will not affect the already added shape annotations. The appearance of a selected free text can also be modified.

### Setting the default stroke color

You can set the default stroke color of the shape annotations by using the `SfPdfViewer.AnnotationSettings.Rectangle.Settings.StrokeColor` property. Refer to the following code. 
 
{% highlight c# %}

SfPdfViewer pdfViewer = new SfPdfViewer();
pdfViewer.AnnotationSettings.Rectangle.Settings.StrokeColor = Color.Red;

{% endhighlight %}

### Setting the default opacity

You can set the default opacity of the shape annotations by using the `SfPdfViewer.AnnotationSettings.Rectangle.Settings.Opacity` property. Opacity value ranges from 0 to 1. Refer to the following code example.

{% highlight c# %}

SfPdfViewer pdfViewer = new SfPdfViewer();
pdfViewer.AnnotationSettings.Rectangle.Settings.Opacity = 0.5f; 

{% endhighlight %}

### Setting the default thickness

You can set the thickness of the shape annotations by using the `SfPdfViewer.AnnotationSettings.Rectangle.Settings.Thickness` property. Refer to the following code example. 

{% highlight c# %}

SfPdfViewer pdfViewer = new SfPdfViewer();
pdfViewer.AnnotationSettings.Rectangle.Settings.Thickness = 5;

{% endhighlight %}

### Setting the default minimum size and minimum length

By the `MinimumSize` property, You can set the minimum size to which the rectangle and circle shape annotations could be resized. 

By the `MinimumLength` property, You can set the minimum length to which the annotations could be resized for line and arrow.

Refer the following code example:

{% tabs %}
{% highlight c# %}

//Sets the minimum size for the rectangle annotations
pdfViewer.AnnotationSettings.Rectangle.Settings.MinimumSize = new Size(10, 10);
//Sets the minimum size for the circle annotations
pdfViewer.AnnotationSettings.Circle.Settings.MinimumSize = new Size(10, 10);
//Sets the minimum length for the line annotations
pdfViewer.AnnotationSettings.Line.Settings.MinimumLength = 10;
//Sets the minimum length for the arrow annotations
pdfViewer.AnnotationSettings.Arrow.Settings.MinimumLength = 10;

{% endhighlight %}
{% endtabs %}

N> The value of `MinimumSize` property will does not affect line, arrow, polyline and polygon annotations. Also, the value of `MinimumLength` property will does not affect rectangle, circle, polyline and polygon annotations.

### Setting the default border style

You can set the border style for the rectangle and polygon annotations using the `BorderEffect` property.  

Refer the following code example:

{% tabs %}
{% highlight c# %}

//Sets the cloud border style for rectangle annotation
pdfViewer.AnnotationSettings.Rectangle.Settings.BorderEffect = BorderEffect.Cloudy;
//Sets the cloud border style for polygon annotation 
pdfViewer.AnnotationSettings.Polygon.Settings.BorderEffect = BorderEffect.Cloudy;

{% endhighlight %}
{% endtabs %}

N> The value of `BorderEffect` property will does not affect other shape annotations such as circle, line, and arrow annotations. 

### Changing the properties of a selected shape

You can change the properties of the selected annotation by casting the `sender` parameter of the `ShapeAnnotationSelected` event handler to `ShapeAnnotation` and modifying its properties. The following code shows how to change the properties.

{% tabs %}
{% highlight xaml %}

<syncfusion:SfPdfViewer x:Name="pdfViewer" ShapeAnnotationSelected="PdfViewer_ShapeAnnotationSelected" />

{% endhighlight %}

{% highlight c# %}

SfPdfViewer pdfViewer = new SfPdfViewer();
pdfViewer.ShapeAnnotationSelected += PdfViewer_ShapeAnnotationSelected;

{% endhighlight %}
{% endtabs %}

{% tabs %}
{% highlight c# %}

private void PdfViewer_ShapeAnnotationSelected(object sender, Syncfusion.SfPdfViewer.XForms.ShapeAnnotationSelectedEventArgs args)
{
	//Get the type of the annotation. Here it is Rectangle
	AnnotationMode annotationMode = args.AnnotationType;
	//Cast the sender object as shape annotation.
	ShapeAnnotation selectedShapeAnnotation = sender as ShapeAnnotation;
	//Set the stroke color of the selected annotation using shape annotation settings.
	selectedShapeAnnotation.Settings.StrokeColor = Color.Blue;
	//Set the opacity of the selected annotation using shape annotation settings.
	selectedShapeAnnotation.Settings.Opacity = 0.3f;
	//Set the thickness of the selected annotation using shape annotation settings.
	selectedShapeAnnotation.Settings.Thickness = 3;
}

{% endhighlight %}
{% endtabs %}

## Moving or resizing shape annotations

Select the shape annotation to move or resize it. After the selector appears around the annotation, dragging the annotation by tapping anywhere inside the selector will move the annotation. Similarly, tapping and dragging on the corner bubbles will resize the selected annotation. 

### Detecting the move or resize of a shape

The event `AnnotationMovedOrResized` will be raised when you move or resize the selected annotation.

{% tabs %}
{% highlight xaml %}

<syncfusion:SfPdfViewer x:Name="pdfViewer" AnnotationMovedOrResized="PdfViewer_AnnotationMovedOrResized"/>

{% endhighlight %}

{% highlight c# %}

SfPdfViewer pdfViewer = new SfPdfViewer();
pdfViewer.AnnotationMovedOrResized += PdfViewer_AnnotationMovedOrResized;

{% endhighlight %}
{% endtabs %}

{% tabs %}
{% highlight c# %}

private void PdfViewer_AnnotationMovedOrResized(object sender, AnnotationMovedOrResizedEventArgs args) 
{
	//Determine whether the moved or resized annotation is a shape or some other annotation. 
	if(sender as ShapeAnnotation == null)
	{
		//The annotation is not a shape
	}
	else
	{
		//The annotation is a shape
	} 
	//Retrieve the old bounds of the annotation
	Rectangle oldBounds = args.OldBounds;
	//Retrieve the new bounds of the annotation
	Rectangle newBounds = args.NewBounds;
}

{% endhighlight %}
{% endtabs %}

## Deleting shape annotations

The PDF viewer supports removing a single annotation and all the annotations in the PDF document.

### Removing a selected annotation

The following code snippet illustrates removing a selected annotation from the PDF document.

{% tabs %}
{% highlight xaml %}

<syncfusion:SfPdfViewer x:Name="pdfViewer" ShapeAnnotationSelected="PdfViewer_ShapeAnnotationSelected"/>
<Button x:Name="deleteShapeAnnotationButton" Grid.Row="1" Clicked="deleteShapeAnnotationButton_Clicked"/>

{% endhighlight %}
{% highlight c# %}

ShapeAnnotation selectedShapeAnnotation;
private void PdfViewer_ShapeAnnotationSelected(object sender, ShapeAnnotationSelectedEventArgs args)
{
	//Cast the sender object as Shape annotation.
	selectedShapeAnnotation = sender as ShapeAnnotation;
}
private void deleteShapeAnnotationButton_Clicked(object sender, EventArgs e)
{
	//Delete the selected shape annotation
	pdfViewer.RemoveAnnotation(selectedShapeAnnotation);
}

{% endhighlight %}
{% endtabs %}

### Removing all annotations

The following code snippet illustrates removing all annotations from the PDF.

{% tabs %}
{% highlight c# %}

pdfViewer.ClearAllAnnotations();

{% endhighlight %}
{% endtabs %}

### Detecting the removal of a shape

The event `ShapeAnnotationRemoved` will be raised when a shape annotation is removed from the PDF.

{% tabs %}
{% highlight xaml %}

<syncfusion:SfPdfViewer x:Name="pdfViewer" ShapeAnnotationRemoved="PdfViewer_ShapeAnnotationRemoved"/>

{% endhighlight %}

{% highlight c# %}

SfPdfViewer pdfViewer = new SfPdfViewer();
pdfViewer.ShapeAnnotationRemoved += PdfViewer_ShapeAnnotationRemoved;

{% endhighlight %}
{% endtabs %}

The properties of the removed shape annotation can be obtained from the `args` parameter of the event handler.

{% tabs %}
{% highlight c# %}

private void PdfViewer_ShapeAnnotationRemoved(object sender, ShapeAnnotationRemovedEventArgs args)
{
	//Get the type of the annotation. Here it is rectangle
	AnnotationMode annotationMode = args.AnnotationType;
	//Get the bounds of the rectangle
	Rectangle bounds = args.Bounds;
	//Get the data points of the shape
	List<Point> dataPoints = args.DataPoints;
	//Get the opacity value
	float opacity = args.Opacity;
	//Get the page number in which the annotations are present
	int pageNumber = args.PageNumber;
	//Get the position of the shape within the page
	Point position = args.Position;
	//Get the stroke color of the shape 
	Color strokeColor = args.StrokeColor;
	//Get the thickness of the shape
	float thickness = args.Thickness;
}

{% endhighlight %}
{% endtabs %}

## How to lock or unlock the shape annotations?
 
To lock or unlock all the shape annotation, set the `IsLocked` API to `true` or `false` respectively, and the following sample explains the same. But other annotation types can be moved, resized, removed or their attributes can be changed. 

{% tabs %}
{% highlight c# %}

//Disable the arrow annotation interaction such as move, resize, remove, and attributes changes.
pdfViewerControl.AnnotationSettings.Arrow.Settings.IsLocked = true;
//Disable the line annotation interaction such as move, resize, remove, and attributes changes.
pdfViewerControl.AnnotationSettings.Line.Settings.IsLocked = true; 
//Disable the rectangle annotation interaction such as move, resize, remove, and attributes changes.
pdfViewerControl.AnnotationSettings.Rectangle.Settings.IsLocked = true;
//Disable the circle annotation interaction such as move, resize, remove, and attributes changes.
pdfViewerControl.AnnotationSettings.Circle.Settings.IsLocked = true;
//Disable the polygon annotation interaction such as move, resize, remove, and attributes changes.
pdfViewerControl.AnnotationSettings.Polygon.Settings.IsLocked = true;
//Disable the polyline annotation interaction such as move, resize, remove, and attributes changes.
pdfViewerControl.AnnotationSettings.Polyline.Settings.IsLocked = true;

{% endhighlight %}
{% endtabs %}
 
Interactions with shape annotation types such as move, resize, remove or attribute changes will be allowed only if the `SfPdfViewer.AnnotationSettings.IsLocked` API is set to `false`. The following code prevents the unlocking of the shape annotations, although the `IsLocked` property of the shape annotation is set to `false`.
 
{% tabs %}
{% highlight c# %}

//Disable the shape annotation interaction, though its 'IsLocked' property is set to ‘false’ .
pdfViewerControl.AnnotationSettings.IsLocked = true;
pdfViewerControl.AnnotationSettings.Arrow.Settings.IsLocked = false;
pdfViewerControl.AnnotationSettings.Line.Settings.IsLocked = false;
pdfViewerControl.AnnotationSettings.Rectangle.Settings.IsLocked = false;
pdfViewerControl.AnnotationSettings.Circle.Settings.IsLocked = false;
pdfViewerControl.AnnotationSettings.Polygon.Settings.IsLocked = false;
pdfViewerControl.AnnotationSettings.Polyline.Settings.IsLocked = false;

{% endhighlight %}
{% endtabs %}

N> The `IsLocked` properties of the classes [RectangleAnnotation](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfPdfViewer.XForms.RectangleAnnotation.html), [CircleAnnotation](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfPdfViewer.XForms.CircleAnnotation.html), [LineAnnotation](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfPdfViewer.XForms.LineAnnotation.html) and [ArrowAnnotation](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfPdfViewer.XForms.ArrowAnnotation.html) have been marked as obsolete. Use the `RectangleAnnotation.Settings.IsLocked`, `CircleAnnotation.Settings.IsLocked`, `LineAnnotation.Settings.IsLocked` and `ArrowAnnotation.Settings.IsLocked` properties instead.

## How to enable or disable the shape annotation selection?

To enable or disable the shape annotation selection, set the `Constraints` API to `AnnotationConstraints.Selectable` or `~AnnotationConstraints.Selectable` respectively, and the following sample explains the same. But other annotation types can be selected, moved, resized, removed or their attributes can be changed. 

{% tabs %}
{% highlight c# %}

//Disable the selection of arrow annotations.
pdfViewerControl.AnnotationSettings.Arrow.Settings.Constraints = ~AnnotationConstraints.Selectable;
//Disable the selection of line annotations.
pdfViewerControl.AnnotationSettings.Line.Settings.Constraints = ~AnnotationConstraints.Selectable;
//Disable the selection of rectangle annotations. 
pdfViewerControl.AnnotationSettings.Rectangle.Settings.Constraints = ~AnnotationConstraints.Selectable;
//Disable the selection of circle annotations.
pdfViewerControl.AnnotationSettings.Circle.Settings.Constraints = ~AnnotationConstraints.Selectable;
//Disable the selection of polygon annotations.
pdfViewerControl.AnnotationSettings.Polygon.Settings.Constraints = ~AnnotationConstraints.Selectable;
//Disable the selection of polyline annotations.
pdfViewerControl.AnnotationSettings.Polyline.Settings.Constraints = ~AnnotationConstraints.Selectable;

{% endhighlight %}
{% endtabs %}

Shape annotation selection will be allowed only if the `SfPdfViewer.AnnotationSettings.Constraints` API is set to `AnnotationConstraints.Selectable`. The following code prevents the shape annotations selection, even though the `Constraints` property of the shape annotation is set to `AnnotationConstraints.Selectable`.

{% tabs %}
{% highlight c# %}

//Disable the shape annotation selection, though its 'Constraints' property is set to ‘AnnotationConstraints.Selectable’ 
pdfViewerControl.AnnotationSettings.Constraints= ~AnnotationConstraints.Selectable;
pdfViewerControl.AnnotationSettings.Arrow.Settings.Constraints = AnnotationConstraints.Selectable;
pdfViewerControl.AnnotationSettings.Line.Settings.Constraints = AnnotationConstraints.Selectable;
pdfViewerControl.AnnotationSettings.Rectangle.Settings.Constraints = AnnotationConstraints.Selectable;
pdfViewerControl.AnnotationSettings.Circle.Settings.Constraints = AnnotationConstraints.Selectable;
pdfViewerControl.AnnotationSettings.Polygon.Settings.Constraints = AnnotationConstraints.Selectable;
pdfViewerControl.AnnotationSettings.Polyline.Settings.Constraints = AnnotationConstraints.Selectable;

{% endhighlight %}
{% endtabs %}

## How to get and set the name of the shape annotations?

The PDF Viewer allows the users to get and set the name of shape annotations through the [Name](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfPdfViewer.XForms.IAnnotation.html#Syncfusion_SfPdfViewer_XForms_IAnnotation_Name) API. 

The following code sample explains modifying the name of the shape annotation in the [ShapeAnnotationAdded](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfPdfViewer.XForms.SfPdfViewer.html#Syncfusion_SfPdfViewer_XForms_SfPdfViewer_ShapeAnnotationAdded) event.

{% tabs %}
{% highlight c# %}

private void PdfViewerControl_ShapeAnnotationAdded(object sender, ShapeAnnotationAddedEventArgs args)
{
	//Sets the name for the annotation.
	(sender as ShapeAnnotation).Name = "Shape1";           
}

{% endhighlight %}
{% endtabs %}

N> For illustration purposes, we have only provided the sample for modifying the name of the shape annotation in the [ShapeAnnotationAdded](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfPdfViewer.XForms.SfPdfViewer.html#Syncfusion_SfPdfViewer_XForms_SfPdfViewer_ShapeAnnotationAdded) event. But this can be done in all other events as well. 

N>You can also explore our [Xamarin.Forms PDF Viewer example](https://github.com/syncfusion/xamarin-demos/tree/master/Forms/PdfViewer) to knows the functionalities of each feature.
