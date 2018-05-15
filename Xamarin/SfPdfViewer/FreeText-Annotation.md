---
layout: post
title:  Working with freetext annotations
description: Working with freetext annotations
platform: Xamarin.Forms
control: SfPdfViewer
documentation: ug
---

# Working with freetext annotations

PDF viewer allows you to include freetext annotations in a PDF document and provides options to modify or remove the existing freetext annotations.  

## Adding freetext annotations

### Enabling freetext annotation mode

Set the [AnnotationMode](https://help.syncfusion.com/cr/cref_files/xamarin/sfpdfviewer/Syncfusion.SfPdfViewer.XForms~Syncfusion.SfPdfViewer.XForms.SfPdfViewer~AnnotationMode.html) property of the PDF viewer to `FreeText`. After setting the annotation mode, tap any PDF page and a popup will appear. Zooming, panning and scrolling will be disabled. Type the text in the popup and click "OK" to add the typed text to the page. Once the freetext annotation is added to the page zooming, panning and scrolling will be enabled again.

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

### Disabling freetext annotation

Use the following code to reset the annotation mode to `None`.

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

### Detecting the inclusion of freetext annotation

The event `FreeTextAnnotationAdded` will be raised when a freetext annotation is added to the PDF. 

{% tabs %}
{% highlight xaml %}

<syncfusion:SfPdfViewer x:Name="pdfViewer" FreeTextAnnotationAdded="PdfViewer_FreeTextAnnotationAdded"/>

{% endhighlight %}

{% highlight c# %}

SfPdfViewer pdfViewer = new SfPdfViewer();
pdfViewer.FreeTextAnnotationAdded += PdfViewer_FreeTextAnnotationAdded;

{% endhighlight %}
{% endtabs %}

## Selecting a freetext annotation

You can select a freetext annotation by tapping it. When a freetext is selected the `FreeTextAnnotationSelected` event will be raised. 

### Changing the properties of the selected freetext

You can change the properties of the selected annotation by casting the `sender` object parameter of the `FreeTextAnnotationSelected` event's handler to FreeTextAnnotation and modifying its properties.  The following code shows how to change the properties. 

{% tabs %}
{% highlight xaml %}

<syncfusion:SfPdfViewer x:Name="pdfViewer" FreeTextAnnotationSelected="PdfViewer_FreeTextAnnotationSelected" />

{% endhighlight %}

{% highlight c# %}

SfPdfViewer pdfViewer = new SfPdfViewer();
pdfViewer.FreeTextAnnotationSelected += PdfViewer_FreeTextAnnotationSelected;

{% endhighlight %}
{% endtabs %}

{% tabs %}
{% highlight c# %}

private void PdfViewer_FreeTextAnnotationSelected(object sender, FreeTextAnnotationSelectedEventArgs args)
{
	//Cast the sender object to FreeTextAnnotation
    FreeTextAnnotation selectedFreeTextAnnotation = sender as FreeTextAnnotation;

    //Change the text color
    selectedFreeTextAnnotation.Settings.TextColor = Color.Red;

    //Change the text size
    selectedFreeTextAnnotation.Settings.TextSize = 4;
}

{% endhighlight %}
{% endtabs %}

## Customizing the default appearance of freetext annotations

You can customize the default text color and text size of all freetext annotations that are yet to be added. This will not affect the freetext annotations that were already added. Customizing these properties for an individual selected freetext is described in the 'Selecting a freetext annotation' section further below;

### Setting the default text color

You can set the default text color of the freetext annotations by using the `SfPdfViewer.AnnotationSettings.FreeTextAnnotationSettings.TextColor` property. Refer to the following code. 
 
{% highlight c# %}

SfPdfViewer pdfViewer = new SfPdfViewer();

pdfViewer.AnnotationMode = AnnotationMode.FreeText;

pdfViewer.AnnotationSettings.FreeTextAnnotationSettings.TextColor = Color.Red;

{% endhighlight %}

### Setting the default text size

You can set the default text size of the freetext annotations by using the `SfPdfViewer.AnnotationSettings.FreeTextAnnotationSettings.TextSize` property. Refer to the following code example. 

{% highlight c# %}

SfPdfViewer pdfViewer = new SfPdfViewer();

pdfViewer.AnnotationMode = AnnotationMode.FreeText;

pdfViewer.AnnotationSettings.FreeTextAnnotationSettings.TextSize = 4; 

{% endhighlight %}

## Deleting freetext annotations

The PDF viewer can remove a selected annotation or all the annotations in the PDF document. 

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

### Removing a selected freetext annotation.

The following code snippet illustrates removing a selected freetext from the PDF document.
{% tabs %}
{% highlight xaml %}

<syncfusion:SfPdfViewer x:Name="pdfViewer" FreeTextAnnotationSelected="PdfViewer_FreeTextAnnotationSelected"/>
<Button x:Name="deleteFreeTextAnnotationButton" Grid.Row="1" Clicked="deleteFreeTextAnnotationButton_Clicked" />

{% endhighlight %}
{% highlight c# %}

FreeTextAnnotation selectedFreeTextAnnotation;

private void PdfViewer_FreeTextAnnotationSelected(object sender, FreeTextAnnotationSelectedEventArgs args)
{
	//Cast the sender object to freetext annotation.
	selectedFreeTextAnnotation = sender as FreeTextAnnotation;
}

private void deleteFreeTextAnnotationButton_Clicked(object sender, EventArgs e)
{
	//Delete the selected freetext annotation
	pdfViewer.RemoveAnnotation(selectedFreeTextAnnotation);
}

{% endhighlight %}
{% endtabs %}

### Detecting the removal of a freetext

The event `FreeTextAnnotationRemoved` will be raised when a freetext annotation is removed from the PDF.

{% tabs %}
{% highlight xaml %}

<syncfusion:SfPdfViewer x:Name="pdfViewer" FreeTextAnnotationRemoved="PdfViewer_FreeTextAnnotationRemoved"/>

{% endhighlight %}

{% highlight c# %}

SfPdfViewer pdfViewer = new SfPdfViewer();
pdfViewer.FreeTextAnnotationRemoved += PdfViewer_FreeTextAnnotationRemoved;

{% endhighlight %}
{% endtabs %}

## Detecting a tap on freetext annotations

Tapping a freetext annotation selects it or deselects if it is already selected. The event `FreeTextAnnotationTapped` is raised when a freetext is tapped. 

{% tabs %}
{% highlight xaml %}

<syncfusion:SfPdfViewer x:Name="pdfViewer" FreeTextAnnotationTapped="PdfViewer_FreeTextAnnotationTapped"/>

{% endhighlight %}

{% highlight c# %}

SfPdfViewer pdfViewer = new SfPdfViewer();
pdfViewer.FreeTextAnnotationTapped += PdfViewer_FreeTextAnnotationTapped;

{% endhighlight %}
{% endtabs %}

## Deselecting freetext annotations

You can deselect a selected freetext annotation by tapping on it or somewhere else on the PDF page. Deselection can be detected using the `FreeTextAnnotationDeselected` event.

{% tabs %}
{% highlight xaml %}

<syncfusion:SfPdfViewer x:Name="pdfViewer" FreeTextAnnotationDeselected="PdfViewer_FreeTextAnnotationDeselected"/>

{% endhighlight %}

{% highlight c# %}

SfPdfViewer pdfViewer = new SfPdfViewer();
pdfViewer.FreeTextAnnotationDeselected += PdfViewer_FreeTextAnnotationDeselected;

{% endhighlight %}
{% endtabs %}

The following code shows how to retrieve the properties of the deselected freetext annotation.

{% tabs %}
{% highlight c# %}

private void PdfViewer_FreeTextAnnotationDeselected(object sender, FreeTextAnnotationDeselectedEventArgs args)
{ 
   //Get the bounds
   Rectangle bounds = args.Bounds;

   //Get the page number on which the deselected freetext is
   int pageNumber = args.PageNumber;

   //Get the text of the freetext annotation
   string text = args.Text;

   //Get the text color
   Color textColor = args.TextColor;

   //Get the text size
   float textSize = args.TextSize;
}

{% endhighlight %}
{% endtabs %}

## Moving or resizing the selected freetext annotation

Tap and drag the annotation to move it. It can be resized by selecting it and dragging the bubbles at the corners.  

### Detecting the move or resizing of a freetext annotation

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
	 //Determine whether the moved or resized annotation is a freetext annotation or some other annotation. 
	 
	 if(sender as FreeTextAnnotation == null)
	 {
		//The annotation is not a freetext
	 }
	 else
	 {
		//The annotation is a freetext
	 }
	 
     //Retrieve the old bounds of the annotation
     Rectangle oldBounds = args.OldBounds;

     //Retrieve the new bounds of the annotation
     Rectangle newBounds = args.NewBounds;
}

{% endhighlight %}
{% endtabs %}