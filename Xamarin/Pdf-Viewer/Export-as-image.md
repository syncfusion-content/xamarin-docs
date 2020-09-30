---
layout: post
title: PDF to image conversion in Xamarin Pdf Viewer | Syncfusion
description: Convert pages of the PDF to image stream with custom scale factor using Syncfusion Xamarin.Forms PDF Viewer 
platform: Xamarin.Forms
control: SfPdfViewer
documentation: ug
---

# Exporting the pages of PDF document as images

The PdfViewerControl allows users to export the pages of a PDF document as image streams using the `ExportAsImage` and `ExportAsImageAsync` method. The resultant image streams can be saved as image files in the local storage.

## Exporting a single PDF page as image

To synchronously export a single PDF page as image, you should use the ExportAsImage method that accepts page index as its parameter. The following code example describes exporting page at index 0 as image stream. 

{% tabs %}
{% highlight c# %}

//Accessing the PDF document that is added as embedded resource as stream
var fileStream = typeof(App).GetTypeInfo().Assembly.GetManifestResourceStream("GettingStarted.Assets.Xamarin-Forms-Succinctly.pdf");
//Initialize the SfPdfViewer
SfPdfViewer pdfViewerControl = new SfPdfViewer();
//Load the PDF document as stream
pdfViewerControl.LoadDocument(fileStream);
//Export the page of PDF document to image stream with the given index
Stream stream = pdfViewerControl.ExportAsImage(0);

{% endhighlight %}
{% endtabs %}

To asynchronously export a single PDF page as image, you should use ExportAsImageAsync method that accepts page index as its parameter. The below code example illustrates exporting page at index 0 as image stream.

{% tabs %}
{% highlight c# %}

//Load the PDF document as stream
pdfViewerControl.LoadDocument(fileStream);
//Asynchronously export the page of PDF document to image stream with the given index
Stream stream = await pdfViewerControl.ExportAsImageAsync(1);

{% endhighlight %}
{% endtabs %} 

## Exporting a single PDF page as image with custom scale factor

To synchronously export a single PDF page as image with custom scale factor, you should use the ExportAsImage method that accepts page index and scale factor as its parameters. The following code example describes exporting page at index 0 with the scale factor 2.0 as image stream.

{% tabs %}
{% highlight c# %}

//Accessing the PDF document that is added as embedded resource as stream
var fileStream = typeof(App).GetTypeInfo().Assembly.GetManifestResourceStream("GettingStarted.Assets.Xamarin-Forms-Succinctly.pdf");
//Initialize the SfPdfViewer
SfPdfViewer pdfViewerControl = new SfPdfViewer();
//Load the PDF document as stream
pdfViewerControl.LoadDocument(fileStream);
//Export the 0th index of PDF page to image stream with size two times greater than the original size 
Stream stream = pdfViewerControl.ExportAsImage(0,2.0f);

{% endhighlight %}
{% endtabs %}

To asynchronously export a single PDF page as image with custom scale factor, you should use ExportAsImageAsync method that accepts page index and scale factor as its parameters. The below code example illustrates exporting page at index 0 with the scale factor 2.0 as image stream.

{% tabs %}
{% highlight c# %}

//Load the PDF document as stream
pdfViewerControl.LoadDocument(fileStream);
//Asynchronously export the 0th index of PDF page to image stream with size two times greater than the original size 
Stream stream = await pdfViewerControl.ExportAsImageAsync(0, 2.0f);

{% endhighlight %}
{% endtabs %}

## Exporting a range of PDF pages as images

To synchronously export a range of PDF pages as images, you should use the ExportAsImage method that accepts start page index and end page index as its parameter. The following code example describes exporting pages ranging between index 0 and 3 as image stream array.

{% tabs %}
{% highlight c# %}

var fileStream = typeof(App).GetTypeInfo().Assembly.GetManifestResourceStream("GettingStarted.Assets.Xamarin-Forms-Succinctly.pdf");
//Initialize the SfPdfViewer
SfPdfViewer pdfViewerControl = new SfPdfViewer();
//Load the PDF document as stream
pdfViewerControl.LoadDocument(fileStream);
//Export the pages of PDF document from the index 0 to 3 to the array of image stream
Stream[] stream = pdfViewerControl.ExportAsImage(0,3);

{% endhighlight %}
{% endtabs %}

To asynchronously export a range of PDF pages as images, you should use ExportAsImageAsync method that accepts start page index and end page index as its parameter. The below code example illustrates exporting pages ranging between index 0 and 3 as image stream array

{% tabs %}
{% highlight c# %}

//Load the PDF document as stream
pdfViewerControl.LoadDocument(fileStream);
//Asynchronously export the pages of PDF document from the index 0 to the index 3 to the array of image stream.
Stream[] stream = await pdfViewerControl.ExportAsImageAsync(0, 3);

{% endhighlight %}
{% endtabs %}

## Exporting a range of PDF pages as images with custom scale factor

To synchronously export a range of PDF pages as images, you should use the ExportAsImage method that accepts start page index, end page index, and scale factor as its parameter. The following code example describes exporting pages ranging between index 0 and 3 with the scale factor 2 as image stream array.

{% tabs %}
{% highlight c# %}

var fileStream = typeof(App).GetTypeInfo().Assembly.GetManifestResourceStream("GettingStarted.Assets.Xamarin-Forms-Succinctly.pdf");
//Initialize the SfPdfViewer
SfPdfViewer pdfViewerControl = new SfPdfViewer();
//Load the PDF document as stream
pdfViewerControl.LoadDocument(fileStream);
//Export the pages of PDF document from the index 0 to 3 to the array of image stream
//All the exported images are scaled 2 times larger than its original size
Stream[] stream = pdfViewerControl.ExportAsImage(0, 3, 2.0f);

{% endhighlight %}
{% endtabs %}

To asynchronously export a range of PDF pages as images, you should use ExportAsImageAsync method that accepts start page index, end page index and scale factor as its parameter. The below code example illustrates exporting pages ranging between index 0 and 3 with the scale factor 2 as image stream array

{% tabs %}
{% highlight c# %}

//Load the PDF document as stream
pdfViewerControl.LoadDocument(fileStream);
//Asynchronously export the pages of PDF document from the index 0 to the index 3 to the array of image stream.
// All the exported images are scaled 2 times larger than its original size
Stream[] stream = await pdfViewerControl.ExportAsImageAsync(0, 3, 2.0f);

{% endhighlight %}
{% endtabs %}