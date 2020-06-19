---
layout: post
title:  Add & modify text markups PDF Viewer Xamarin.Forms | Syncfusion
description: PDF Viewer Xamarin.Forms allows user to highlight, underline and strikethrough the text content in the PDF document.
platform: Xamarin
control: SfPdfViewer
documentation: ug
---

# Working with text markup annotation

The PDF viewer supports to add, edit, and delete text markup annotations (highlight, underline, and strikethrough) in the PDF document.

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

## How to enable or disable text markup annotation interaction?

The interaction operation can be enabled or disabled for text markup annotation alone by setting the `IsLocked` API to `false` or `true` respectively.

For example, the following code disables the interaction operations for all text markup annotations in the PDF. But other annotation types can be selected, moved, resized, or removed. 

{% tabs %}
{% highlight c# %}

//Disable the text markup highlight annotation interaction
pdfViewerControl.AnnotationSettings.TextMarkup.Highlight.IsLocked = true;

//Disable the text markup underline annotation interaction
pdfViewerControl.AnnotationSettings.TextMarkup.Underline.IsLocked = true;

//Disable the text markup strikethrough annotation interaction
pdfViewerControl.AnnotationSettings.TextMarkup.Strikethrough.IsLocked = true;

{% endhighlight %}
{% endtabs %}

The interaction with text markup annotation types will be allowed only if the `SfPdfViewer.AnnotationSettings.IsLocked` API is set to `false`. The following code does not allow the interactions with text markup annotations, although the `IsLocked` property of the text markup annotation is set to `false`. 

{% tabs %}
{% highlight c# %}

//Disables the text markup annotation interaction, though its 'IsLocked' property is set to ‘false’ 
pdfViewerControl.AnnotationSettings.IsLocked = true;
pdfViewerControl.AnnotationSettings.TextMarkup.Highlight.IsLocked = false;
pdfViewerControl.AnnotationSettings.TextMarkup.Underline.IsLocked = false;
pdfViewerControl.AnnotationSettings.TextMarkup.Strikethrough.IsLocked = false;

{% endhighlight %}
{% endtabs %}