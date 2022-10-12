---
layout: post
title: Touch interaction events in Xamarin Pdf Viewer | Syncfusion
description: Learn here all about Touch interaction events support in Syncfusion Xamarin Pdf Viewer (SfPdfViewer) control and more.
platform: Xamarin
control: SfPdfViewer
documentation: ug
---

# Touch interaction events in Xamarin Pdf Viewer (SfPdfViewer)

## Tapped 

The [`Tapped`](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfPdfViewer.XForms.SfPdfViewer.html) event is triggered when the user taps on the document display area of the PDF Viewer control. The event argument of this event contains the following information:

* [`PageNumber`](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfPdfViewer.XForms.TouchInteractionEventArgs.html#Syncfusion_SfPdfViewer_XForms_TouchInteractionEventArgs_PageNumber)          : The page number where the tap event occurred.
* [`Position`](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfPdfViewer.XForms.TouchInteractionEventArgs.html#Syncfusion_SfPdfViewer_XForms_TouchInteractionEventArgs_Position) 			: The tapped position with respect to the PDF Viewer's client area.
* [`PagePosition`](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfPdfViewer.XForms.TouchInteractionEventArgs.html#Syncfusion_SfPdfViewer_XForms_TouchInteractionEventArgs_PagePosition) 			: The tapped position with respect to the PDF page.

## DoubleTapped

The [`DoubleTapped`](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfPdfViewer.XForms.SfPdfViewer.html) event is triggered when the user double taps on the document display area of the PDF Viewer control. The event argument of this event contains the following information:

* [`PageNumber`](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfPdfViewer.XForms.TouchInteractionEventArgs.html#Syncfusion_SfPdfViewer_XForms_TouchInteractionEventArgs_PageNumber)          : The page number where the double tap event occurred.
* [`Position`](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfPdfViewer.XForms.TouchInteractionEventArgs.html#Syncfusion_SfPdfViewer_XForms_TouchInteractionEventArgs_Position) 			: The double tapped position with respect to the PDF Viewer's client area.
* [`PagePosition`](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfPdfViewer.XForms.TouchInteractionEventArgs.html#Syncfusion_SfPdfViewer_XForms_TouchInteractionEventArgs_PagePosition) 			: The double tapped position with respect to the PDF page.

## LongPressed

The [`LongPressed`](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfPdfViewer.XForms.SfPdfViewer.html) event is triggered when the user long presses on the document display area of the PDF Viewer control. The event argument of this event contains the following information:

* [`PageNumber`](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfPdfViewer.XForms.TouchInteractionEventArgs.html#Syncfusion_SfPdfViewer_XForms_TouchInteractionEventArgs_PageNumber)          : The page number where the long press event occurred.
* [`Position`](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfPdfViewer.XForms.TouchInteractionEventArgs.html#Syncfusion_SfPdfViewer_XForms_TouchInteractionEventArgs_Position) 			: The long pressed position with respect to the PDF Viewer's client area.
* [`PagePosition`](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfPdfViewer.XForms.TouchInteractionEventArgs.html#Syncfusion_SfPdfViewer_XForms_TouchInteractionEventArgs_PagePosition) 			: The long pressed position with respect to the PDF page.

{% capture codesnippet1 %}
{% tabs %}
{% highlight xaml %}

<Grid x:Name="pdfViewGrid">
<syncfusion:SfPdfViewer x:Name="pdfViewerControl" Tapped="PdfViewerControl_Tapped"
DoubleTapped="PdfViewerControl_DoubleTapped" LongPressed="PdfViewerControl_LongPressed"
InputFileStream="{Binding PdfDocumentStream}"/>
</Grid>

{% endhighlight %}
{% endtabs %}
{% endcapture %}
{{ codesnippet1 | UnOrderList_Indent_Level_1 }}

{% capture codesnippet2 %}
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
//Gets the position of the PDF Viewer's client area where you tapped.
Point position = e.Position;
//Gets the position of the PDF page where you tapped.
Point pagePosition = e.PagePosition;
}

private void PdfViewerControl_DoubleTapped(object sender, Syncfusion.SfPdfViewer.XForms.TouchInteractionEventArgs e)
{
//Gets the page number of the PDF Viewer where you double tapped.
int pageNumber = e.PageNumber;
//Gets the position of the PDF Viewer's client area where you double tapped.
Point position = e.Position;
//Gets the position of the PDF page where you double tapped.
Point pagePosition = e.PagePosition;
}

private void PdfViewerControl_Tapped(object sender, Syncfusion.SfPdfViewer.XForms.TouchInteractionEventArgs e)
{
//Gets the page number of the PDF Viewer where you long pressed.
int pageNumber = e.PageNumber;
//Gets the position of the PDF Viewer's client area where you long pressed.
Point position = e.Position;
//Gets the position of the PDF page where you long pressed.
Point pagePosition = e.PagePosition;
}

{% endhighlight %}
{% endtabs %}
{% endcapture %}
{{ codesnippet2 | UnOrderList_Indent_Level_1 }}

N>You can refer to our [Xamarin PDF Viewer](https://www.syncfusion.com/xamarin-ui-controls/xamarin-pdf-viewer) feature tour page for its groundbreaking feature representations. You can also explore our [Xamarin.Forms PDF Viewer example](https://github.com/syncfusion/xamarin-demos/tree/master/Forms/PdfViewer) to knows the functionalities of each feature.
