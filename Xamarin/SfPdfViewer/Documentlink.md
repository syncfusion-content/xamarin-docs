---
layout: post
title:  Working with Document Link Annotation (Table of content) | Syncfusion
description: Working with Document Link Annotation (Table of content)
platform: Xamarin
control: SfPdfViewer
documentation: ug
---

# Working with Document Link Annotation (Table of content)

The PDF viewer navigates to a specific destination within the PDF document.


## How to disable document link navigation in PDF document using PDF viewer control?

Set the “EnableDocumentLinkAnnotation” property to false to disable the document link navigation in PDF viewer. 

{% tabs %}
{% highlight xaml %}

<syncfusion:SfPdfViewer x:Name="pdfViewerControl"  EnableDocumentLinkAnnotation=”false” InputFileStream="{Binding PdfDocumentStream}" />

{% endhighlight %}
{% endtabs %}

N> By default, the EnableDocumentLinkAnnotation property is set to true.
