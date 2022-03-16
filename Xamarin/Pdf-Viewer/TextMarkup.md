---
layout: post
title: Text markup annotations in Xamarin Pdf Viewer | Syncfusion
description: Learn here all about Text markup annotations support in Syncfusion Xamarin Pdf Viewer (SfPdfViewer) control and more.
platform: Xamarin
control: SfPdfViewer
documentation: ug
---

# Text markup annotations in Xamarin Pdf Viewer (SfPdfViewer)

The [Xamarin PDF Viewer](https://www.syncfusion.com/xamarin-ui-controls/xamarin-pdf-viewer) supports to add, edit, and delete text markup annotations (highlight, underline, and strikethrough) in the PDF document.

## Highlight a text

The two ways to highlight a text in the PDF document are: 

1. By selecting the text and highlight option

	* Select the text in the PDF document.
    * Select “Highlight” option in the context menu that appears.
	
2. Enabling the highlight mode and selecting the text

By default, the PDF viewer will be in the scrolling and text selection mode. Once highlight annotation mode is activated, scrolling of the document will be frozen and highlight annotations will be included when you swipe over the texts in the pages of the PDF document.

XAML code to switch to highlight annotation mode

{% tabs %}
{% highlight xaml %}

<Button x:Name="highlightAnnotationButton" BackgroundColor="Transparent" Image="TextHighlightIcon.png" HorizontalOptions="CenterAndExpand" VerticalOptions="CenterAndExpand" Command="{Binding AnnotationModeCommand, Source={x:Reference Name=pdfViewerControl}}" CommandParameter=”Highlight” />

{% endhighlight %}
{% endtabs %}

C# code to switch to highlight annotation mode

{% tabs %}
{% highlight c# %}

pdfViewerControl.AnnotationMode = AnnotationMode.Highlight;

{% endhighlight %}
{% endtabs %}

XAML code to switch to normal mode from annotation mode.

{% tabs %}
{% highlight xaml %}

<Button x:Name="resetAnnotationButton" BackgroundColor="Transparent" Image="resetIcon.png" HorizontalOptions="CenterAndExpand" VerticalOptions="CenterAndExpand" Command="{Binding AnnotationModeCommand, Source={x:Reference Name=pdfViewerControl}}" CommandParameter=”None” />

{% endhighlight %}
{% endtabs %}

C# code to switch to normal mode from annotation mode.

{% tabs %}
{% highlight c# %}

pdfViewerControl.AnnotationMode = AnnotationMode.None;

{% endhighlight %}
{% endtabs %}

### Highlight the text programmatically

By `AddAnnotation` method , You can highlight the text programmatically. The created text markup annotation object passed as a parameter. The `TextMarkupAnnotation` instance acquires the `TextMarkupAnnotationType`, page number, start index and end index of the text as the parameters. 

The following code sample illustrates the same.

{% tabs %}
{% highlight c# %}

//Creates the text markup annotation             
TextMarkupAnnotation textMarkupAnnotation = new TextMarkupAnnotation(TextMarkupAnnotationType.Highlight, 2, 20, 200);        
   
//Add the text markup annotation to the specified page
pdfViewerControl.AddAnnotation(textMarkupAnnotation);

{% endhighlight %}
{% endtabs %}

## Underline a text

The two ways to underline a text in the PDF document are: 

1. By selecting the text and underline option

	* Select the text in the PDF document.
    * Select “Underline” option in the context menu that appears.
	
2. Enabling the underline mode and selecting the text

By default, the PDF viewer will be in the scrolling and text selection mode. Once underline annotation mode is activated, scrolling of the document will be frozen and underline annotations will be included when you swipe over the texts in the pages of the PDF document.

XAML code to switch to underline annotation mode

{% tabs %}
{% highlight xaml %}

<Button x:Name="underlineAnnotationButton" BackgroundColor="Transparent" Image="TextUnderlineIcon.png" HorizontalOptions="CenterAndExpand" VerticalOptions="CenterAndExpand" Command="{Binding AnnotationModeCommand, Source={x:Reference Name=pdfViewerControl}}" CommandParameter=”Underline” />

{% endhighlight %}
{% endtabs %}

C# code to switch to underline annotation mode

{% tabs %}
{% highlight c# %}

pdfViewerControl.AnnotationMode = AnnotationMode.Underline;

{% endhighlight %}
{% endtabs %}

XAML code to switch to normal mode from annotation mode.


{% tabs %}
{% highlight xaml %}

<Button x:Name="resetAnnotationButton" BackgroundColor="Transparent" Image="resetIcon.png" HorizontalOptions="CenterAndExpand" VerticalOptions="CenterAndExpand" Command="{Binding AnnotationModeCommand, Source={x:Reference Name=pdfViewerControl}}" CommandParameter=”None” />

{% endhighlight %}
{% endtabs %}

C# code to switch to normal mode from annotation mode.

{% tabs %}
{% highlight c# %}

pdfViewerControl.AnnotationMode = AnnotationMode.None;

{% endhighlight %}
{% endtabs %}

### Underline the text programmatically

By `AddAnnotation` method , You can underline the text programmatically. The created text markup annotation object passed as a parameter. The `TextMarkupAnnotation` instance acquires the `TextMarkupAnnotationType`, page number, start index and end index of the text as the parameters. 

The following code sample illustrates the same.

{% tabs %}
{% highlight c# %}

//Creates the text markup annotation             
TextMarkupAnnotation textMarkupAnnotation = new TextMarkupAnnotation(TextMarkupAnnotationType.Underline, 2, 20, 200);        
   
//Add the text markup annotation to the specified page
pdfViewerControl.AddAnnotation(textMarkupAnnotation);

{% endhighlight %}
{% endtabs %}

### Render squiggly annotation as an underline annotation

To avoid data loss, the squiggly annotation will be rendered as an underline annotation while importing or loading a document. Though the squiggly annotation is rendered as underline annotations in the `SfPdfViewer`, it will be preserved as a squiggly annotation while saving and exporting. Attributes changes like color, the opacity will also be preserved on save and export.

N>The support to add, render, and edit squiggly annotation through UI or programmatically is not provided yet.

## Strikethrough a text

The two ways to strikethrough a text in the PDF document are: 

1. By selecting the text and strikethrough option

	* Select the text in the PDF document.
    * Select “Strikethrough” option in the context menu that appears.
	
2. Enabling the strikethrough mode and selecting the text

By default, the PDF viewer will be in the scrolling and text selection mode. Once strikethrough annotation mode is activated, scrolling of the document will be frozen and strikethrough annotations will be included when you swipe over the texts in the pages of the PDF document.

XAML code to switch to strikethrough annotation mode

{% tabs %}
{% highlight xaml %}

<Button x:Name="strikethroughAnnotationButton" BackgroundColor="Transparent" Image="TextStrikethroughIcon.png" HorizontalOptions="CenterAndExpand" VerticalOptions="CenterAndExpand" Command="{Binding AnnotationModeCommand, Source={x:Reference Name=pdfViewerControl}}" CommandParameter=”Strikethrough” />

{% endhighlight %}
{% endtabs %}

C# code to switch to strikethrough annotation mode

{% tabs %}
{% highlight c# %}

pdfViewerControl.AnnotationMode = AnnotationMode.Strikethrough;

{% endhighlight %}
{% endtabs %}

XAML code to switch to normal mode from annotation mode.

{% tabs %}
{% highlight xaml %}

<Button x:Name="resetAnnotationButton" BackgroundColor="Transparent" Image="resetIcon.png" HorizontalOptions="CenterAndExpand" VerticalOptions="CenterAndExpand" Command="{Binding AnnotationModeCommand, Source={x:Reference Name=pdfViewerControl}}" CommandParameter=”None” />

{% endhighlight %}
{% endtabs %}

C# code to switch to normal mode from annotation mode.

{% tabs %}
{% highlight c# %}

pdfViewerControl.AnnotationMode = AnnotationMode.None;

{% endhighlight %}
{% endtabs %}

### Strikethrough the text programmatically

By `AddAnnotation` method , You can strikethrough the text programmatically. The created text markup annotation object passed as a parameter. The `TextMarkupAnnotation` instance acquires the `TextMarkupAnnotationType`, page number, start index and end index of the text as the parameters. 

The following code sample illustrates the same.

{% tabs %}
{% highlight c# %}

//Creates the text markup annotation             
TextMarkupAnnotation textMarkupAnnotation = new TextMarkupAnnotation(TextMarkupAnnotationType.Strikethrough, 2, 20, 200);        
   
//Add the text markup annotation to the specified page
pdfViewerControl.AddAnnotation(textMarkupAnnotation);

{% endhighlight %}
{% endtabs %}

## Selecting text markup annotation programmatically

By `SelectAnnotation` method ,You can select the text markup annotation programmatically. The specified text markup annotation object passed as a parameter.
 
The following code sample illustrates the same.

{% tabs %}
{% highlight c# %}

//Selects the specified text markup annotation
pdfViewerControl.SelectAnnotation(textMarkupAnnotation);

{% endhighlight %}
{% endtabs %}

N> Once `SelectAnnotation` method is called and as long as the annotation stays selected, the `SelectedAnnotation` property will return the same instance as the parameter of this method.

## Deselecting text markup annotation programmatically

By `DeselectAnnotation` method ,You can deselect the text markup annotation programmatically. The specified text markup annotation object passed as a parameter. 

The following code sample illustrates the same.

{% tabs %}
{% highlight c# %}

//Deselects the specified text markup annotation 
pdfViewerControl.DeselectAnnotation(textMarkupAnnotation);

{% endhighlight %}
{% endtabs %}

N> There is no effect in calling `DeselectAnnotation` method, if the given annotation is not selected. Once this method is called, the `SelectedAnnotation` property will return null until any other annotation gets selected.

## Deleting a text markup annotation

The PDF viewer removes a single annotation in the PDF document, removes all the annotations in a page, and removes all the annotations in the document.

### Removing a single annotation.

The following code snippet illustrates removing a single annotation from the PDF document.

{% tabs %}
{% highlight xaml %}

<syncfusion:SfPdfViewer x:Name="pdfViewerControl" TextMarkupSelected="PdfViewerControl_TextMarkupSelected" />

{% endhighlight %}
{% endtabs %}

C# code to remove selected annotation from the PDF document

{% tabs %}
{% highlight c# %}

private void PdfViewerControl_TextMarkupSelected(object sender, TextMarkupSelectedEventArgs args)
{
   TextMarkupAnnotation selectedAnnotation = sender as TextMarkupAnnotation;
   pdfViewerControl.RemoveAnnotation(selectedAnnotation);
}

{% endhighlight %}
{% endtabs %}

### Removing all the annotations in a page

The ClearAllAnnotations(int pageNumber) API can be used to remove all the annotations in a page of the PDF document. 

{% tabs %}
{% highlight xaml %}

<Button x:Name="clearAllAnnotationsButton" Clicked="clearAllAnnotationsButton_Clicked" />

{% endhighlight %}
{% endtabs %}

C# code to clear all the annotations in a given page number.

{% tabs %}
{% highlight c# %}

private void clearAllAnnotationsButton_Clicked(object sender, EventArgs e)
{
   pdfViewerControl.ClearAllAnnotations(pageNumber);
}
{% endhighlight %}
{% endtabs %}

### Removing all the annotations in the PDF document

The ClearAllAnnotations API can be used to remove all the annotations in the PDF document.

{% tabs %}
{% highlight xaml %}

<Button x:Name="clearAllAnnotationsButton" Clicked="clearAllAnnotationsButton_Clicked" />

{% endhighlight %}
{% endtabs %}

C# code to clear all the annotations in a PDF document.

{% tabs %}
{% highlight c# %}

private void clearAllAnnotationsButton_Clicked(object sender, EventArgs e)
{
   pdfViewerControl.ClearAllAnnotations();
}
{% endhighlight %}
{% endtabs %}

## Editing the color of the text markup annotation

You can edit the color of the text markup annotation before including the annotation and after including the annotation. 

### Before inclusion of the annotation or Default color

You can alter the default color of the annotation to change the color while including annotation. Refer to the following code sample. 

{% tabs %}
{% highlight c# %}

pdfViewerControl.AnnotationSettings.TextMarkup.Highlight.Color = Color.Red;
pdfViewerControl.AnnotationSettings.TextMarkup.Underline.Color = Color.Magenta;
pdfViewerControl.AnnotationSettings.TextMarkup.Strikethrough.Color = Color.Yellow;

{% endhighlight %}
{% endtabs %}

N>Setting this property will not edit the color of annotations that are included in prior.

### After inclusion of the annotation

* Select the annotation.
* TextMarkupSelected event will be triggered and you will get a copy of selected annotation. 
* Edit the copy of annotation, so that you can edit the color of the text markup annotation.          

The following code snippet illustrates the same.    
                     
{% tabs %}
{% highlight xaml %}

<syncfusion:SfPdfViewer x:Name="pdfViewerControl" TextMarkupSelected="PdfViewerControl_TextMarkupSelected" />

{% endhighlight %}
{% endtabs %}

{% tabs %}
{% highlight c# %}

private void PdfViewerControl_TextMarkupSelected(object sender, TextMarkupSelectedEventArgs args)
{
   TextMarkupAnnotation selectedAnnotation = sender as TextMarkupAnnotation;
   selectedAnnotation.Settings.Color = Color.Yellow;
}

{% endhighlight %}
{% endtabs %}

## Performing undo and redo

The PDF viewer performs undo and redo for the changes made in annotations in the PDF document. In text markup annotation undo and redo actions are provided for: 

* Inclusion of new text markup annotation.
* Deletion of text markup annotation.
* Changing the color of the text markup annotation. 

Refer to the following code sample to perform undo and redo operations:  

{% tabs %}
{% highlight xaml %}

<Button x:Name="undoButton" BackgroundColor="Transparent" Image="UndoIcon.png" HorizontalOptions="Center" VerticalOptions="Center" Command="{Binding PerformUndoCommand ,Source={x:Reference Name=pdfViewerControl}}"/>

<Button x:Name="redoButton" BackgroundColor="Transparent" Image="RedoIcon.png" HorizontalOptions="Center" VerticalOptions="Center" Command="{Binding PerformRedoCommand ,Source={x:Reference Name=pdfViewerControl}}"/>

{% endhighlight %}
{% endtabs %}

{% tabs %}
{% highlight c# %}

pdfViewerControl.PerformUndo();
pdfViewerControl.PerformRedo();

{% endhighlight %}
{% endtabs %}


## Saving the PDF document

After performing all the changes over the PDF document in the PDF viewer, the resultant document can be saved using the SaveDocument() API.

{% tabs %}
{% highlight xaml %}
<Button x:Name="saveButton" Clicked="saveButton_Clicked" />

{% endhighlight %}
{% endtabs %}

{% tabs %}
{% highlight c# %}

private void saveButton_Clicked(object sender, EventArgs e)
{
   Stream stream = pdfViewerControl.SaveDocument();
}
{% endhighlight %}
{% endtabs %}

N>The `CanUndo` property is used to identify whether a document loaded in the PDF viewer is edited or not. When this property is set to true, means that the document in the PDF viewer is edited. 

## How to lock or unlock the text markup annotations?
 
To lock or unlock all the text markup annotation, set the `IsLocked` API to `true` or `false` respectively, and the following sample explains the same. But other annotation types can be moved, resized, removed or their attributes can be changed. 

{% tabs %}
{% highlight c# %}

//Disable the text markup highlight annotation interaction such as remove and attributes changes.
pdfViewerControl.AnnotationSettings.TextMarkup.Highlight.IsLocked = true;

//Disable the text markup underline annotation interaction such as remove and attributes changes.
pdfViewerControl.AnnotationSettings.TextMarkup.Underline.IsLocked = true;

//Disable the text markup strikethrough annotation interaction such as remove and attributes changes.
pdfViewerControl.AnnotationSettings.TextMarkup.Strikethrough.IsLocked = true;

{% endhighlight %}
{% endtabs %}
 
Interactions with text markup annotation types such as remove or attribute changes will be allowed only if the `SfPdfViewer.AnnotationSettings.IsLocked` API is set to `false`. The following code prevents the unlocking of the text markup annotations, although the `IsLocked` property of the text markup annotation is set to `false`.
 
{% tabs %}
{% highlight c# %}

//Disable the text markup annotation interaction, though its 'IsLocked' property is set to ‘false’ 
pdfViewerControl.AnnotationSettings.IsLocked = true;
pdfViewerControl.AnnotationSettings.TextMarkup.Highlight.IsLocked = false;
pdfViewerControl.AnnotationSettings.TextMarkup.Underline.IsLocked = false;
pdfViewerControl.AnnotationSettings.TextMarkup.Strikethrough.IsLocked = false;

{% endhighlight %}
{% endtabs %}

## How to enable or disable the text markup annotation selection?

To enable or disable the text markup annotation selection, set the `Constraints` API to `AnnotationConstraints.Selectable` or `~AnnotationConstraints.Selectable` respectively, and the following sample explains the same. But other annotation types can be selected, moved, resized, removed or their attributes can be changed. 

{% tabs %}
{% highlight c# %}

//Disable the selection of text markup highlight annotation 
pdfViewerControl.AnnotationSettings.TextMarkup.Highlight.Constraints = ~AnnotationConstraints.Selectable;

//Disable the selection of text markup underline annotation
pdfViewerControl.AnnotationSettings.TextMarkup.Underline.Constraints = ~AnnotationConstraints.Selectable;

//Disable the selection of text markup strikethrough annotation
pdfViewerControl.AnnotationSettings.TextMarkup.Strikethrough.Constraints = ~AnnotationConstraints.Selectable;

{% endhighlight %}
{% endtabs %}

Text markup annotation selection will be allowed only if the `SfPdfViewer.AnnotationSettings.Constraints` API is set to `AnnotationConstraints.Selectable`. The following code prevents the text markup annotations selection, even though the `Constraints` property of the text markup annotation is set to `AnnotationConstraints.Selectable`.

{% tabs %}
{% highlight c# %}

//Disable the text markup annotation selection, though its 'Constraints' property is set to ‘AnnotationConstraints.Selectable’ 
pdfViewerControl.AnnotationSettings.Constraints = ~AnnotationConstraints.Selectable;
pdfViewerControl.AnnotationSettings.TextMarkup.Highlight.Constraints = AnnotationConstraints.Selectable;
pdfViewerControl.AnnotationSettings.TextMarkup.Underline.Constraints = AnnotationConstraints.Selectable;
pdfViewerControl.AnnotationSettings.TextMarkup.Strikethrough.Constraints = AnnotationConstraints.Selectable;

{% endhighlight %}
{% endtabs %}

## How to get and set the name of the text markup annotations?

The PDF Viewer allows the users to get and set the name of text markup annotations through the [Name](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfPdfViewer.XForms.IAnnotation.html#Syncfusion_SfPdfViewer_XForms_IAnnotation_Name) API.

The following code sample explains modifying the name of the text markup annotation in the [TextMarkupAdded](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfPdfViewer.XForms.SfPdfViewer.html#Syncfusion_SfPdfViewer_XForms_SfPdfViewer_TextMarkupAdded) event.

{% tabs %}
{% highlight c# %}
private void PdfViewerControl_TextMarkupAdded(object sender, TextMarkupAddedEventArgs args)
{
(sender as TextMarkupAnnotation).Name = "TextMarkupAnnotation1";
}
{% endhighlight %}
{% endtabs %}

N> For illustration purposes, we have only provided the sample for modifying the name of the text markup annotation in the [TextMarkupAdded](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfPdfViewer.XForms.SfPdfViewer.html#Syncfusion_SfPdfViewer_XForms_SfPdfViewer_TextMarkupAdded) event. But this can be done in all other events as well. 

N>You can also explore our [Xamarin.Forms PDF Viewer example](https://github.com/syncfusion/xamarin-demos/tree/master/Forms/PdfViewer) to knows the functionalities of each feature.
