---
layout: post
title: Rendering PDF pages using pdfium in Xamarin Pdf Viewer | Syncfusion
description: Learn here all about Rendering PDF pages using pdfium support in Syncfusion Xamarin Pdf Viewer (SfPdfViewer) control and more.
platform: xamarin
control: SfPdfViewer
documentation: UG
---

# Rendering PDF pages using pdfium in Xamarin Pdf Viewer (SfPdfViewer)

The [Xamarin PDF Viewer](https://www.syncfusion.com/xamarin-ui-controls/xamarin-pdf-viewer) allows using Pdfium, which is a third-party open-source PDF rendering engine, to render the pages of a PDF document. By default, the PdfViewer uses native PDF rendering. However, using the Pdfium rendering engine will overcome the defects in the native PDF rendering.

## Setting the Renderer property

Set the `CustomPdfRenderer` property to an instance of a class that implements the `IPdfRenderer` implementation. Implementing this interface is explained in detail in the following sections. 

If the `CustomPdfRenderer` property is not set, the pages are rendered using the default rendering of the SfPdfViewer control.

The [CustomPdfRenderer](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfPdfViewer.XForms.SfPdfViewer.html#Syncfusion_SfPdfViewer_XForms_SfPdfViewer_CustomPdfRenderer) property should be assigned to the [AlternatePdfRenderer](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfPdfViewer.XForms.ICustomPdfRendererService.html#Syncfusion_SfPdfViewer_XForms_ICustomPdfRendererService_AlternatePdfRenderer) property of the `CustomPdfRenderer` class as in the following code sample,

{% tabs %}
{% highlight c# %}
		// Provides functionality to render PDF pages using third-party PDF renderers.
		pdfViewer.CustomPdfRenderer = DependencyService.Get<ICustomPdfRendererService>().AlternatePdfRenderer;

{% endhighlight %}
{% endtabs %}

## PDFium renderer sample

The sample that illustrates loading a PDF using the Pdfium renderer in Android and UWP can be downloaded from the link below.
[https://www.syncfusion.com/downloads/support/directtrac/general/ze/PdfiumDemoSample-2002924505](https://www.syncfusion.com/downloads/support/directtrac/general/ze/PdfiumDemoSample-2002924505)

N>At present, this feature is available on Android and UWP platforms.

N>You can also explore our [Xamarin.Forms PDF Viewer example](https://github.com/syncfusion/xamarin-demos/tree/master/Forms/PdfViewer) to knows the functionalities of each feature.
