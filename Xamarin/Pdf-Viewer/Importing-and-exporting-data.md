---
layout: post
title: Importing and exporting data in Xamarin Pdf Viewer | Syncfusion
description: PDF Viewer provides options to import and export data like form fields and annotations in the PDF document 
platform: Xamarin
control: SfPdfViewer
documentation: ug
---

# Importing and exporting data

PDF Viewer provides options to import and export data like form fields and annotations in the PDF document.

## Importing and exporting form data

The import and export of form data supports the following extensions.

* fdf
* xfdf
* json
* xml

The required file type can be chosen from the `DataFormat` enumeration. In the following sections only the fdf file type is explained for brevity.

### Exporting form data 

The `ExportFormData` method exports the current data filled in the form fields into a stream in the specified file format. The name of the PDF (with extension) from which the data are exported should be given as the second argument to the method.

{% tabs %}
{% highlight c# %}

//Export form data to "fdf" data format
Stream fdfStreamToSave = pdfViewerControl.ExportFormData(DataFormat.Fdf, "PdfFileName.fdf");

{% endhighlight %}
{% endtabs %}

N>While saving the stream returned by the `ExportFormData` method, the file name must have the same extension as the file type that was given as the first argument. For example, in the above case the file type provided is `fdf`, so the saved file extension should be `.fdf`.

### Importing form data

The `ImportFormData` method imports the data from a file of specified type and fills the saved data into the form fields.

{% tabs %}
{% highlight c# %}

//Import form data from "fdf" data format
Stream fdfStreamToImport = typeof(App).GetTypeInfo().Assembly.GetManifestResourceStream("SampleDefaultNamespace.Assets.PdfFileName.fdf");
pdfViewerControl.ImportFormData(fdfStreamToImport, DataFormat.Fdf);

{% endhighlight %}
{% endtabs %}

## Importing and exporting annotations

The import and export of annotations support following extensions.

* fdf
* xfdf

The required file type can be chosen from the `DataFormat` enumeration. In the following sections only the fdf file type is explained for brevity.

### Exporting annotations

The `ExportAnnotations` method exports the current annotations added to the document into a stream in the specified file format. The name of the PDF (with extension) from which the annotations are exported should be given as the second argument to the method.

{% tabs %}
{% highlight c# %}

//Export annotations to "fdf" data format
Stream fdfStreamToSave = pdfViewerControl.ExportAnnotations(AnnotationDataFormat.Fdf, "PdfFileName.fdf");

{% endhighlight %}
{% endtabs %}

### Export annotations asynchronously

The PDF Viewer allows you to export the current annotations added to the document into a stream asynchronously using the [`ExportAnnotationsAsync`](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfPdfViewer.XForms.SfPdfViewer.html#Syncfusion_SfPdfViewer_XForms_SfPdfViewer_ExportAnnotationsAsync_Syncfusion_Pdf_Parsing_AnnotationDataFormat_System_Threading_CancellationToken_) method. You can also cancel the asynchronous annotation exporting when it is in progress.

{% tabs %}
{% highlight c# %}

//Export the annotations asynchronously to the "fdf" data format 
Stream fdfStreamToSave = await pdfViewerControl.ExportAnnotationsAsync(AnnotationDataFormat.Fdf, cancellationTokenSource);

{% endhighlight %}
{% endtabs %}

In the above code sample, the `cancellationTokenSource` enables you to cancel the asynchronous annotation exporting when it is in progress.

N>While saving the stream returned by the [`ExportAnnotations`](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfPdfViewer.XForms.SfPdfViewer.html#Syncfusion_SfPdfViewer_XForms_SfPdfViewer_ExportAnnotations_Syncfusion_Pdf_Parsing_AnnotationDataFormat_) and [`ExportAnnotationsAsync`](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfPdfViewer.XForms.SfPdfViewer.html#Syncfusion_SfPdfViewer_XForms_SfPdfViewer_ExportAnnotationsAsync_Syncfusion_Pdf_Parsing_AnnotationDataFormat_System_Threading_CancellationToken_) method, the file name must have the same extension as the file type that was given as the first argument. e.g. In the above case the file type provided is `fdf`, so the saved file extension should be `.fdf`.

### Cancel the asynchronous annotations exporting

You can raise the cancel request when the annotations exporting is in progress

{% tabs %}
{% highlight c# %}

private void cancelButton_Clicked(object sender, EventArgs e)
 { 
   cancellationTokenSource.Cancel();
 }

{% endhighlight %}
{% endtabs %}

In the above code sample, the `cancellationTokenSource` instance is the same as the one given as the argument when exporting the annotations asynchronously.

N>Calling the above method will not have any effect once the annotations are completely exported. It will stop the exporting process only when it is in progress.

### Importing annotations

The `ImportAnnotations` method imports the annotations from the file of specified type and fills the saved annotations into the loaded PDF document.

{% tabs %}
{% highlight c# %}

//Import annotations from "fdf" data format
Stream fdfStreamToImport = typeof(App).GetTypeInfo().Assembly.GetManifestResourceStream("SampleDefaultNamespace.Assets.PdfFileName.fdf");
pdfViewerControl.ImportAnnotations(fdfStreamToImport, AnnotationDataFormat.Fdf);

{% endhighlight %}
{% endtabs %}