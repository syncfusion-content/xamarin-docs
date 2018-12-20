---
layout: post
title: Importing and exporting form data | Syncfusion
description: Importing and exporting form data
platform: Xamarin
control: SfPdfViewer
documentation: ug
---

# Importing and exporting form data

PDF viewer provides options to import and export data to and from form fields in the PDF document. The form data files with the following extensions are supported.

1. fdf
2. xfdf
3. json
4. xml

The required file type can be chosen from the `DataFormat` enumeration. In the following sections only the fdf file type is illustrated for brevity.

## Exporting form data 

The `ExportFormData` method exports the current data filled in the form fields into a stream in the specified file format. The name of the PDF, with extension, from which the data are exported should be given as the second argument to the method.

{% tabs %}
{% highlight c# %}

Stream fdfStreamToSave = pdfViewerControl.ExportFormData(DataFormat.Fdf, "PdfFileName.Pdf");

{% endhighlight %}
{% endtabs %}

N> While saving the stream returned by the `ExportFormData` method, the file name must have the same extension as the file type that was given as the first argument. e.g. In the above case the file type provided is `fdf`, so the saved file extension should be `.fdf`.

## Importing form data

The `ImportFormData` method imports the data from a file of specified type and fills the new data into the form fields.

{% tabs %}
{% highlight c# %}

Stream fdfStreamToImport = typeof(App).GetTypeInfo().Assembly.GetManifestResourceStream("SampleDefaultNamespace.Assets.FileName.fdf");
pdfViewerControl.ImportFormData(fdfStreamToImport, DataFormat.Fdf);

{% endhighlight %}
{% endtabs %}