---
layout: post
title:  Table of content navigation in Xamarin Pdf Viewer | Syncfusion
description: Document Link Annotation or Table of content support in PDF Viewer Xamarin.Forms allows the user to navigate to specific destination within PDF document.
platform: Xamarin
control: SfPdfViewer
documentation: ug
---

# Working with Document Link Annotation (Table of content)

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