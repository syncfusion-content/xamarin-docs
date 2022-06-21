---
layout: post
title: Free text annotations in Xamarin Pdf Viewer control | Syncfusion
description: Learn here all about Free text annotations support in Syncfusion Xamarin Pdf Viewer (SfPdfViewer) control and more.
platform: Xamarin
control: SfPdfViewer
documentation: ug
---

# Free text annotations in Xamarin Pdf Viewer (SfPdfViewer)

[Xamarin PDF Viewer](https://www.syncfusion.com/xamarin-ui-controls/xamarin-pdf-viewer) allows you to include free text annotations in a PDF document and provides options to modify or remove the existing ones.

## Adding free text annotations using toolbar

### Enabling free text annotation mode

Set the `AnnotationMode` property of the PDF viewer to `FreeText`. After setting the annotation mode, the zooming, panning, and scrolling will be disabled. Tap anywhere on the displayed PDF page, a popup will appear. Type the text in the popup and click &#34;Ok&#34; to add text to the page. Once the free text annotation is added, the zooming, panning, and scrolling will be enabled again.

{% tabs %}
{% highlight xaml %}

<syncfusion:SfPdfViewer x:Name="pdfViewer"/>
<Button x:Name="freeTextAnnotationButton" Command="{Binding AnnotationModeCommand, Source={x:Reference Name=pdfViewer}}" CommandParameter="FreeText" />

{% endhighlight %}

{% highlight c# %}

SfPdfViewer pdfViewer = new SfPdfViewer();
pdfViewer.AnnotationMode = AnnotationMode.FreeText;

{% endhighlight %}
{% endtabs %}

### Disabling free text annotation mode

Setting the annotation mode to `None` disables the free text mode.

{% tabs %}
{% highlight xaml %}

<syncfusion:SfPdfViewer x:Name="pdfViewer"/>
<Button x:Name="resetAnnotationButton" Command="{Binding AnnotationModeCommand, Source={x:Reference Name=pdfViewer}}" CommandParameter="None" />

{% endhighlight %}
{% highlight c# %}

pdfViewer.AnnotationMode = AnnotationMode.None;

{% endhighlight %}
{% endtabs %}

### Detecting the inclusion of free text annotations

The event `FreeTextAnnotationAdded` will be raised when a free text annotation is added to the PDF.

{% tabs %}
{% highlight xaml %}

<syncfusion:SfPdfViewer x:Name="pdfViewer" FreeTextAnnotationAdded="PdfViewer_FreeTextAnnotationAdded"/>

{% endhighlight %}

{% highlight c# %}

pdfViewer.FreeTextAnnotationAdded += PdfViewer_FreeTextAnnotationAdded;

{% endhighlight %}
{% endtabs %}

## Adding free text annotations programmatically

By `AddAnnotation` method , You can add the free text annotations programmatically. The created free text annotation object passed as a parameter. The `FreeTextAnnotation` instance acquires the text, page number and bounds as the parameters. 

The following code sample illustrates the same.

{% tabs %}
{% highlight c# %}

string text = "Syncfusion";
           
//Creates the free text annotation
FreeTextAnnotation freeTextAnnotation = new FreeTextAnnotation(text, 1, new Rectangle(100, 100, 100, 50));           

//Add the free text annotation to the specified page 
pdfViewer.AddAnnotation(freeTextAnnotation);

{% endhighlight %}
{% endtabs %}

## Detecting tap on free text annotations

Tapping a free text annotation selects it or deselects if it is already selected. The event `FreeTextAnnotationTapped` is raised when a free text is tapped.

{% tabs %}
{% highlight xaml %}

<syncfusion:SfPdfViewer x:Name="pdfViewer" FreeTextAnnotationTapped="PdfViewer_FreeTextAnnotationTapped"/>

{% endhighlight %}

{% highlight c# %}

pdfViewer.FreeTextAnnotationTapped += PdfViewer_FreeTextAnnotationTapped;

{% endhighlight %}
{% endtabs %}

## Selecting free text annotations

You can select a free text annotation by tapping on it. When a free text is selected, the `FreeTextAnnotationSelected` event will be raised. The properties of the selected free text can be retrieved using the `args` parameter of the event handler.

{% tabs %}
{% highlight c# %}

private void PdfViewer_FreeTextAnnotationSelected(object sender, FreeTextAnnotationSelectedEventArgs args)
{
	//Get the bounds
	Rectangle bounds = args.Bounds;

	//Get the page number on which the deselected free text is
	int pageNumber = args.PageNumber;

	//Get the text of the free text annotation
	string text = args.Text;

	//Get the text color
	Color textColor = args.TextColor;

	//Get the text size
	float textSize = args.TextSize;
}

{% endhighlight %}
{% endtabs %}

### Selecting free text annotation programmatically

By `SelectAnnotation` method, You can select the free text annotation programmatically. The specified free text annotation object passed as a parameter. 

The following code sample illustrates the same.

{% tabs %}
{% highlight c# %}

//Selects the specified free text annotation
pdfViewer.SelectAnnotation(freetextAnnotation);

{% endhighlight %}
{% endtabs %}

N> Once `SelectAnnotation` method is called and as long as the annotation stays selected, the `SelectedAnnotation` property will return the same instance as the parameter of this method.

## Deselecting free text annotations

You can deselect a selected free text annotation by tapping on it or somewhere on the PDF page. Deselection can be detected using the `FreeTextAnnotationDeselected` event.

{% tabs %}
{% highlight xaml %}

<syncfusion:SfPdfViewer x:Name="pdfViewer" FreeTextAnnotationDeselected="PdfViewer_FreeTextAnnotationDeselected"/>

{% endhighlight %}

{% highlight c# %}

pdfViewer.FreeTextAnnotationDeselected += PdfViewer_FreeTextAnnotationDeselected;

{% endhighlight %}
{% endtabs %}

### Deselecting free text annotation programmatically?

By `DeselectAnnotation` method, You can deselect the free text annotation. The specified free text annotation object passed as a parameter. 

The following code sample illustrates the same.

{% tabs %}
{% highlight c# %}

//Deselects the specified free text annotation 
pdfViewer.DeselectAnnotation(freetextAnnotation);

{% endhighlight %}
{% endtabs %}

N> There is no effect in calling `DeselectAnnotation` method, if the given annotation is not selected. Once this method is called, the `SelectedAnnotation` property will return null until any other annotation gets selected.

## Customizing the appearance of free text annotations

You can customize the default text color and text size of free text annotations to be added. This will not affect the already added free text annotations. The appearance of a selected free text can also be modified.  

### Setting the default text color

You can set the default text color of the free text annotations by using the `SfPdfViewer.AnnotationSettings.FreeTextAnnotationSettings.TextColor` property. Refer to the following code.
 
{% tabs %} 
{% highlight c# %}

pdfViewer.AnnotationSettings.FreeTextAnnotationSettings.TextColor = Color.Red;

{% endhighlight %}
{% endtabs %}

### Setting the default text size

You can set the default text size of the free text annotations by using the `SfPdfViewer.AnnotationSettings.FreeTextAnnotationSettings.TextSize` property. Refer to the following code example.

{% tabs %}
{% highlight c# %}

pdfViewer.AnnotationSettings.FreeTextAnnotationSettings.TextSize = 4; 

{% endhighlight %}
{% endtabs %}

### Setting the default background-color

You can set the background color for the free text annotations using the `SfPdfViewer.AnnotationSettings.FreeText.FillColor` property. The default value is set to `Color.Transparent`.

{% tabs %}
{% highlight c# %}

//Setting the background color of the free text annotation

pdfViewerControl.AnnotationSettings.FreeText.FillColor = Color.LightBlue;

{% endhighlight %}
{% endtabs %}

### Setting the default minimum size

By the `SfPdfViewer.AnnotationSettings.FreeText.MinimumSize` property, You can set the minimum size to which the free text annotations could be resized.
 
Refer the following code example:

{% tabs %}
{% highlight c# %}

//Sets the minimum size for the free text annotations
pdfViewerControl.AnnotationSettings.FreeText.MinimumSize = new Size(10, 10);

{% endhighlight %}
{% endtabs %}

### Changing the properties of a selected free text

You can change the properties of the selected annotation by casting the `sender` parameter of the `FreeTextAnnotationSelected` event handler to FreeTextAnnotation and modify its properties. The following code shows how to change the properties.

{% tabs %}
{% highlight c# %}
Button changeFreeTextPropertiesButton = new Button();
changeFreeTextPropertiesButton.Clicked += changeFreeTextPropertiesButton_Clicked;

FreeTextAnnotation selectedFreeTextAnnotation;

private void PdfViewer_FreeTextAnnotationSelected(object sender, FreeTextAnnotationSelectedEventArgs args)
{
	//Cast the sender object to FreeTextAnnotation
    selectedFreeTextAnnotation = sender as FreeTextAnnotation;
}

private void changeFreeTextPropertiesButton_Clicked(object sender, EventArgs e)
{
	//Change the color of the text
    selectedFreeTextAnnotation.Settings.TextColor = Color.Blue;

	//Change the size of the text
	selectedFreeTextAnnotation.Settings.TextSize = 7;
}

{% endhighlight %}
{% endtabs %}

## Moving or resizing free text annotations

To move or resize the annotation, it should be selected. After the selector appears, tapping and dragging anywhere inside the selector will move the annotation. Tapping on the bubbles around the selector and dragging will resize the annotation. 

### Detecting the move or resize of a free text annotation

The event `FreeTextAnnotationMovedOrResized` will be raised when you move or resize the free text annotation. 

{% tabs %}
{% highlight xaml %}

<syncfusion:SfPdfViewer x:Name="pdfViewer" FreeTextAnnotationMovedOrResized="PdfViewer_FreeTextAnnotationMovedOrResized"/>

{% endhighlight %}

{% highlight c# %}

pdfViewer.FreeTextAnnotationMovedOrResized += PdfViewer_FreeTextAnnotationMovedOrResized;

{% endhighlight %}
{% endtabs %}

The properties of the moved or resized free text can be obtained from the `args` parameter of the event handler.

{% tabs %}
{% highlight c# %}

private void PdfViewer_FreeTextAnnotationMovedOrResized(object sender, FreeTextAnnotationMovedOrResizedEventArgs args) 
{ 
     //Retrieve the old bounds of the annotation
     Rectangle oldBounds = args.OldBounds;

     //Retrieve the new bounds of the annotation
     Rectangle newBounds = args.NewBounds;
	 
	 //Retrieve the page number in which the free text is
     int pageNumber = args.PageNumber;
}

{% endhighlight %}
{% endtabs %}

## Deleting free text annotations

PDF viewer can remove a selected annotation or all annotations in the PDF document.

### Removing a selected free text annotation

The following code snippet illustrates removing a selected free text from the PDF document.

{% tabs %}
{% highlight xaml %}

<syncfusion:SfPdfViewer x:Name="pdfViewer" FreeTextAnnotationSelected="PdfViewer_FreeTextAnnotationSelected"/>
<Button x:Name="deleteFreeTextAnnotationButton" Grid.Row="1" Clicked="deleteFreeTextAnnotationButton_Clicked" />

{% endhighlight %}
{% highlight c# %}

FreeTextAnnotation selectedFreeTextAnnotation;

private void PdfViewer_FreeTextAnnotationSelected(object sender, FreeTextAnnotationSelectedEventArgs args)
{
	//Cast the sender object to free text annotation.
	selectedFreeTextAnnotation = sender as FreeTextAnnotation;
}

private void deleteFreeTextAnnotationButton_Clicked(object sender, EventArgs e)
{
	//Delete the selected free text annotation
	pdfViewer.RemoveAnnotation(selectedFreeTextAnnotation);
}

{% endhighlight %}
{% endtabs %}

### Removing all annotations

The `ClearAllAnnotations` method can be used to delete all annotations irrespective of their types from the PDF. 

{% tabs %}
{% highlight xaml %}

<syncfusion:SfPdfViewer x:Name="pdfViewer" />
<Button x:Name="deleteAllAnnotationsButton" Command="{Binding ClearAllAnnotationsCommand, Source={x:Reference Name=pdfViewer}} />

{% endhighlight %}
{% highlight c# %}

private void DeleteAllAnnotationsButton_Clicked(object sender, EventArgs e)
{
	pdfViewer.ClearAllAnnotations();
}

{% endhighlight %}
{% endtabs %}

### Detecting the removal of a free text

The event `FreeTextAnnotationRemoved` will be raised when a free text annotation is removed from the PDF.

{% tabs %}
{% highlight xaml %}

<syncfusion:SfPdfViewer x:Name="pdfViewer" FreeTextAnnotationRemoved="PdfViewer_FreeTextAnnotationRemoved"/>

{% endhighlight %}

{% highlight c# %}

pdfViewer.FreeTextAnnotationRemoved += PdfViewer_FreeTextAnnotationRemoved;

{% endhighlight %}
{% endtabs %}

The properties of the removed free text can be obtained from the `args` parameter of the event handler. 

{% tabs %}
{% highlight c# %}
private void PdfViewer_FreeTextAnnotationRemoved(object sender, FreeTextAnnotationRemovedEventArgs args)
{
	//Get the bounds 
	Rectangle bounds = args.Bounds;
	//Get the page number on which the deselected free text is 
	int pageNumber = args.PageNumber;
	//Get the text of the free text annotation 
	string text = args.Text;
	//Get the text color 
	Color textColor = args.TextColor;
	//Get the text size 
	float textSize = args.TextSize;
}
{% endhighlight %}
{% endtabs %}

## Render sticky notes annotation as free text annotation

To avoid data loss and by default, the sticky notes or popup annotation will be rendered as free-text annotation while importing or loading a document. Though the sticky notes annotations are rendered as free text annotations in the `SfPdfViewer`, they will be preserved as sticky notes annotation while saving and exporting. Only the change of text attribute will be preserved on save and export.

You can also avoid or restrict the sticky notes from being rendered as free text annotation by setting the `AllowRenderingPopupAsFreeText` property to `false`. The following code illustrates the same:

{% tabs %}
{% highlight c# %}

//Restrict the sticky notes or popup annotation from being rendered as free text annotation
pdfViewerControl.AnnotationSettings.AllowRenderingPopupAsFreeText = false;

{% endhighlight %}
{% endtabs %}

N>The support to add, render, and edit sticky notes annotation through UI or programmatically is not provided yet. Once the support is provided, the `AllowRenderingPopupAsFreeText` property will be deprecated.

## How to lock or unlock the free text annotations?
 
To lock or unlock all the free text annotation, set the `IsLocked` API to `true` or `false` respectively, and the following sample explains the same. But other annotation types can be moved, resized, removed or their attributes can be changed. 

{% tabs %}
{% highlight c# %}

//Disable the free text annotation interaction such as move, resize, remove, and attributes changes.
pdfViewerControl.AnnotationSettings.FreeText.IsLocked = true;

{% endhighlight %}
{% endtabs %}
 
Interactions with free text annotation types such as move, resize, remove or attribute changes will be allowed only if the `SfPdfViewer.AnnotationSettings.IsLocked` API is set to `false`. The following code prevents the unlocking of the free text annotations, although the `IsLocked` property of the free text annotation is set to `false`.
 
{% tabs %}
{% highlight c# %}

//Disable the free text annotation interaction, though its 'IsLocked' property is set to ‘false’ .
pdfViewerControl.AnnotationSettings.IsLocked = true;
pdfViewerControl.AnnotationSettings.FreeText.IsLocked = false;

{% endhighlight %}
{% endtabs %}

## How to enable or disable the free text annotation selection?

To enable or disable the free text annotation selection, set the `Constraints` API to `AnnotationConstraints.Selectable` or `~AnnotationConstraints.Selectable` respectively, and the following sample explains the same. But other annotation types can be selected, moved, resized, removed or their attributes can be changed. 

{% tabs %}
{% highlight c# %}

//Disable the selection of free text annotations.
pdfViewerControl.AnnotationSettings.FreeText.Constraints = ~AnnotationConstraints.Selectable;

{% endhighlight %}
{% endtabs %}

Free text annotation selection will be allowed only if the `SfPdfViewer.AnnotationSettings.Constraints` API is set to `AnnotationConstraints.Selectable`. The following code prevents the free text annotations selection, even though the `Constraints` property of the free text annotation is set to `AnnotationConstraints.Selectable`.

{% tabs %}
{% highlight c# %}

//Disable the free text annotation selection, though its 'Constraints' property is set to ‘AnnotationConstraints.Selectable’ 
pdfViewerControl.AnnotationSettings.Constraints= ~AnnotationConstraints.Selectable;
pdfViewerControl.AnnotationSettings.FreeText.Constraints = AnnotationConstraints.Selectable;

{% endhighlight %}
{% endtabs %}

## How to get and set the name of the free text annotations?

The PDF Viewer allows the users to get and set the name of free text annotations through the [Name](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfPdfViewer.XForms.IAnnotation.html#Syncfusion_SfPdfViewer_XForms_IAnnotation_Name) API.

The following code sample explains modifying the name of the free text annotation in the [FreeTextAnnotationAdded](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfPdfViewer.XForms.SfPdfViewer.html#Syncfusion_SfPdfViewer_XForms_SfPdfViewer_FreeTextAnnotationAdded) event. 

{% tabs %}
{% highlight c# %}

private void PdfViewerControl_ FreeTextAnnotationAdded (object sender, FreeTextAnnotationAddedEventArgs args)
{
//Sets the name for the annotation.
(sender as FreeTextAnnotation).Name = "FreeText1";           
}

{% endhighlight %}
{% endtabs %}

N>For illustration purposes, we have only provided the sample for modifying the name of the free text annotation in the [FreeTextAnnotationAdded](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfPdfViewer.XForms.SfPdfViewer.html#Syncfusion_SfPdfViewer_XForms_SfPdfViewer_FreeTextAnnotationAdded) event. But this can be done in all other events as well. 

N>You can also explore our [Xamarin.Forms PDF Viewer example](https://github.com/syncfusion/xamarin-demos/tree/master/Forms/PdfViewer) to knows the functionalities of each feature.
