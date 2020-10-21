---
layout: post
title: Touch interaction events in Xamarin Pdf Viewer | Syncfusion
description: Learn about Touch interaction events support in Syncfusion Xamarin Pdf Viewer (SfPdfViewer) control and more details.
platform: Xamarin
control: SfPdfViewer
documentation: ug
---

# Touch interaction events

## Tapped 

The [`Tapped`](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfPdfViewer.XForms.SfPdfViewer.html) event will be triggered when the user taps on the document display area of the PDF Viewer control. The event argument of this event contains the following information:

* [`PageNumber`](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfPdfViewer.XForms.TouchInteractionEventArgs.html#Syncfusion_SfPdfViewer_XForms_TouchInteractionEventArgs_PageNumber)          : The page number in which the tap event occurred.
* [`Position`](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfPdfViewer.XForms.TouchInteractionEventArgs.html#Syncfusion_SfPdfViewer_XForms_TouchInteractionEventArgs_Position) 			: The position of the tap event location with respect to the start of the page.

## DoubleTapped

The [`DoubleTapped`](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfPdfViewer.XForms.SfPdfViewer.html) event will be triggered when the user double taps on the document display area of the PDF Viewer control. The event argument of this event contains the following information:

* [`PageNumber`](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfPdfViewer.XForms.TouchInteractionEventArgs.html#Syncfusion_SfPdfViewer_XForms_TouchInteractionEventArgs_PageNumber)          : The page number in which the double tap event occurred.
* [`Position`](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfPdfViewer.XForms.TouchInteractionEventArgs.html#Syncfusion_SfPdfViewer_XForms_TouchInteractionEventArgs_Position) 			: The position of the double tap event location with respect to the start of the page.

## LongPressed

The [`LongPressed`](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfPdfViewer.XForms.SfPdfViewer.html) event triggered when the user long presses on the document display area of the PDF Viewer control. The event argument of this event contains the following information:

* [`PageNumber`](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfPdfViewer.XForms.TouchInteractionEventArgs.html#Syncfusion_SfPdfViewer_XForms_TouchInteractionEventArgs_PageNumber)          : The page number in which the double tap event occurred.
* [`Position`](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfPdfViewer.XForms.TouchInteractionEventArgs.html#Syncfusion_SfPdfViewer_XForms_TouchInteractionEventArgs_Position) 			: The position of the double tap event location with respect to the start of the page.

{% tabs %}
{% highlight xaml %}

<Grid x:Name="pdfViewGrid">
<syncfusion:SfPdfViewer x:Name="pdfViewerControl" Tapped="PdfViewerControl_Tapped"
DoubleTapped="PdfViewerControl_DoubleTapped" LongPressed="PdfViewerControl_LongPressed"
InputFileStream="{Binding PdfDocumentStream}"/>
</Grid>

{% endhighlight %}
{% endtabs %}

{% tabs %}
{% highlight c# %}

public MainPage()
{
InitializeComponent();

}

private void PdfViewerControl_LongPressed(object sender, Syncfusion.SfPdfViewer.XForms.TouchInteractionEventArgs e)
{
//Gets the page number of the PDF Viewer where you tapped.
int pageNumber = e.PageNumber;
//Gets the position of the PDF Viewer where you tapped.
Point position = e.Position;
}

private void PdfViewerControl_DoubleTapped(object sender, Syncfusion.SfPdfViewer.XForms.TouchInteractionEventArgs e)
{
//Gets the page number of the PDF Viewer where you double tapped.
int pageNumber = e.PageNumber;
//Gets the position of the PDF Viewer where you double tapped.
Point position = e.Position;
}

private void PdfViewerControl_Tapped(object sender, Syncfusion.SfPdfViewer.XForms.TouchInteractionEventArgs e)
{
//Gets the page number of the PDF Viewer where you long pressed.
int pageNumber = e.PageNumber;
//Gets the position of the PDF Viewer where you long pressed.
Point position = e.Position;
}

{% endhighlight %}
{% endtabs %}
