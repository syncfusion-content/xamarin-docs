---
layout: post
title:  Working with freetext annotations | Syncfusion
description: Working with freetext annotations
platform: Xamarin
control: SfPdfViewer
documentation: ug
---

# Working with free text annotations

PDF viewer allows you to include free text annotations in a PDF document and provides options to modify or remove the existing ones.

## Adding free text annotations

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