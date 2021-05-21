---
layout: post
title: Table of content navigation in Xamarin Pdf Viewer control | Syncfusion
description: Learn here all about Table of content navigation support in Syncfusion Xamarin Pdf Viewer (SfPdfViewer) control and more.
platform: Xamarin
control: SfPdfViewer
documentation: ug
---

# Table of content navigation in Xamarin Pdf Viewer (SfPdfViewer)

The [Xamarin PDF Viewer](https://www.syncfusion.com/xamarin-ui-controls/xamarin-pdf-viewer) navigates to a specific destination within the PDF document.


## How to disable document link navigation in PDF document using PDF viewer control?

Set the “EnableDocumentLinkAnnotation” property to false to disable the document link navigation in PDF viewer. 

{% tabs %}
{% highlight xaml %}

<syncfusion:SfPdfViewer x:Name="pdfViewerControl"  EnableDocumentLinkAnnotation=”false” InputFileStream="{Binding PdfDocumentStream}" />

{% endhighlight %}
{% endtabs %}

N>By default, the EnableDocumentLinkAnnotation property is set to true.

N>You can also explore our [Xamarin.Forms PDF Viewer example](https://github.com/syncfusion/xamarin-demos/tree/master/Forms/PdfViewer) to knows the functionalities of each feature.
